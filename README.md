# dt-sample-helm-chart
Repository containing a proof of concept helm chart.

The deployment can be tested by port forwarding service `web-app` by using following command:

`kubectl port-forward -n <namespace> service/web-app 9099:9099`
