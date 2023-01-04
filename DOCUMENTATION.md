# Dokumentation

## Authenticate cluster access
- go to cluster in google cloud, press the three dots on the right of the cluster and click "Connect". Copy the given command into your command line ;)

---
## Task Tutorial 
https://tekton.dev/docs/getting-started/pipelines/

### Install tekton on cluster
`kubectl apply --filename https://storage.googleapis.com/tekton-releases/pipeline/latest/release.yaml`

### Apply hello world task to cluster
`kubectl apply --filename hello-world.yaml`

output:
`task.tekton.dev/hello created`

### Apply task run
`kubectl apply --filename hello-world-run.yaml`

output: 
`taskrun.tekton.dev/hello-task-run created`

### Verify that it worked
`kubectl get taskrun hello-task-run`

output: 
```
NAME             SUCCEEDED   REASON      STARTTIME   COMPLETIONTIME
hello-task-run   True        Succeeded   2m40s       2m30s
```

### Take a look at the logs
`kubectl logs --selector=tekton.dev/taskRun=hello-task-run`

Displays: `Hello World`

## Pipelines Tutorial
https://tekton.dev/docs/getting-started/pipelines/

### Install tkn 
https://tekton.dev/docs/cli/

### TODO not tested waiting for https://github.com/tektoncd/pipeline/issues/5932
```
  # Install Tasks from the Catalog
  tkn hub install task git-clone
  tkn hub install task golang-test
  tkn hub install task golangci-lint
  tkn hub install task golang-build

  # Install Golang Run Task 
  kubectl apply -f tekton/golang-run.yaml

  # Install the Pipeline
  kubectl apply -f tekton/pipeline.yaml

  # Make the Persistent Volume Claim that we'll be using 
  kubectl apply -f tekton/workspace.yaml
  
  # Execute Pipeline run
  kubectl apply -f tekton/pipeline-run.yaml
  
  tkn pipelinerun ls
  tkn pipelinerun describe -L
  tkn taskrun describe <taskRunName>
  kubectl describe tr <taskRunName>
  kubectl get -o yaml pod <podName> | less
```
---

TODO: 

- [ ] Test pipeline run like on https://github.com/jerop/tekton-demo, does not work yet: https://github.com/tektoncd/pipeline/issues/5932
- [x] Create a pipeline run file
- [ ] Test pipeline run!
- [ ] Create triggers
- [ ] Test if works with pushes that staging is deployed
- [ ] Change go to java project - golang-run to java-run
- [ ] Implement GitHub Action to Trigger release after time period
- [ ] Implement pipeline for production env.
