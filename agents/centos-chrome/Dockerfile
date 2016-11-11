FROM centos
MAINTAINER Henri

RUN yum -y update
RUN yum install -y wget
WORKDIR /opt/

RUN wget --no-cookies --no-check-certificate --header "Cookie: gpw_e24=http%3A%2F%2Fwww.oracle.com%2F; oraclelicense=accept-securebackup-cookie" "http://download.oracle.com/otn-pub/java/jdk/8u60-b27/jdk-8u60-linux-x64.rpm"
RUN yum localinstall -y jdk-8u60-linux-x64.rpm
RUN rm -f jdk-8u60-linux-x64.rpm
RUN wget http://selenium-release.storage.googleapis.com/3.0/selenium-server-standalone-3.0.1.jar
EXPOSE 4444

RUN wget https://dl.google.com/linux/direct/google-chrome-stable_current_x86_64.rpm
RUN yum install -y ./google-chrome-stable_current_*.rpm unzip gnome-terminal
RUN wget https://chromedriver.storage.googleapis.com/2.25/chromedriver_linux64.zip
RUN unzip chromedriver_linux64.zip
EXPOSE 5555
EXPOSE 5557
CMD java -jar selenium-server-standalone-3.0.1.jar -role node -hub http://172.17.0.2:4444/grid/register -browser browserName=chrome -port 5555; bash\
& java -Dwebdriver.chrome.driver=chromedriver -jar selenium-server-standalone-3.0.1.jar -role webdriver -hub http://172.17.0.2:4444/grid/register -browser browserName=chrome -port 5557


