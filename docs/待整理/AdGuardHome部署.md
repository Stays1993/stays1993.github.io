# AdGuardHome 部署

项目地址：[AdguardTeam/AdGuardHome: Network-wide ads & trackers blocking DNS server](https://github.com/AdguardTeam/AdGuardHome)

# 安装 AdGuardHome

[自动安装（Linux/Unix/MacOS/FreeBSD/OpenBSD）](https://github.com/AdguardTeam/AdGuardHome?tab=readme-ov-file#automated-install-linuxunixmacosfreebsdopenbsd)

1. 使用`curl`进行安装，请运行以下命令：

```bash
curl -s -S -L https://raw.githubusercontent.com/AdguardTeam/AdGuardHome/master/scripts/install.sh | sh -s -- -v
```

```bash
# 加速地址
curl -s -S -L https://mirror.ghproxy.com/https://raw.githubusercontent.com/AdguardTeam/AdGuardHome/master/scripts/install.sh | sh -s -- -v
```

2. 使用`wget`安装，请运行以下命令：

```bash
wget --no-verbose -O - https://raw.githubusercontent.com/AdguardTeam/AdGuardHome/master/scripts/install.sh | sh -s -- -v
```

```bash
# 加速地址
wget --no-verbose -O - https://mirror.ghproxy.com/https://raw.githubusercontent.com/AdguardTeam/AdGuardHome/master/scripts/install.sh | sh -s -- -v
```

该脚本还接受一些选项：

- `-c <channel>` 使用指定通道；
- `-r` 重新安装 AdGuard Home；
- `-u` 卸载 AdGuard Home；
- `-v` 用于详细输出。

请注意，选项 `-r` 和 `-u` 是互斥的。

# AdGuardHome 命令

```bash
sudo /opt/AdGuardHome/AdGuardHome -s start|stop|restart|status|install|uninstall
```

- `satr`t：启动 AdGuard Home 服务
- `stop`：停止 AdGuard Home 服务
- `restart`：重启 AdGuard Home 服务
- `status`：查看 AdGuard Home 服务的状态
- `install`：安装 AdGuard Home 服务
- `uninstall`：卸载 AdGuard Home 服务

# DNS 设置

1.  上游 DNS 服务器

    这里一定不能用纯数字的 DNS，一定要用加密的。

    ```
    https://120.53.53.53/dns-query
    https://doh.360.cn/dns-query
    https://1.12.12.12/dns-query
    https://dns.alidns.com/dns-query
    https://223.5.5.5/dns-query

    # 候选
    https://dns.adguard.com/dns-query
    https://dns.cloudflare.com/dns-query
    tls://dns.google
    tcp://8.8.8.8
    tcp://8.8.4.4
    ```

    有 IPV6 的可以再添加下面三个 IPV6 的 DNS。

    ```
    # 阿里云：
    https://2400:3200::1/dns-query
    tls://2400:3200::1
    ```

2.  Bootstrap DNS 服务器

    Bootstrap DNS 服务器里填你最快的 DNS 服务器用于解析上面的 DoT/DoH，建议使用本地运营商 DNS，或者百度下载一个 DNS 优选软件，测试一下你最快的 DNS 填入即可，（不需要太多两三个就行）

    ```
    阿里云：
    223.5.5.5
    223.6.6.6
    ```

3.  DNS 服务配置

    - `EDNS 客户端子网` ：已知前面提及的上游 DNS 服务器都是支持 EDNS 技术的，它有助于获取到更合适的 CDN 节点，建议勾选。
    - `DNS sec` : 用于效验 DNS 记录的签名，防止 DNS 缓存被投毒，建议勾选。勾选后会在日志页面请求列显示小绿锁图标。
    - `禁用 ipv6`：丢弃 IPv6 的 DNS 查询。在本地网络和网站都支持 IPv6 会优先使用 IPv6 去访问网站，但目前 IPv6 的建设还处于初级阶段，大多数地区的 IPv6 网络体验都一般。还有一些代理软件对 IPv6 支持不佳，开启后可能会影响国际互联网的访问。如果对此没有特殊需求，那么勾选即可，这样既不影响 BT 软件连接 IPv6 网络，又可以优先使用 IPv4 来上网。如果只有 IPv4 ，那么是否勾选没有区别。

4.  DNS 缓存配置

    - `乐观缓存`: 启用

5.  参考链接：

- [平均处理时间 1ms，Adguard home 从安装到设置教程，DNS 防污染劫持，又快又稳-软路由,x86 系统,openwrt(x86),Router OS 等-恩山无线论坛](https://www.right.com.cn/forum/thread-8275129-1-1.html)
- [来吧，AdGuardHome 去广告和 DNS 正确姿势-OPENWRT 专版-恩山无线论坛](https://www.right.com.cn/forum/thread-4090928-1-1.html)

# ADH 广告拦截过滤规则

[BlueSkyXN/AdGuardHomeRules: 高达百万级规则！由我原创&整理的 AdGuardHomeRules ADH 广告拦截过滤规则！打造全网最强最全规则集](https://github.com/BlueSkyXN/AdGuardHomeRules)

## 主规则

### 国际用户 URL

#### 放在黑名单区

- https://raw.githubusercontent.com/BlueSkyXN/AdGuardHomeRules/master/all.txt 或者 https://raw.githubusercontent.com/BlueSkyXN/AdGuardHomeRules/master/all-lite.txt （二选一）
- https://raw.githubusercontent.com/BlueSkyXN/AdGuardHomeRules/master/skyrules.txt （建议开启）

#### 放在白名单区

- https://raw.githubusercontent.com/BlueSkyXN/AdGuardHomeRules/master/ok.txt （必须开启）

#### 动漫&漫画网站定制规则

- 三个等级，互不相同，请叠加使用，越高等级越容易误杀
- 目前这个已停止维护
- https://raw.githubusercontent.com/BlueSkyXN/AdGuardHomeRules/master/manhua.txt
- https://raw.githubusercontent.com/BlueSkyXN/AdGuardHomeRules/master/manhua-plus.txt
- https://raw.githubusercontent.com/BlueSkyXN/AdGuardHomeRules/master/manhua-max.txt

### 中国大陆用户特供 URL

#### 放在黑名单区

- https://mirror.ghproxy.com/https://raw.githubusercontent.com/BlueSkyXN/AdGuardHomeRules/master/all.txt 或者 https://mirror.ghproxy.com/https://raw.githubusercontent.com/BlueSkyXN/AdGuardHomeRules/master/all-lite.txt
- https://mirror.ghproxy.com/https://raw.githubusercontent.com/BlueSkyXN/AdGuardHomeRules/master/skyrules.txt

#### 放在白名单区

- https://mirror.ghproxy.com/https://raw.githubusercontent.com/BlueSkyXN/AdGuardHomeRules/master/ok.txt

#### 动漫&漫画网站定制规则

- 三个等级，互不相同，请叠加使用，越高等级越容易误杀
- 目前这个已停止维护
- https://mirror.ghproxy.com/https://raw.githubusercontent.com/BlueSkyXN/AdGuardHomeRules/master/manhua.txt
- https://mirror.ghproxy.com/https://raw.githubusercontent.com/BlueSkyXN/AdGuardHomeRules/master/manhua-plus.txt
- https://mirror.ghproxy.com/https://raw.githubusercontent.com/BlueSkyXN/AdGuardHomeRules/master/manhua-max.txt
