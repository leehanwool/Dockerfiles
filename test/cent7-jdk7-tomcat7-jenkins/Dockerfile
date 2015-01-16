FROM leehanwool/cent7-jdk7

MAINTAINER Nathan Lee <hwlee@itwise.co.kr>

ENV CATALINA_HOME /applications/tomcat
ENV PATH $CATALINA_HOME/bin:$PATH
ENV TOMCAT_MAJOR_VERSION 7
ENV TOMCAT_VERSION 7.0.57
ENV TOMCAT_TGZ_URL http://mirror.apache-kr.org/tomcat/tomcat-$TOMCAT_MAJOR/v$TOMCAT_VERSION/bin/apache-tomcat-$TOMCAT_VERSION.tar.gz

RUN yum install -y net-tools wget tar

RUN mkdir -p "$CATALINA_HOME"

WORKDIR /applications
# INSTALL TOMCAT
#RUN wget -q http://mirror.apache-kr.org/tomcat/tomcat-$TOMCAT_MAJOR_VERSION/v$TOMCAT_VERSION/bin/apache-tomcat-$TOMCAT_VERSION.tar.gz
RUN curl -SL "$TOMCAT_TGZ_URL" -o tomcat.tar.gz \

#RUN tar -xvf apache-tomcat-$TOMCAT_VERSION.tar.gz
RUN tar -xvf tomcat.tar.gz

#RUN rm -rf apache-tomcat-$TOMCAT_VERSION.tar.gz
RUN rm -rf apache-tomcat.tar.gz


RUN wget http://mirrors.jenkins-ci.org/war-stable/latest/jenkins.war

#RUN mv jenkins.war /applications/apache-tomcat-$TOMCAT_VERSION/webapps/
RUN mv jenkins.war /applications/tomcat/webapps/
#RUN rm -rf jenkins.war

#WORKDIR /applications/apache-tomcat-$TOMCAT_VERSION/bin
WORKDIR /applications/tomcat/bin

RUN ./catalina.sh start