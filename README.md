# Angular Admin

## 预览效果

![登录](screenshot/login.png)

![首页](screenshot/index.png)

![列表](screenshot/list.png)

## 环境配置

### docker

> 修改`/etc/docker/daemon.json`

```json
{
  "registry-mirrors": ["https://lvpmz2sk.mirror.aliyuncs.com"]
}
```

### docker-compose

> 部分linux需要单独安装 

```shell
pip install docker-compose
```

### node.js

> npm加速

```shell
npm config set registry https://registry.npm.taobao.org
npm config set disturl https://npm.taobao.org/dist
```

> node-sass加速

- windows(环境变量)
   - 变量名(N): `SASS_BINARY_SITE`
   - 变量值(V): `https://npm.taobao.org/mirrors/node-sass/`
- linux或mac
   - `echo 'sass_binary_site=https://npm.taobao.org/mirrors/node-sass/' >> ~/.npmrc`

## 代码部署

**初始化命令**

```shell
# 启动
docker-compose up -d

# 升级
docker-compose up -d --build
```

**常用命令**

> docker环境命令格式`docker-compose exec server npm run setup`

```shell
npm run setup   # 初始化数据
npm run build   # 编译静态文件
npm run watch   # 本地调试模式

npm config set user 0 
npm config set unsafe-perm true
cnpm run build
ng server

```

## 备份还原

```
# 备份还原
npm run backup
npm run restore

# 指定还原点
npm run backup -- --point test
npm run restore -- --point test

# 单独web
npm run backup -- --type web
npm run restore -- --type web

# 单独mongo
npm run backup -- --type mongo
npm run restore -- --type mongo
```

## dashboard密码生成

> 在线生成工具： https://bcrypt-generator.com
