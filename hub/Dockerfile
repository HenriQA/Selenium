FROM ubuntu
MAINTAINER Henri

RUN apt-get -y update
RUN apt-get install -y wget openjdk-8-jdk maven
WORKDIR /opt/
RUN wget http://selenium-release.storage.googleapis.com/3.0/selenium-server-standalone-3.0.1.jar
EXPOSE 4444
CMD java -jar selenium-server-standalone-3.0.1.jar -role hub -port 4444

