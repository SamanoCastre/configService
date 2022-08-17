# Title of the project #
Config Service

# Description of the project
Config service is the microservice that centralizes all the configuration parameters of the other microservices, in particular the business microservices. 

Note : It must be the first to be launched in order to serve other microservices their configuration parameters


#Requirements
1. Java 17
2. Maven 3.8.6


#Dependencies
1. spring-cloud-config-server
2. spring-boot-starter-test

#Build
command line : mvn clean install (see jenkinsfile)

#Packaging the application
command line : mvn clean package -DskipTests (see the project's jenkins file)

#Deploy
command line : mvn spring-boot:run
