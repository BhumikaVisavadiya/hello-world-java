## Updated as of Aug 16, 2017
## Install FROM UBUNTU IMAGE
#FROM ubuntu:16.04
#
##Author of the Docker File
## MAINTAINER Pictolearn Note: MAINTAINER has been deprecated for LABEL,
## LABEL is a key value pair
#LABEL "Maintainer"="Bhumika"
#
## RUN COMMAND BASICALLY runs the command in the terminal and creates an image.
## Install all the updates for UBUNTU
#RUN apt-get update && apt-get install -y python-software-properties software-properties-common
#
## Install all the updates for UBUNTU
#RUN apt-get install -y iputils-ping
#
## Adds the repository where JDK 8 can be obtained for UBUNTU
##RUN add-apt-repository ppa:webup8team/java
#
## Install necessary packages
##RUN apt-get update && apt-get install -y openjdk-8-jdk \
##    && apt-get clean \
##    && rm -rf /var/lib/apt/lists/*
##
#
#RUN apt-get update && apt-get install -y openjdk-8-jdk && apt-get clean
#
## Set JAVA_HOME environment variable
#ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64
##ENV JAVA_HOME /usr/local/java-8-openjdk-amd64
#
#ENV PATH $JAVA_HOME/bin:$PATH
#
## Verify installation
#RUN java -version
#RUN which java
#
## Confirm JAVA_HOME
#RUN echo $JAVA_HOME
#RUN echo $PATH
#
#
## INSTALL THE VI EDITOR AND MYSQL-CLIENT
##RUN apt-get install -y vim
#RUN apt-get update && apt-get install -y vim
#RUN apt-get update && apt-get install -y mysql-client
#
## NOTE and WARNING: ORACLE JDK is no longer licensed. Please install default jdk or OPEN JDK.
## The initial set up was to get this working with JDK 7 but when the licensing terms for oracle changing we will install the default JDK
## INSTALL ORACLE JDK 8 BY ACCEPTING YES
## RUN echo "oracle-java8-installer shared/accepted-oracle-license-v1-1 boolean true" | debconf-set-selections
##INSTALL ALL the updates again and install MAVEN and JDK 8
## RUN apt-get update && apt-get install -y oracle-java8-installer maven
#RUN apt-get update && apt-get install -y default-jdk maven
#
#
## ADD a directory called docker-git-hello-world inside the UBUNTU IMAGE where you will be moving all of these files under this
## DIRECTORY to
#ADD . /usr/lib/jvm/docker-git-hello-world
#
## AFTER YOU HAVE MOVED ALL THE FILES GO AHEAD CD into the directory and run mvn assembly.
## Maven assembly will package the project into a JAR FILE which can be executed
#RUN cd /usr/lib/jvm/docker-git-hello-world
#RUN mvn assembly:assembly
#
##THE CMD COMMAND tells docker the command to run when the container is started up from the image. In this case we are
## executing the java program as is to print Hello World.
#CMD ["java", "-cp", "/usr/llib/jvm/docker-git-hello-world/target/docker-git-hello-world-0.0.1-SNAPSHOT-jar-with-dependencies.jar", "org.pictolearn.docker.HelloWorldPing"]

FROM ubuntu:20.04

RUN apt update
RUN apt install default-jdk -y
#RUN java -version
#RUN echo $JAVA_HOME
COPY . .
#RUN cd src/main/java/org/pictolearn/docker
RUN javac src/main/java/org/pictolearn/docker/HelloWorldPing.java
CMD ["java", "HelloWorldPing"]
#RUN javac Hello.java
#CMD ["java", "Hello"]