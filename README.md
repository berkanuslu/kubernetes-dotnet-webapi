# .NET Core 3.1 Web API Sample for Docker and Kubernetes

You can create a new Web API Sample with new command of dotnet CLI.

You can show all possible options with --help parameter.

    dotnet new --help

Create a folder and change directory in this folder.

    mkdir kubernetesdotnetwebapi
    cd kubernetesdotnetwebapi

Now you can create a new Web API project just write this command below.

    dotnet new webapi

.NET CLI is created all your need for Web API project with sample controller. Then you can build and run the application on http://localhost:5000 or https://localhost:5001 addresses.

    dotnet build
    dotnet run

## .NET Web API App on Docker

You can build an image of your application with Dockerfile in this repo. Then you can build with this command below.

    docker build --rm -f "Dockerfile" -t DOCKER_HUB_USERNAME/kubernetesdotnetwebapi:latest "."

After build process, you have an image for your app. You can run with this command below with port mapping.

    docker run -p 8080:80 berkanuslu/kubernetesdotnetwebapi

## .NET Web API App on Kubernetes

You can deploy your docker image on Kubernetes with deploy.yaml file in this repo. Then you can create this deployment with this command below.

    kubectl create -f deploy.yaml

You can see all your app logs from kubectl logs. First of all, you need the name of your pod.

    kubectl get pods

This command above has a list about your Kubernetes configuration and you see your pod name. Then with logs command, you can see all your current pod's log in your terminal screen.

    kubectl logs -f kubernetes-dotnet-webapi-7877ff4cf7-s49lk

## Versions

.NET 3.1.2
Docker version 19.03.8, build afacb8b
kubectl v1.15.5

Happy coding!
April 2020
