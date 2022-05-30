FROM centos:latest
RUN sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-Linux-*
RUN sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-Linux-*
RUN yum install java-11-openjdk-devel -y
RUN mkdir /opt/tomcat
WORKDIR /opt/tomcat
ADD https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.63/bin/apache-tomcat-9.0.63.tar.gz .
RUN tar -xvzf apache-tomcat-9.0.63.tar.gz
RUN mv apache-tomcat-9.0.63/* /opt/tomcat
EXPOSE 8080
CMD ["/opt/tomcat/bin/catalina.sh","run"]
