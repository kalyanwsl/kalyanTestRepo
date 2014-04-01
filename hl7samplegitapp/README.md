[Purpose](#purpose)  
[Prerequisites](#prerequisites)  
[Steps to use Mule Deployment plugin](#steps to use mule deployment plugin)  

[Running the deployment plugin](#running the deployment plugin)  
[Resources](#resources)

Purpose
=======

Mule Deployment Plugin designed to deploying a Mule Deployable Artifact (.zip) file to standalone ESB runtime, MMC and Cluster using the REST API of MMC.

Prerequisites
=============

In order to build and run this deployment plugin you'll need:  

* Maven to run the mule-deployment-plugin.
* Mule standalone ESB runtime if deploying on Mule standalone instance. FTP server(like Filezilla) needed if artifact needs to be deployed through network.
* Mule Management Console(MMC) if deploying on MMC.
* Cluster configuration on MMC if deploying on Cluster.

Steps to use Mule Deployment plugin
===================================

Following steps need to take to deploy mule applications on mule server using this plugin.
1. After cloning the ‘mule-deployment-plugin’ (Maven Plugin) from GIT repository (https://github.com/WhiteSky-Labs/wsl-mule-utils/tree/master/mule-deployment-plugin), Add below pluginGroup element to MAVEN_HOME/conf/setting.xml file. groupId (com.whiteskylabs.muledeployment.goals) of the ‘mule-deployment-plugin’ should be added to <pluginGroup> element as shown in below snippet. 
                 <pluginGroups>
                         <pluginGroup>com.whiteskylabs.muledeployment.goals</pluginGroup>
                 </pluginGroups>
2. Do mvn install from the location of ‘mule-deployment-plugin’ plugin. So that, plugin get installed on maven local repository.
3. Place all your mule applications (.zip files need to be deployed) in a directory of local system and set this directory location to “muleApplicationsSourceDirectory” key in the XXXXDeployment.properties file.
4. Configure target Mule server (MMC or Standalone) details and other configurations in XXXXDeployment.properties file. (Described each property below and sample deployment configuration properties files are available under 'mule-deployment-plugin/properties' directory). 
5. Pass the absolute file path of the properties file as a parameter while executing the maven command.
6. Execute the Maven command
          Maven command for MMC:       mvn wsldeploy:mmc -DpropertiesFilePath=G:\mulesoft\MuleAppDeployment\MMCDeployment.properties
          Maven command for Mule Standalone server:  mvn wsldeploy:standalone -DpropertiesFilePath=G:\mulesoft\MuleAppDeployment\StandaloneDeployment.properties
          Maven command for MMC cluster:  mvn wsldeploy:cluster -DpropertiesFilePath=G:\mulesoft\MuleAppDeployment\MMCDeployment.properties

Resources
=========

Here's a list of features used in this demo with a link to their documentation

●     [Mule Expression Language](http://www.mulesoft.org/documentation/display/MULE3USER/Mule+Expression+Language)  
●     [Configuring Endpoints](http://www.mulesoft.org/documentation/display/MULE3USER/Configuring+Endpoints)  
●     [Studio transformers](http://www.mulesoft.org/documentation/display/MULE3STUDIO/Studio+Transformers)  
●     [Flow references](http://www.mulesoft.org/documentation/display/MULE3STUDIO/Flow+Ref+Component+Reference)
 

Webinars and additional documentation related to Mule ESB can be found under [Resources](http://www.mulesoft.com/resources) menu option.
