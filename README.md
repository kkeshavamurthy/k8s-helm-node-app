# k8s-helm-node-app
This is a helm chart that displays a webpage with the number of visits. 

## Installing and running the chart

* Dependencies:
This chart has a dependency of Mariadb. 

This will add the repo URL to repo list and then download the repo to the charts directory
```
helm repo add k8s-helm-charts https://kubernetes-charts.storage.googleapis.com
helm dependency update
```
* Installing the helm chart
```
helm install helm-node-app/
```
Untill db pod is up and running, the node pod might crash. But, will stabilize once the db is up and running. 

* Deleting the chart
```
helm delete <RELEASE_NAME> --purge
```
This will delete the db volumes as well and hence all data will be lost. Do not use the --purge flag if you need to preserve the data

* Debugging the chart
To make sure everything is correct, you can dry-run the chart before deploying it to kubernetes. This will help in catching some errors before deployment. Note that passing of dry-run does not guarentee that k8s will accept the chart without errors. 
```
helm install node-helm-app/ --dry-run --debug
```

