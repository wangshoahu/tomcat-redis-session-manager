# tomcat-redis-session-manager

> 使用redis配置tomcat共享session


### 必要环境：

* java1.7
* tomcat7.0.69
* redis2.9.0
* 以上版本可自行更改
* 源码来源：<a href="https://github.com/jcoleman/tomcat-redis-session-manager " target="_blank">tomcat-redis-session-manager</a>
* 打包生成tomcat-redis-session-manager.jar

## tomcat session共享配置步骤

1. 添加redis session集群依赖的jar包到 TOMCAT_BASE/lib 目录下

 		* tomcat-redis-session-manager.jar
 		* jedis-2.9.0.jar
 		* commons-pool2-2.4.2.jar


2. 修改 TOMCAT_BASE/conf 目录下的 context.xml 文件
			
			<Valve className="com.orangefunction.tomcat.redissessions.RedisSessionHandlerValve" />
               <Manager className="com.orangefunction.tomcat.redissessions.RedisSessionManager"
			  host="localhost"
			  port="6379"
			  database="0" 
			  maxInactiveInterval="60"/>
							
3. context.xml redis集群及其他配置见<a href="https://github.com/jcoleman/tomcat-redis-session-manager " target="_blank">tomcat-redis-session-manager</a>


