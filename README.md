
### 说明
无需安装docker，通过 [maven的jib插件](https://github.com/fishandsheep/jib) ,将本项目容器化并推送到dockerhub

### 构建步骤
1. 在parent 的 pom.xml 替换自己的 dockerhub 仓库(my-docker-id)、容器名称(my-app:my-tag)、账号(my_username)、密码(my_password)
```
<to>
    <image>docker.io/${my-docker-id}/${my-app:my-tag-name}</image>
    <auth>
        <username>${my_username}</username>
        <password>${my_password}</password>
    </auth>
</to>
```

2. 执行上传仓库的(无需安装docker)
```
     ./mvnw package jib:build -pl spider-flow-web -am
```

2. 仅push到本地(无需账号密码，需安装docker)
```
     ./mvnw package jib:dockerBuild -pl spider-flow-web -am
```

### fork by spider-flow
- [spider-flow](https://github.com/ssssssss-team/spider-flow)
