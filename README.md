# moxycoding 所有站点部署配置示例

所需环境：`docker`,`docker-compose`

## 1.手动创建网络

> 所有的 docker-compose 构建的环境皆在 moxy_gateway 一个网络中，这样就可以使用服务名访问对应服务，进行通信

`docker network create moxy_gateway`

## 2.构建服务步骤

`cd moxy.admin.vue`

- `docker-compose pull`
- `docker-compose build`
- `(docker-compose down) 2>/dev/null`
- `docker-commpose up -d`

## 注意事项
- traefik： acme.json 需要手动创建`touch acme.json`并设置读写权限`chmod 600 acme.json`
- jenkins: 需要为 ./data 目录设置Jenkins用户权限 `sudo chown -R 1000 ./data`,jenkins中构建docker后，可使用 Publish Over SSH 远程连接到主机执行镜像的构建
