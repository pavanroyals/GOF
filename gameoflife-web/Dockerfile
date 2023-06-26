FROM tomcat:8-jre8

COPY target/gameoflife.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080

CMD ["catalina.sh", "run"]
