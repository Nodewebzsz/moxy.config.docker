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
