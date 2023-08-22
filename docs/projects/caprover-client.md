---
layout: default
title: Caprover client
parent: Projects
nav_order: 5
---
# Caprover client
The goal of this project is to create a client for caprover that can be used to deploy docker containers to caprover without having to publish the docker image to a container registry first.

## Problem
Currently, there are three ways you can deploy your application from Github to Caprover:
1. the [Deploy Github repo to Caprover](https://github.com/marketplace/actions/deploy-github-repo-to-caprover) Github Action.
It requires you to either build a `.tar` file or publish the docker image to a container registry first, then you can update the Caprover app.  
2. Build your own workflow using the [Caprover CLI](https://caprover.com/docs/cli-commands.html) to publish the app. This solution, however, does not verify if the build of the docker image or if the deployment itself went well.
3. 

If you want to build the docker image on your Caprover server, using the (Caprover CLI)[https://caprover.com/docs/cli-commands.html], there is no way to determine if the deployment succeeded, as the commands succeeds immediately after the build is started.

## Solution
Since the Caprover CLI allows us to use other API methods as well, we will build a script that pulls information about the application to be built, so that we can make sure the application is updated.



