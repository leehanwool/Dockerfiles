FROM leehanwool/cent7-jdk7

MAINTAINER Nathan Lee <hwlee@itwise.co.kr>

ENV CATALINA_HOME /applications/tomcat
ENV PATH $CATALINA_HOME/bin:$PATH
ENV TOMCAT_MAJOR_VERSION 7
ENV TOMCAT_VERSION 7.0.57
ENV TOMCAT_TGZ_URL http://mirror.apache-kr.org/tomcat/tomcat-$TOMCAT_MAJOR/v$TOMCAT_VERSION/bin/apache-tomcat-$TOMCAT_VERSION.tar.gz

RUN yum install -y net-tools wget tar

WORKDIR /applications
# INSTALL TOMCAT
RUN curl "$TOMCAT_TGZ_URL" -o tomcat.tar.gz

RUN tar xvf tomcat.tar.gz

RUN rm -rf tomcat.tar.gz

EXPOSE 8080

