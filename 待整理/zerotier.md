## 相关链接

1. **[ZeroTier](https://my.zerotier.com/)**
2. [ZeroTier 实现内网穿透详细教程，其实 5 分钟就可以搞定-CSDN 博客](https://blog.csdn.net/weixin_44786530/article/details/128283075) [文章更新日期 2024-03-19]
3. [群晖 DSM7.x 使用 ZeroTier 套件的简单办法 - 我不是矿神](https://imnks.com/3175.html)
4.
5. [linux 系统的 ubuntu 下 zerotier 的基本使用教程\_ubuntu zerotier-CSDN 博客](https://blog.csdn.net/awzs7758520/article/details/130127967)
6. [通过 ZeroTier 异地组网 实现远程访问局域网 | ZhiChao's Blog](https://zhichao.org/posts/zerotier#%E9%85%8D%E7%BD%AE%E5%AE%A2%E6%88%B7%E7%AB%AF%E8%B7%AF%E7%94%B1)

## 下载安装 `Deepin V23专属`

第一步：下载`zerotier`安装包，[下载链接](http://download.zerotier.com/debian/buster/pool/main/z/zerotier-one/)

```bash
# 使用 wget 下载最新的 amd64 架构的 ZeroTier One .deb 文件
wget http://download.zerotier.com/debian/buster/pool/main/z/zerotier-one/zerotier-one_1.14.0_amd64.deb

# 使用 dpkg 安装下载的 .deb 文件
sudo dpkg -i zerotier-one_1.14.0_amd64.deb
```

这里下载一个 deb 包的 zerotier，版本选最新的，下载完成后安装。  
第二步：下载依赖[libssl1.1](http://security.ubuntu.com/ubuntu/pool/main/o/openssl/libssl1.1_1.1.1-1ubuntu2.1~18.04.23_amd64.deb)并安装：

```bash
# 使用 wget 下载 libssl1.1_1.1.1-1ubuntu2.1~18.04.23_amd64.deb
wget http://security.ubuntu.com/ubuntu/pool/main/o/openssl/libssl1.1_1.1.1-1ubuntu2.1~18.04.23_amd64.deb

# 使用 dpkg 安装下载的 .deb 文件
sudo dpkg -i libssl1.1_1.1.1-1ubuntu2.1~18.04.23_amd64.deb
```

## 其他安装方式

[Download - ZeroTier](https://www.zerotier.com/download/#entry-5)

### 使用脚本安装

`curl -s https://install.zerotier.com | sudo bash`

- 经过测试的操作系统/发行版：
  - MacOS (10.13+) (just installs ZeroTier One.pkg)
  - Debian Linux (7+)
  - RedHat/CentOS Linux (6+)
  - Fedora Linux (16+)
  - SuSE Linux (12+)
  - Mint Linux (20+)
  - Kali Linux (2024.1+)

## ZeroTier 使用

### 0. 初次使用命令

```bash
# 启动ZeroTier服务
systemctl start zerotier-one
systemctl enable zerotier-one

# 加入网络
sudo zerotier-cli join a09acf0233aa9942
```

### 1. 加入网络

首先在要连接的 Linux 设备上输入如下命令加入网络，如果连接成功就会出现 200 join OK 的状态码提示：

```bash
# 加入网络命令，操作成功则返回 “200 join OK”
sudo zerotier-cli join  a09acf0233aa9942
```

### 2. 查看当前连接

```bash
# 查看当前连接的网络，如果列表中出现 Network ID、Name 说明连接成功，后台分配好IP后再查看IP地址也会出现。
sudo zerotier-cli listnetworks
```

### 3. 断开当前加入的网络

```bash
# 断开网络命令，操作成功则返回 “200 leave OK”
sudo zerotier-cli leave ###########
```

## 常见错误及解决方法

1. LXC 容器无法使用 ZeroTier：

   - [错误：无法配置虚拟网络端口：无法打开 TUN/TAP 设备：没有此类文件或目录：r/zerotier --- ERROR: unable to configure virtual network port: could not open TUN/TAP device: No such file or directory : r/zerotier](https://www.reddit.com/r/zerotier/comments/l10x9f/error_unable_to_configure_virtual_network_port/)
   - [LXC 中的 OpenVPN - Proxmox VE --- OpenVPN in LXC - Proxmox VE](https://pve.proxmox.com/wiki/OpenVPN_in_LXC)

2. Deepin 无法安装 Zerotier：

   - [zerotier 安装不了－论坛－深度科技](https://bbs.deepin.org/post/274115) [文章更新日期 2024-07-10]

3. zerotier-one: fatal error: cannot bind to local control interface port 9993：
   如果出现此类报错， 表示端口被占用,使用以下命令查看
   `netstat -lp | grep 9993`
   如果 9993 被 ZeroTier 自己占用,则杀掉 `killall -9 zerotier-one` 之后重启服务,直到启动成功.
   -------楼主备注：输入多次，直到出现：`killall: zerotier-one: no process killed`
   启动完成后输入
   `sudo zerotier-cli join xxxxxxxxxxxxxxxx`

   或者更换端口：

   - [How I fixed zerotier-one: fatal error: cannot bind to local control interface port 9993 | TechOverflow](https://techoverflow.net/2022/09/27/how-i-fixed-zerotier-one-fatal-error-cannot-bind-to-local-control-interface-port-9993/)
