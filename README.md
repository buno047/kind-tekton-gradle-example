# Tekton Pipeline example with Gradle 

This project is example how to migrate from jenkins pipelines to the cloud native tekton CD using gradle

## Why Tekton pipelines

- GitOps
- Cloud native
- Industry Standard 
- Task Encapsulation

## Reusable Tasks Catalog

- https://github.com/tektoncd/catalog
- https://github.com/open-toolchain/tekton-catalog

## What is Included

- all tools as docker image ```docker exec -it dev-tools zsh``` 
- gradle one click scripts to bootstrap local k8s cluster with Kind https://kind.sigs.k8s.io
- latest Tekton pipelines and triggers with dashboard

- Dashboard v0.8.2  http://localhost:8080/#/about
- Pipelines v0.15.1
- Triggers  v0.7.0

![alt text](https://github.com/dimetron/kind-tekton-gradle-example/raw/master/docs/k9s.png "k9s")

## Requirements 

All tools baked inside Docker image 
https://github.com/dimetron/kind-tekton-gradle-example/blob/master/tools/Dockerfile

- IDE VS Code or IntelliJ (alternative gradlew CLI)
- Docker Desktop with 6 GB RAM and shared drive

![alt text](https://github.com/dimetron/kind-tekton-gradle-example/raw/master/docs/docker.png "Docker")

## Creating k8s cluster

Gradle default task `all-tasks` will do 

- setup local cluster
- deploy tekton using [kapp](https://get-kapp.io)
- deploy tasks and pipelines
- execute pipeline using tekton pipeline-run

```./gradlew```

## Open Dashboard k9s 

```docker exec -it dev-tools k9s```

## Using Tekton command line

```
docker exec -it dev-tools zsh
tkn task list
```

## Tekton Dashboard 

As part of demo repository dashboard installed with [ingress](http://localhost:8080/#/pipelineruns)

![alt text](https://github.com/dimetron/kind-tekton-gradle-example/raw/master/docs/tekton-dashboard.png "Dashboard")

## Using Tekton Plugin VS Code / IntelliJ

VS Code:
![alt text](https://github.com/dimetron/kind-tekton-gradle-example/raw/master/docs/vs-code-tekton.png "VSCode plugin")

IntelliJ:
![alt text](https://github.com/dimetron/kind-tekton-gradle-example/raw/master/docs/intellij-tekton.png "IDEA plugin")

## References:

- https://tekton.dev/docs/
- https://tekton.dev/docs/triggers/

- https://github.com/tektoncd/triggers/tree/master/examples/bitbucket
- https://github.com/tektoncd/triggers/tree/master/examples/gitlab

Tutorials:
- https://cloud.ibm.com/docs/ContinuousDelivery?topic=ContinuousDelivery-tekton-pipelines
- https://developer.ibm.com/technologies/devops/tutorials/build-and-deploy-a-docker-image-on-kubernetes-using-tekton-pipelines/#create-a-task-to-build-an-image-and-push-it-to-a-container-registry
- https://developer.ibm.com/tutorials/tekton-triggers-101/

## Troubleshooting

in case of issues delete docker container ```docker rm -f dev-tools``` and run Gradle ```./gradlew``` again