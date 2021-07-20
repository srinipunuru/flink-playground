# Steps to create the flink cluster that uses abfs for storing checkpoint, savepoint and JobManager HA state 
```
kubectl create clusterrolebinding flink-role-binding-default --clusterrole=edit --serviceaccount=default:default

# apply flink config map
kubectl apply -f flink-configuration-configmap.yaml

# create job manager service
kubectl apply -f jobmanager-service.yaml

# create Job manager deployment
kubectl apply -f jobmanager-session-deployment.yaml

# create Task manager deployment
kubectl apply -f taskmanager-session-deployment.yaml
```