# Title of the project #
Config Service

# Description of the project
Config service is the microservice that centralizes all the configuration parameters of the other microservices, in particular the business microservices. 

Note : It must be the first to be launched in order to serve other microservices their configuration parameters


#Requirements
1. Java 17
2. Maven 3.8.6

#Build
command line : mvn clean install (see jenkinsfile)

#Packaging the application
command line : mvn clean package -DskipTests (see the project's jenkins file)

#Deploy
command line : mvn spring-boot:run

#Full system deployment order

1. Deploy the MS config-service as indicated in the readme.md located the classpath of the config-service project.
2. Deploy the MS registre-service as indicated in the readme.md located the classpath of the registre-service project.
3. Deploy the MS gateway-service as indicated in the readme.md located the classpath of the gateway-service project.
4. Deploy the MS hopital-service as indicated in the readme.md located the classpath of the hopital-service project.
5. Deploy the MS reservation-service as indicated in the readme.md located the classpath of the reservation-service project.
