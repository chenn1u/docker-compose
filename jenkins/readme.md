# 中文界面

1. 系统管理-插件管理-download progress
2. 点一下 装完成后重启Jenkins(空闲时)
3. 等待重启

# maven

1. 系统管理-插件管理-available plugins
2. 安装[Maven Integration](https://plugins.jenkins.io/maven-plugin)
3. 安装[Config File Provider Plugin](https://plugins.jenkins.io/config-file-provider)
4. 系统管理-managed files-add a new config
5. 添加global maven和maven配置，可以在里面改镜像地址
6. build `clean install -DskipTests`
7. 以shell脚本执行springboot项目

```shell
BUILD_ID=dontKillMe
cd target
ps -ef | grep jhylj-java-0.0.1-SNAPSHOT.jar | grep -v grep | awk '{print "kill -15"$2}' | sh
nohup java -jar jhylj-java-0.0.1-SNAPSHOT.jar > jhylj.log 2>&1 &
```



