`minikube start --nodes=3`
`minikube addons enable ingress`


https://www.elastic.co/guide/en/cloud-on-k8s/current/k8s-deploy-eck.html

Install custom resource definitions and the operator with its RBAC rules:

`kubectl apply -f https://download.elastic.co/downloads/eck/1.5.0/all-in-one.yaml`

Monitor the operator logs:

`kubectl -n elastic-system logs -f statefulset.apps/elastic-operator`

`kubectl get elasticsearch`

`kubectl get service quickstart-es-http`

`PASSWORD=$(kubectl get secret elasticsearch-es-elastic-user -o go-template='{{.data.elastic | base64decode}}') && echo $PASSWORD`

kubectl port-forward service/quickstart-es-http 9200
kubectl port-forward service/quickstart-es-http 9200

kubectl expose service kibana-kb-http --port=5601 --target-port=5601 --name=kibana-web --type=NodePort
kubectl expose service tb-web-ui --port=5601 --target-port=5601 --name=kibana-web --type=NodePort

minikube service kibana-web --url

curl -u "elastic:$PASSWORD" -k "https://quickstart-es-http:9200"

elastic
25Q9l7zOsT64i6B6oV1mX9CD

FILEBEAT

https://www.elastic.co/guide/en/beats/filebeat/7.12/running-on-kubernetes.html


