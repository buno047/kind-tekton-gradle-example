# Tekton Pipeline example with Gradle 

This project is example how to migrate legacy groovy jenkins pipelines to the cloud native tekton CD 

## Requirements 

- Docker Desktop
- kubectl
- tkn 

## Creating k8s cluster and 

Gradle default task `all-tasks` will do 

- setup local cluster
- deploy tekton
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

As part of demo repository dashboard installed with ingress http://localhost:8080/tekton-dashboard/

## Using Tekton Plugin VS Code / IntelliJ

VS Code:
![alt text](https://github.com/dimetron/kind-tekton-gradle-example/raw/master/docs/vs-code-tekton.png "VSCode plugin")


## References:

- https://tekton.dev/docs/
- https://tekton.dev/docs/triggers/

- https://github.com/tektoncd/triggers/tree/master/examples/bitbucket
- https://github.com/tektoncd/triggers/tree/master/examples/gitlab

Tutorials:

- https://developer.ibm.com/technologies/devops/tutorials/build-and-deploy-a-docker-image-on-kubernetes-using-tekton-pipelines/#create-a-task-to-build-an-image-and-push-it-to-a-container-registry
- https://developer.ibm.com/tutorials/tekton-triggers-101/


## Troubleshooting

in case of issues run Gradle again
