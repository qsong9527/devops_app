FROM ubuntu

# Refresh cache and install wget tool.
RUN apt-get update && apt-get install -y wget

# Setting work directory.
WORKDIR /home

####################################################
#
# Install and Configure JDK
#
# Install JDK 1.8
RUN wget --no-cookies --no-check-certificate --header "Cookie:gpw_e24=http%3a%2f%2fwww.oracle.com%2ftechnetwork%2fjava%2fjavase%2fdownloads%2fjdk7-downloads-1880260.html;oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u144-b01/090f390dda5b47b9b721c7dfaa008135/jdk-8u144-linux-x64.tar.gz
RUN tar -xzf jdk-8u144-linux-x64.tar.gz

# Configure Environment
ENV JAVA_HOME /home/jdk1.8.0_144
ENV JRE_HOME $JAVA_HOME/jre
ENV CLASSPATH .:$JAVA_HOME/lib:$JRE_HOME/lib
ENV PATH $PATH:$JAVA_HOME/bin

####################################################
#
# Install and Configure Tomcat
#
# Install Tomcat 8.5
RUN wget http://apache.communilink.net/tomcat/tomcat-8/v8.5.23/bin/apache-tomcat-8.5.23.tar.gz
RUN tar -xzf apache-tomcat-8.5.23.tar.gz

# Confiure Tomcat 8.5
ENV CATALINA_HOME /home/apache-tomcat-8.5.23

EXPOSE 8080

# Configure Tomcat auto start after start container.
CMD ["//home/apache-tomcat-8.5.23/bin/catalina.sh", "run"]

ENTRYPOINT echo hello world


