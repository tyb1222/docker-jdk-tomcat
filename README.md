# docker-jdk-tomcat
this is a dockerfile for tomcat app based on centos.Just use this file and start your docker app.
usage:
1、use the fllowing command to build image
  docker build -t centos_jdk_tomcat .
2、list all docker images
3、start image
  docker run -d -p 58080:8080 2d5242592b00
  
and then ,you can visit http://127.0.0.1:58080,
