FROM tomcat:8-jre8

RUN rm -rf /usr/local/tomcat/webapps/*

COPY gameoflife-web-latest.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 4000
CMD ["catalina.sh", "run"]
