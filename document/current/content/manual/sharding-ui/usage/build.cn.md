+++
toc = true
title = "部署运行"
weight = 1
+++

## 部署运行

### Maven方式

1. `git clone https://github.com/apache/incubator-shardingsphere.git`。
1. 运行 `mvn clean install -Prelease`。
1. 获取安装包 `/sharding-distribution/shardingsphere-ui-distribution/target/apache-shardingsphere-incubating-${latest.release.version}--sharding-ui-bin.tar.gz`。
1. 解压缩后运行bin/start.sh。

### 前后分离

#### 后端
1. 后端程序执行入口为`org.apache.shardingsphere.ui.Bootstrap`

#### 前端
1. 进入`sharding-ui-frontend/`目录。
1. 执行`npm install`。
1. 执行`npm run dev`。
1. 访问`http://localhost:8080/`。

## 配置

Sharding-UI的配置文件为conf/application.properties, 它有两部分组成。

1. 程序监听端口。
1. 登录身份验证信息。

```properties
server.port=8088

user.admin.username=admin
user.admin.password=admin
```

## 注意事项
1. 若使用maven构建后，再进行本地运行前端项目时，可能因为node版本不一致导致运行失败，可以清空`node_modules/`目录后重新运行。