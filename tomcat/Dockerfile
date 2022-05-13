FROM maven as maven

WORKDIR /usr/src/app
COPY . /usr/src/app
RUN mvn package

FROM tomcat:alpine

COPY --from=maven /usr/src/app/target/demo.war /usr/local/tomcat/webapps/demo.war

EXPOSE 8080

EXPOSE 8080
CMD ["catalina.sh", "run"]
