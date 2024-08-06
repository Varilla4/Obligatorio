FROM inovatrend/tomcat8-java8

ADD todo.war /opt/tomcat/webapps/

COPY tomcat-users.xml /opt/tomcat/conf/

RUN mkdir /opt/config

COPY app.properties /opt/config

EXPOSE 8080

CMD ["catalina.sh", "run"]