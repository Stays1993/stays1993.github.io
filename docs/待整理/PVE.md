1. [佛西博客 - Proxmox VE（pve&kvm）中的 efi 系统](https://foxi.buduanwang.vip/virtualization/pve/509.html/)
2. [国光的 PVE 环境搭建教程](https://pve.sqlsec.com/)
3. [PVE 系列-初始化 LXC 容器并安装 Docker](https://gvnote.com/p/pve-lxc-setup-and-docker-install)
4. [显卡 ROM 文件下载 | TechPowerUp](https://www.techpowerup.com/vgabios/)

---

2. [img2KVM，将 IMG 格式转换为 KVM 格式，安装 DSM 群晖虚拟机 | 魔都水滴](https://blog.margrop.net/post/img2kvm-convert-img-format-file-to-kvm/)

- 安装 img2kvm

```bash
cd $HOME;
wget -c https://aa2.goca.top/d/Storage/PVE/img2kvm -O img2kvm;
chmod +x img2kvm;
mv img2kvm /usr/bin/img2kvm;
```

- 使用 img2kvm
  所用的命令格式为：
  > img2kvm <img_name> <vm_id> <vmdisk_name> [storage]

其具体参数说明如下：
`img_name`：是 IMG 文件名称。一般为“xxx.img”或“xxx.img.gz”的格式。img2kvm 可以直接识别并转换“img.gz”压缩格式的固件文件，对于“xxx.img.gz”来说，只需要输入“xxx.img”作为名称即可，不必再另外加“.gz”。
`vm_id`：是创建好的虚拟机的 ID。一般为一组非零开头的数字，如 100。
`vmdisk_name`：是虚拟机要使用的磁盘名称。建议采用 vm-<vm_id>-disk-<disk_id>的命名方式，如 vm-100-disk-1。
`storage`：是指导入使用的存储池的 ID，默认为“local-lvm”，这是安装 PVE 时自动创建的。此项为可选项，若不指定则使用默认值。
接下来，只需要在面板上，分配硬盘即可。

---

PVE 工具

1. [pve_source - X86 派 - 迷你硬件玩家集中地](https://bbs.x86pi.cn/thread?topicId=20)
2. [ivanhao/pvetools](https://github.com/ivanhao/pvetools)
