```bash
#!/bin/bash

# 配置变量
SOURCE_DIR="/path/to/source"               # 需要备份的源目录
BACKUP_DIR="//${SMB_SERVER_IP}/${SMB_SHARE_DIR}/backup"  # SMB备份的目标目录，使用变量代替IP和目录
COMPRESSED_BACKUP_DIR="/path/to/compressed" # 压缩包备份的目标目录
MAX_COMPRESSIONS=7                         # 保留的最大压缩包数量
SMB_USER="smb"                             # SMB用户名
SMB_PASSWORD="123456"                      # SMB密码（明文）
MOUNT_POINT="/mnt/docker_data"             # 临时挂载点
LOG_FILE="${BACKUP_DIR}/backup-$(date +%Y%m%d).log" # 在SMB共享中创建日志文件

# SMB 共享的 IP 和目录
SMB_SERVER_IP="192.168.9.252"              # SMB 服务器 IP 地址
SMB_SHARE_DIR="docker_data"                # SMB 共享的目录

# 确保备份目录存在
mkdir -p "${COMPRESSED_BACKUP_DIR}"

# 函数：写入日志文件
log_message() {
    echo "$1" | tee -a "${LOG_FILE}"
}

# 开始备份操作
log_message "备份操作开始：$(date)"

# 挂载SMB共享
log_message "正在挂载 SMB 共享..."
mount -t cifs "//${SMB_SERVER_IP}/${SMB_SHARE_DIR}" "${MOUNT_POINT}" -o username="${SMB_USER}",password="${SMB_PASSWORD}"
if [ $? -ne 0 ]; then
  log_message "挂载 SMB 共享失败，退出脚本。"
  exit 1
fi

# 使用rsync备份目录到SMB
log_message "开始使用 rsync 备份到 SMB 共享..."
rsync -avz --delete "${SOURCE_DIR}" "${BACKUP_DIR}"
if [ $? -ne 0 ]; then
  log_message "rsync 备份到 SMB 共享失败，退出脚本。"
  umount "${MOUNT_POINT}"
  exit 1
fi

# 创建压缩包
COMPRESSED_FILE="${COMPRESSED_BACKUP_DIR}/backup-$(date +%Y%m%d%H%M%S).tar.gz"
log_message "正在创建压缩包备份..."
tar -czf "${COMPRESSED_FILE}" -C "${SOURCE_DIR}" .
if [ $? -ne 0 ]; then
  log_message "创建压缩包备份失败，退出脚本。"
  umount "${MOUNT_POINT}"
  exit 1
fi

# 删除旧的压缩包，保留最新的7份
log_message "正在清理旧的压缩包..."
find "${COMPRESSED_BACKUP_DIR}" -name 'backup-*.tar.gz' -type f | sort | head -n -${MAX_COMPRESSIONS} | xargs -I {} rm {}
if [ $? -ne 0 ]; then
  log_message "删除旧的压缩包失败，退出脚本。"
  umount "${MOUNT_POINT}"
  exit 1
fi

# 卸载SMB共享
log_message "正在卸载 SMB 共享..."
umount "${MOUNT_POINT}"
if [ $? -ne 0 ]; then
  log_message "卸载 SMB 共享失败。"
  exit 1
fi

log_message "备份操作完成：$(date)"

```
