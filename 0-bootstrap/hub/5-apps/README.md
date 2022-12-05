# README - Apps


## Crossplane

Behaviour that was noticed:

ArgoCD uses a label to indicate ownership of a Kubernetes resource to an application. Any resource with this label that is not deployed as part of ArgoCD could be deleted as part of the next application sync. Composite Resource Claim (XRC) automatically propagate all labels and annotations to their Composite Resource (XR), this causes ArgoCD to pick up ownership of the XR and desire deletion.

This is no good. The way around (and I am not proud of this) was to add the XRD Api Group to the deny list of this AppProject. Refer to the "5-apps".yaml and look for "clusterResourceBlacklist".

The actions recommended in the following issues coincide with this "hacky" solution:

1) https://github.com/crossplane/crossplane/issues/2000
2) https://github.com/crossplane/crossplane/issues/2121

## Action points

1) Find a better workaround to the above.


## Additional Resources

1) https://argo-cd.readthedocs.io/en/stable/user-guide/compare-options/
2) https://argo-cd.readthedocs.io/en/stable/user-guide/sync-options/

Perhaps we can make use of ignoring extraneous resources as provided in the first link of this section. This warrants some investigation.