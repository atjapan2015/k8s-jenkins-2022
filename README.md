
```
kubectl create ns jenkins
kubectl apply -f jenkins.yaml
kubectl apply -f jenkins-service.yaml
kubectl -n jenkins exec -it $(kubectl -n jenkins get pods --selector=app=jenkins -o jsonpath='{.items..metadata.name}') -it -- bin/bash
---
cat /var/jenkins_home/secrets/initialAdminPassword
---

or

kubectl -n jenkins exec -it $(kubectl -n jenkins get pods --selector=app=jenkins -o jsonpath='{.items..metadata.name}') -it -- cat /var/jenkins_home/secrets/initialAdminPassword

```

config /etc/hosts
```
xxx.xxx.xxx.xxx jenkins.myserver.site
```
