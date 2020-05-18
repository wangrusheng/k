# Ubuntu 安装 Docker

[TOC]



# 1. 系统要求

Docker CE 支持以下版本的 [Ubuntu](https://www.ubuntu.com/server) 操作系统：

- Ubuntu Eoan 19.10
- Ubuntu Bionic 18.04 (LTS)
- Ubuntu Xenial 16.04 (LTS)

# 2. 卸载

旧版本的 Docker 称为 `docker` 或者 `docker-engine`，使用以下命令卸载：

```bash
#卸载
$ sudo apt-get remove docker docker-engine docker.io containerd runc
#删除Images, containers, volumes
$ sudo rm -rf /var/lib/docker
```

当前称为 Docker Engine-Community 软件包 docker-ce，使用以下命令卸载：

```bash
$ sudo apt-get purge docker-ce docker-ce-cli containerd.io
#删除Images, containers, volumes
$ sudo rm -rf /var/lib/docker
```

# 3. 安装docker的几种方式

* Docker 仓库安装

* 下载 DEB package 手动安装

* 开发、测试环境脚本自动安装

## Docker 仓库安装

### 设置仓库

1. 安装 apt 依赖包，用于通过HTTPS来获取仓库:

```bash
$ sudo apt-get update
$ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
```

2. 添加 Docker 的官方 GPG 密钥

```bash
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

验证您现在是否拥有密钥

```bash
#搜索指纹的后8个字符 9DC8 5822 9FC7 DD38 854A E2D8 8D81 803C 0EBF CD88 
$ sudo apt-key fingerprint 0EBFCD88
pub   4096R/0EBFCD88 2017-02-22
      Key fingerprint = 9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88
uid                  Docker Release (CE deb) <docker@docker.com>
sub   4096R/F273FCD8 2017-02-22
```

3. 使用以下指令设置稳定版仓库

```bash
$ sudo add-apt-repository "deb [arch=amd64] http://mirrors.aliyun.com/docker-ce/linux/ubuntu $(lsb_release -cs) stable"
```

### 安装 Docker Engine-Community

1. 安装最新版本的 Docker Engine-Community 和 containerd ，或者转到下一步安装特定版本：

```bash
 $ sudo apt-get update
 $ sudo apt-get install docker-ce docker-ce-cli containerd.io
```

2. 安装特定版本的 Docker Engine-Community

   a.  列出仓库里可用的版本:

```bash
$ apt-cache madison docker-ce

 docker-ce | 18.03.1~ce-0~ubuntu | http://mirrors.aliyun.com/docker-ce/linux/ubuntu xenial/stable amd64 Packages
 docker-ce | 18.03.0~ce-0~ubuntu | http://mirrors.aliyun.com/docker-ce/linux/ubuntu xenial/stable amd64 Packages
 docker-ce | 17.12.1~ce-0~ubuntu | http://mirrors.aliyun.com/docker-ce/linux/ubuntu xenial/stable amd64 Packages
```

​	b. 使用第二列中的版本字符串安装特定版本，例如 18.03.1\~ce-0\~ubuntu。

```bash
sudo apt-get install docker-ce=5:19.03.8~3-0~ubuntu-xenial docker-ce-cli=5:19.03.8~3-0~ubuntu-xenial containerd.io
```

3. 校验Docker 是否安装成功

```bash
$ sudo docker run hello-world
```

## 下载 DEB package 手动安装

1. 下载对应系统版本的deb包并上传到服务器。

   获取系统版本信息

   ```bash
   $ lsb_release -cs
   xenial
   ```

   打开`https://download.docker.com/linux/ubuntu/dists/xenial/pool/stable/amd64/`，选择某版本的`.deb`文件，下载并上传到服务器

   ```bash
   containerd.io_1.2.6-3_amd64.deb 
   docker-ce_19.03.8_3-0_ubuntu-xenial_amd64.deb 
   docker-ce-cli_19.03.8_3-0_ubuntu-xenial_amd64.deb 
   ```

2. 依次安装

   ```bash
   $ sudo dpkg -i containerd.io_1.2.6-3_amd64.deb 
   $ sudo dpkg -i docker-ce_19.03.8_3-0_ubuntu-xenial_amd64.deb
   $ sudo dpkg -i docker-ce-cli_19.03.8_3-0_ubuntu-xenial_amd64.deb
   ```

3. 校验Docker 是否安装成功

```bash
$ sudo docker run hello-world
```


## 开发、测试环境脚本自动安装

Docker 在 [get.docker.com ](https://get.docker.com/)和 [test.docker.com](https://test.docker.com/) 上提供了快捷脚本，用于将快速安装 Docker Engine-Community 的边缘版本和测试版本。脚本的源代码在 docker-install 仓库中。 不建议在生产环境中使用这些脚本，在使用它们之前，您应该了解潜在的风险。

1. 下载脚本并安装

```bash
$ curl -fsSL https://get.docker.com -o get-docker.sh
$ sudo sh get-docker.sh --mirror Aliyun
```

2. 校验Docker 是否安装成功

```bash
$ sudo docker run hello-world
```

# 4. 建立 docker 用户组

默认情况下，`docker` 命令会使用 [Unix socket](https://en.wikipedia.org/wiki/Unix_domain_socket) 与 Docker 引擎通讯。而只有 `root` 用户和 `docker` 组的用户才可以访问 Docker 引擎的 Unix socket。出于安全考虑，一般 Linux 系统上不会直接使用 `root`用户。因此，更好地做法是将需要使用 `docker` 的用户加入 `docker` 用户组。

建立 `docker` 组：

```bash
$ sudo groupadd docker
```

将当前用户加入 `docker` 组：

```bash
$ sudo usermod -aG docker $USER
#更新用户组
$ newgrp docker
```

# 4. 镜像加速

`vi /etc/docker/daemon.json`
加入如下内容

```json 
{
  "registry-mirrors": [
    "https://registry.docker-cn.com"
  ]
}
```

```bash
$ sudo systemctl daemon-reload
$ sudo systemctl restart docker

#检查加速器是否生效
docker info
#计算下载时间
time pull helloword
```

# 5. docker-compose
```bash
#安装
sudo curl -L "https://github.com/docker/compose/releases/download/1.25.5/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```

# 6. 参考

docker官方【[Install Docker Engine on Ubuntu](https://docs.docker.com/engine/install/ubuntu/)】

RUNOOB.COM【[ubuntu docker 安装](https://www.runoob.com/docker/ubuntu-docker-install.html)】



