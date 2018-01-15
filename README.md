# Spring Config Server Files

## This acts as a repository for configuration files used by Spring Config Servers.

This repository contains a heirarchical file structure of properties folders. Under the top level are project folders. Each project folder should contain a folder for each separate microservice within the project. Generic properties files may be placed in this folder as well, and will apply to all services within the project. For instance, look at Sample Microservices Project. Within this folder are two folders and one file:
  - Sample Service 1
  - Sample Service 2
  - application.properties

Application.properties contains two lines: 
  - application.name=Sample Microservices Project
  - application.var1=master var1 value
  
Within each Sample Service folder is a properties file. In Sample Service 1 we have:
  - application.var1=SS1 var1 value
  - application.servicename=Sample Service 1

In Sample Service 2's properties file we just have:
  - application.servicename=Sample Service 2

This repo holds none of the code of the application, but assumes we have 3 services running: Sample Service 1, Sample Service 2, and a Spring Cloud Config Server. The config server will have its own properties file (separate from this repo), that will point to this git repo and allow it to host all of these properties files. The two services will each also have a properties file separate from this repo, and those properties files will just configure the connection to Spring Cloud Config Server.

With this setup, the services will be able to load properties from this repo on startup. Values in the main application.properties file will be overwritten by those in the service-specific files, so the final properties for each service will look like this:

Service 1:
  - application.name=Sample Microservices Project
  - application.var1=SS1 var1 value
  - application.servicename=Sample Service 1

Service 2:
  -- application.name=sample Microservices Project
  -- application.var1=master var1 value
  -- application.servicename=Sample Service 2

