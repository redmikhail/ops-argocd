# Physical Risk Sandbox Deployment artifacts

This repository includes all required manifests to deploy Physical Risk Sandbox application. Manifests are structured to be used with `kustomize` tool from Kubernetes community (https://kubernetes.io/docs/tasks/manage-kubernetes-objects/kustomization/) in form of the overlays. Kustomize is embedded as part of the `kubectl` kubernetes cli tool (or `oc` client if OpenShift is being used). 

To apply deployment:
* Login to OpenShift cluster using os/kubectl tools (we will use `oc` for all command examples futher in the text but commands or format will be the same for `kubectl`) 
* Navigate to directory _kustomize/overlays/osc-cl2_ 
```
cd kustomize/overlays/osc-cl2
```
* Execute 
```
oc apply -k .
```

To generate all deployment artifacts without applying them to the target cluster use
```
oc kustomize . 
```

If needed manifests can be applied individually from _kustomize/base_ directory. Please note that in this case you may need to create secrets and configmap objects manually (kustomize takes care of generation of the configmaps) using configmaps-example, secrets-example as an examples.