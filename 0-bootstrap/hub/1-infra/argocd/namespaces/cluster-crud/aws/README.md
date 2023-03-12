# README

This namespace will house resources necessary to support the creation of clusters, namely the following:

1) Secret containing the RH pull secret, cloud provider credentials and the SSH keys.
2) ConfigMap containing configurations required to populate the YAML's as per the user input from Backstage, or any other platform really.

The configmaps directory within the infra AppProject and repository houses the aforementioned configmap.

Secret deployment via ExternalSecrets is done on the Clusters App Project.