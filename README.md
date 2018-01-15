# Spring Config Server Files

## This acts as a repository for configuration files used by Spring Config Servers.

This repository contains a heirarchical file structure of properties folders. Under the top level are project folders. Each project folder should contain a folder for each separate microservice within the project. Generic properties files may be placed in this folder as well, and will apply to all services within the project. For instance, look at Sample Microservices Project. Within this folder are two folders and one file:
  - Sample Service 1
  - Sample Service 2
  - application.properties

Application.properties contains two lines, application.name="Sample Microservices Project" and application.var1="master var1 value. Within each Sample Service folder is a properties file. In Sample Service 1 we have application.var1="Sample Service 1 var1 value", and application.servicename="Sample Service 1". In Sample Service 2 we just have application.servicename="Sample Service 2 
