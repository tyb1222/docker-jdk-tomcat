# docker-jdk-tomcat
FROM centos
MAINTAINER centos_jdk_tomcat
RUN mkdir -p /software
COPY jdk1.8.0_20 /software/jdk1.8.0_20
COPY apache-tomcat-7.0.56 /software/apache-tomcat-7.0.56
ADD SCAS.war /software/apache-tomcat-7.0.56/webapps/SCAS.war
ENV JAVA_HOME=/software/jdk1.8.0_20/
ENV TOMCAT_HOME=/software/apache-tomcat-7.0.56/
ENV PATH=$JAVA_HOME/bin:$TOMCAT_HOME/bin:$PATH
ENV CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
EXPOSE 8080
ENTRYPOINT /software/apache-tomcat-7.0.56/bin/startup.sh
