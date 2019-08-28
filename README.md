
# RUN

```$xslt
docker-compose.exe up
```
...for each folder.

# LINKS

**tomcat:** http://localhost:8080/ 

**tomcat_db:** localhost:3307

**tomcat_phpmyadmin:** http://localhost:8081/ 

**mysal:** localhost:3306 

**docker_GUI:** http://localhost:9000/#/containers

--------------------

default password
```$xslt
root
```

# troubleshoot

1) Problem with phpmyadmin login.
```
ALTER USER root IDENTIFIED WITH mysql_native_password BY 'PASSWORD';
```
2) Problem 403 with login to tomcat manager
```$xslt
Find the CATALINA_HOME/webapps/manager/META-INF/context.xml file 
and add the comment markers around the Valve.

<Context antiResourceLocking="false" privileged="true" >
<!--
<Valve className="org.apache.catalina.valves.RemoteAddrValve" allow="127\.\d+\.\d+\.\d+|::1|0:0:0:0:0:0:0:1" />
-->
</Context>
```