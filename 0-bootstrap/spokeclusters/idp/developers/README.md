# README


## Strategy
Reconciliation strategy:

1) Initially, my strategy for adding resources to a cluster was to have the subscription pointing to a “kustomization.yaml” file where the Kustomization file lists a bunch of resources as per the file snapshot given below
2) The plan was to append to this kustomization file the newly added resource(s) in question as [such](https://stackoverflow.com/questions/68753205/how-to-add-a-list-item-in-yq-version-4)
3) Following that copy the actual resource YAML and git push 

This DID NOT work. I need to investigate why.

```
apiVersion: v1
kind: Namespace
metadata:
  name: one

---

apiVersion: v1
kind: Namespace
metadata:
  name: two

---
apiVersion: v1
kind: Namespace
metadata:
  name: three
```

## Fallback

The fallback plan was to have a base YAML and append resources via echoes where necessary putting a seperator where necessary. This is NOT good over the long term, and this needs to be rectified at some point.

