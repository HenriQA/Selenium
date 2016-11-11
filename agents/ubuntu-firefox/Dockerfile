FROM ubuntu
MAINTAINER Henri

RUN apt-get -y update
RUN apt-get -y upgrade
RUN apt-get install -y wget openjdk-8-jdk maven
WORKDIR /opt/
RUN wget http://selenium-release.storage.googleapis.com/3.0/selenium-server-standalone-3.0.1.jar
EXPOSE 4444

RUN apt-get install -y firefox
EXPOSE 5555
CMD java -jar selenium-server-standalone-3.0.1.jar -role node -hub http://172.17.0.2:4444/grid/register -browser browserName=firefox -port 5555


