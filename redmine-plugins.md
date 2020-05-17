# docker bitnami/redmie 安装

## pull image

```shell
#bitnami/redmine:4 相同tag不断更新，特性会相应变化，用Digest镜像不会变化
docker.io/bitnami/redmine@sha256:3f525ef4bc09cf2315d2391653ea0b82c57a8114afe0e11d7078d7bf4220ef97
docker tag b16779d2983b bitnami/redmine:4
```

## 准备docker-compose.yml[^bitnami-redmine]

2. docker-copose.yml

```yaml
version: '2'
services:
  mariadb:
    image: 'bitnami/mariadb:10.3'
    environment:
      - MARIADB_ROOT_PASSWORD=123456
      - MARIADB_USER=bn_redmine
      - MARIADB_DATABASE=bitnami_redmine
      - MARIADB_PASSWORD=123456
    volumes:
      - 'mariadb_data:/bitnami'
  redmine:
    image: 'bitnami/redmine:4'
    environment:
      - REDMINE_DB_PORT=3306
      - REDMINE_DB_USERNAME=bn_redmine
      - REDMINE_DB_NAME=bitnami_redmine
      - REDMINE_DB_PASSWORD=123456
    ports:
      - '80:3000'
    volumes:
      - 'redmine_data:/bitnami'
    depends_on:
      - mariadb
volumes:
  mariadb_data:
    driver: local
  redmine_data:
    driver: local
```

3. 上传docker-compose.yml到/opt/redmine

## 启动redmine
```shell
cd /opt/redmine
docker-compose up -d
```

地址：http://ip:80

用户：user

密码：bitnami1

## 安装plugin[^plugins]

### 下载plugin

* [redmine_checklists](https://www.redmine.org/plugins/redmine_checklists)

  redmine_checklists-3_1_17-light.zip

* [redmine_tags](https://www.redmine.org/plugins/redmine_tags)

  redmineup_tags-2_0_8-light.zip

* [redmine_questions](https://www.redmine.org/plugins/redmine_questions)

  redmine_questions-1_0_2-light.zip

### 上传plugin 到plugins

```shell
cd /var/lib/docker/volumes/redmine_redmine_data/_data/redmine/plugins
```


### 解压zip、删除zip
```shell
unzip redmine_checklists-3_1_16-light.zip
unzip redmineup_tags-2_0_8-light.zip
unzip redmine_questions-1_0_2-light.zip
```

### 进入redmine容器

```shell
docker exec -it redmine bash
```


### 进入redmine目录
```shell
cd /opt/bitnami/redmine
```

### 软件源

```shell
#查看源
cat /etc/apt/sources.list
```

```shell
echo 'deb http://mirrors.163.com/debian/ stretch main'>/etc/apt/sources.list
echo 'deb http://mirrors.163.com/debian-security/ stretch/updates main'>>/etc/apt/sources.list
```

```shell
#更新源
apt-get update
```

### 安装软件

```shell
install_packages vim gcc make default-libmysqlclient-dev postgresql-client libpq-dev  libmagickwand-dev
```
### 修改gem source

gem镜像:https://gems.ruby-china.com/

```shell
vim Gemfile
source 'https://gems.ruby-china.com'
```

### install

```shell
bundle install --without development test --no-deployment
bundle exec rake redmine:plugins NAME=redmineup_tags RAILS_ENV=production
bundle exec rake redmine:plugins NAME=redmine_checklists RAILS_ENV=production
bundle exec rake redmine:plugins NAME=redmine_questions RAILS_ENV=production
bundle exec rake redmine:plugins:migrate RAILS_ENV=production
```

### uninstall

```shell
bundle exec rake redmine:plugins:migrate NAME=redmine_questions VERSION=0 RAILS_ENV=production
cd /opt/bitnami/redmine/plugins
rm -rf redmine_questions
```

宿主机重启 redmine 生效

```shell
docker restart redmine
docker logs redmine
```

### 参考

[^bitnami-redmine]:Bitnami Images [docker-compose.yml](https://github.com/bitnami/bitnami-docker-redmine)
[^plugins]:[redmine-plugins](https://www.redmine.org/projects/redmine/wiki/Plugins)



