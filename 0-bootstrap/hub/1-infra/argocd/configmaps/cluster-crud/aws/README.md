# README


This points to a configmap in the infra repository. This configmap contains configs required to populate the YAML's as part of the cluster crud tekton pipeline. There has to be some sort of mapping from the user input to the actual fields understood by Hive/OCM. A key value store is the best use case for this. May as well use K8's configmaps for this.