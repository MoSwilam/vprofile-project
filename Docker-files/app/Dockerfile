FROM openjdk:11 AS BUILD_IMAGE

LABEL project="V-Profile"
LABEL maintainer="Mo Swilam"

RUN apt update && apt install -y maven

RUN git clone https://github.com/devopshydclub/vprofile-project.git

RUN cd vprofile-project && git checkout docker && mvn install


FROM tomcat:9-jre10

ARG tomcatAppDir=/usr/local/tomcat/webapps/*

RUN rm -rf $tomcatAppDir

COPY --from=BUILD_IMAGE /vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080

CMD ["catalina.sh", "run"]