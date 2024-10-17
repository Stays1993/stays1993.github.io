用户配置文件

> $HOME/.config/containers/registries.conf

全局配置文件

> /etc/containers/registries.conf

配置文件

```conf
# 取消从默认地址搜索的仓库域名
# unqualified-search-registries = ["docker.io", "gcr.io", "ghcr.io", "quay.io", "registry.k8s.io"]

[registries.search]
registries = ['docker.io', 'quay.io', 'gcr.io', 'ghcr.io', 'registry.k8s.io']

# Docker Hub 镜像加速器配置
[[registries.mirror]]
prefix = "docker.io"
location = "docker.linkos.org"

# Google Container Registry
[[registries.mirror]]
prefix = "gcr.io"
location = "gcr.linkos.org"

# GitHub Container Registry
[[registries.mirror]]
prefix = "ghcr.io"
location = "ghcr.linkos.org"

# RedHat Quay
[[registries.mirror]]
prefix = "quay.io"
location = "quay.linkos.org"

# Kubernetes
[[registries.mirror]]
prefix = "registry.k8s.io"
location = "k8s.linkos.org"

# 如果加速器地址不支持HTTPS，可以添加insecure=true（但请注意安全风险）
# insecure = true
```

```toml
[registries.search]
registries = ['docker.io', 'quay.io', 'gcr.io', 'ghcr.io', 'registry.k8s.io']

[[registries.mirror]]
location = "您的Docker Hub镜像加速器地址"
prefix = "docker.io"

# 如果您需要为其他注册表配置镜像加速器，请添加更多的[[registries.mirror]]段
# 例如，为Google Container Registry配置加速器
# [[registries.mirror]]
# location = "您的Google镜像加速器地址"
# prefix = "gcr.io"

# 注意：如果加速器地址不支持HTTPS，并且您想绕过证书验证（不推荐，因为这可能会降低安全性），
# 您可以在Podman的命令行中使用--tls-verify=false选项，但不建议在registries.conf中直接配置insecure=true，
# 因为这可能会影响所有通过Podman进行的注册表交互。
```
