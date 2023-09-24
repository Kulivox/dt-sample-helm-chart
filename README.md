# dt-sample-helm-chart
Repository containing a proof of concept helm chart.

The deployment can be tested by port forwarding service `web-app` by using following command:

`kubectl port-forward -n <namespace> service/web-app 9099:9099`

## CD tool integrations

### Flux
The repository also contains configuration for flux. All that needs to be done to bootstrap this configuration is to run:
```
flux bootstrap github \
  --owner=<USER NAME> \
  --repository=dt-sample-helm-chart \
  --branch=master \
  --path=./flux/prod \
  --personal
```
### ArgoCD
ArgoCD setup is a bit more complicated, but it seems to be easier to maintain. You have to add ArgoCD to your cluster manually, apply the kubernetes manifests in the `argocd/` directory and the ArgoCD will take care of the rest of the deployment.
