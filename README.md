---
services: service-fabric
platforms: dotnet
author: sondreb
---

# Service Fabric Web Socket Sample  #

This repository contains a sample project for Azure Service Fabric, the next-generation platform as a service offering from Microsoft. 

## Overview
This sample is a basic one that demonstrates how to host a Web Socket endpoint on Azure Service Fabric, relying on SignalR.

Sample was written to have a simpler and easier example, than the more elaborate existing sample by Microsoft:
https://github.com/Azure-Samples/service-fabric-dotnet-data-streaming-websockets

## Notes
Depending on how many instances of the service you deploy, you might need to configure the Network Load Balancer on Azure
to ensure connections have a fixed connection. When SignalR does connection negotiation, it sends 3 requests to the server
and it is important that all 3 goes to the same running service instance.

## Pre-Requisites
Visual Studio 2015

Before starting, make sure you have the Service Fabric development environment setup on your machine. Detailed instructions on how to setup the development environment can be found here https://azure.microsoft.com/en-gb/documentation/articles/service-fabric-get-started/ 
 
This solution is built against Service Fabric 5.1.163 (install using web platform installer by searching for "Service Fabric") 


## Download and building the source
Download the source and verify that you can build it in your local development environment by right clicking the DataStreaming solution and selecting Rebuild Solution. The solution uses the NuGet package manager to download and install its dependencies automatically.

Deploying the Solution to a Service Fabric Cluster 
- Right click on the Service Fabric application and select Publish 
- Select either your local cluster or your cloud deployment (requires that you have access to an Azure based Service fabric cluster).  For the purposes of these instructions we’ll assume you are deploying to a local dev box Service Fabric cluster
- Click Publish and validate the application deploys successfully. 
- Open Service Fabric Explorer and validate that the cluster and the service application and all sub-services are healthy

 
## Run The Test Client
There is a simple Test Client written as a C# Console App, that can be used to verify connection, stability and data transfer.



