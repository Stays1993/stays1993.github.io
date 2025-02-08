 # 常用软件

1. google-chrome

    1.1. 下载Google Chrome deb包
    ```bash
    wget "https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb" -O google.deb
    ```

    1.2. 安装 Google Chrome
    ```bash
    sudo dpkg -i ./google.deb
    ```

    1.3. 删除 Google Chrome deb包(可选)
    ```bash
    sudo rm -rf ./google.deb
```

2. (微信)[https://linux.weixin.qq.com/]

    2.1 下载 微信Linux版 deb包
    ```bash
    wget "https://dldir1v6.qq.com/weixin/Universal/Linux/WeChatLinux_x86_64.deb" -O wechat.deb
    ```

    2.2. 安装 微信Linux版
    ```bash
    sudo apt install ./wechat.deb
    ```

    2.3 安装 libatomic1 依赖
    ```bash
    sudo apt install libatomic1
    ```

    2.4. 删除 微信Linux版 deb包(可选)
    ```bash
    sudo rm -rf ./wechat.deb
```

3. (vscode)[https://code.visualstudio.com/]

    3.1 通过snap进行安装
    ```bash
    sudo snap install --classic code
    ```

4. [星火商店](https://www.spark-app.store/download_latest)

    4.1 下载 [spark-store deb 包](https://gitee.com/spark-store-project/spark-store/releases/)
    下载最新的deb包，下载链接需要更换为最新版本的下载链接

    ```bash
    wget https://gitee.com/spark-store-project/spark-store/releases/download/4.3.3.2/spark-store_4.3.3.2_amd64.deb -O spark-store.deb
    ```

    4.2 安装 spark-store deb 包
    ```bash
    sudo apt install ./spark-store.deb
    ```

    4.3 删除 spark-store deb 包(可选)
    ```bash
    sudo rm -rf ./spark-store.deb
    ```

5. [fd-find](https://github.com/cha0ran/fd-zh) - 另一个终端查找文件工具

    5.1 安装 fd-find
    ```bash
    sudo apt install fd-find
    ```

    5.2 软连接fd命令
    ```
    sudo ln -s $(which fdfind) /usr/bin/fd
    ```

6. [kchmviewer] chm阅读器

    6.1 安装 fd-find
    ```bash
    sudo apt-get install kchmviewer
    ```

7. [todesk](https://www.todesk.com/linux.html)

## 配置文件
1. [chezmoi](https://www.chezmoi.io/install/)tar -xvf pycharm-professional-2024.3.1.1.tar.gz

    1.1 通过snmp安装 chezmoi
    ```bash
    snap install --classic chezmoi
    ```

    1.2 验证 chezmoi 安装
    ```bash
    chezmoi --version
    ```tar -xvf pycharm-professional-2024.3.1.1.tar.gz

    1.3 chezmoi的使用

    [`Stays1993/dofile`](https://github.com/Stays1993/dofile)

    2. [zsh]
    3. [zplug]
    4. [starship]


## KDE 美化

1. 图标 `Tela circle icon theme`


## 开发

1. Pycharm 专业版

    1.1. 下载 Pycharm 专业版.tar.gz 压缩包 [下载链接]https://www.jetbrains.com/pycharm/download/

    1.2. 解压到`/opt`目录下
    ```bash
    cd $HOME/Downloads
    tar -xvf pycharm-professional-2024.3.1.1.tar.gz
    sudo mv ./pycharm-2024.3.1.1 /opt/pycharm
    ```

2. 安装`Installing Miniconda`(https://docs.anaconda.com/miniconda/#miniconda-latest-installer-links/)
    ```bash
    mkdir -p $HOME/miniconda3
    wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O $HOME/miniconda3/miniconda.sh
    bash $HOME/miniconda3/miniconda.sh -b -u -p $HOME/miniconda3
    rm $HOME/miniconda3/miniconda.sh

    # 环境变量
    $HOME/miniconda3/bin/conda init bash
    $HOME/miniconda3/bin/conda init zsh
```

3. 安装[Node.js](https://nodejs.org/zh-cn/download)

    ```bash
    # Download and install nvm:
    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash

    # Download and install Node.js:
    nvm install 22

    # Verify the Node.js version:
    node -v # Should print "v22.13.0".
    nvm current # Should print "v22.13.0".

    # Verify npm version:
    npm -v # Should print "10.9.2".
        ```


——
——————————
# 其他
yt-dlp
steam
