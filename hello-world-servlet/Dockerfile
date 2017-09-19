FROM lmecld/modernwebapps:jdk-maven as builder
ADD . /src
RUN cd /src && mvn clean compile && mvn war:war


FROM tomcat:8.0
COPY --from=builder /src/target/hello-world-servlet.war /usr/local/tomcat/webapps/hello-world-servlet.war
EXPOSE 8080
CMD ["catalina.sh", "run"]
