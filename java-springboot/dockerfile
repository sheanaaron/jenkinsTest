# Start with a base image containing Maven 
FROM maven:3.6.3-jdk-8

# Add Maintainer Info
MAINTAINER Somansh Kumar <somansh@akeo.no>

# Creating Code repo
RUN mkdir /home/app

# Working Directory
WORKDIR /home/app

# Copying files from repo to Working Directory
COPY . /home/app

# Creating JAR package
RUN mvn clean package

# Add a volume 
VOLUME /tmp

# Make port 8080 available to the world outside this container
EXPOSE 8080

# The application's jar file
ARG JAR_FILE=/home/app/target/sample-websocket-demo-0.0.1.jar

# Copying JAR file
RUN cp /home/app/target/sample-websocket-demo-0.0.1.jar /sample-websocket.jar

# Run the jar file 
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","/sample-websocket.jar"]

