FROM leehanwool/cent7-jdk7

MAINTAINER Nathan Lee <hwlee@itwise.co.kr>

ENV TOMCAT_MAJOR_VERSION 7
ENV TOMCAT_VERSION 7.0.57


RUN yum install -y net-tools wget tar

RUN mkdir applications

WORKDIR /applications
# INSTALL TOMCAT
RUN wget -q http://mirror.apache-kr.org/tomcat/tomcat-$TOMCAT_MAJOR_VERSION/v$TOMCAT_VERSION/bin/apache-tomcat-$TOMCAT_VERSION.tar.gz

RUN tar xvf apache-tomcat-$TOMCAT_VERSION.tar.gz

RUN rm -rf apache-tomcat-$TOMCAT_VERSION.tar.gz


RUN wget http://mirrors.jenkins-ci.org/war-stable/latest/jenkins.war

RUN mv jenkins.war /applications/apache-tomcat-$TOMCAT_VERSION/webapps/
RUN rm -rf jenkins.war

WORKDIR /applications/apache-tomcat-$TOMCAT_VERSION/bin

RUN ./catalina.sh start