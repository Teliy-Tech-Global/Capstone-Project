## Introduction

- In today’s software development world, delivering high-quality applications quickly and reliably is paramount. To achieve this, organizations are increasingly adopting Continuous Integration and Continuous Deployment (CI/CD) pipelines. These pipelines automate the building, testing, and deployment phases, enabling developers to streamline their workflows and deliver software with efficiency and consistency.

## Overview of Jenkins:

- Jenkins is an open-source automation server widely used for building, testing, and deploying software applications. It provides a wide range of plugins and integrations, making it highly customizable and suitable for various programming languages and technologies. Jenkins enables developers to automate repetitive tasks, collaborate with teams, and establish robust CI/CD pipelines.

## Prerequisites:

- Here I will be deploying the application on the same node where jenkins is running so here are few things make sure are installed on your server.

1. Docker & docker-compose

2. Git

3. Give permissions to Jenkins to run docker using below command

`sudo usermod -a -G docker jenkins`

![Alt text](./images/permssion.PNG)

## Next install github-integration plugin in jenkins.

- Go to Manage Jenkins > Plugins > Available Plugins. Search for github integration and click on install without restart. Once done check whether it is enabled or not by navigating into installed plugins.

![](./images/integration.PNG)

## Go to your repository setting add webhook to trigger jenkins.

- It should appear like this once webhook is added.
  ![](./images/webhook.PNG)
  ![](./images/success.PNG)

## Go to Jenkins > create a new Freestyle Project and configure the job.

- Under General check the github project and add the github url

![](./images/github-url.PNG)

- Select git in source code management, add github url and add main in branches to build.

- Select GitHub hook trigger for GITScm polling under build trigger.
  ![](./images/build.PNG)

- Select execute shell in build steps and docker-compose commands.

## Click on apply and save. As everything is done now make changes in repository and it will automatically trigger your jenkins job.

![](./images)
![](./images/pipeline.PNG)

## Conclusion:

Congratulations 🎉, you have successfully created jenkins CICD pipeline to deploy your nodejs application which will be triggered via webhook when any developer pushes new code in github repository.
