```
$ kind create cluster

$ kubectl apply -f https://raw.githubusercontent.com/open-policy-agent/gatekeeper/release-3.1/deploy/gatekeeper.yaml
$ kubectl apply -f manifests/gatekeeper-system/base/constrainttemplate.yaml
$ kubectl apply -k manifests/gatekeeper-system/overlays/production

$ kubectl apply -k manifests/default/app1/overlays/staging/
Error from server ([denied by deny-deployment] expected: production, actual: staging): error when creating "manifests/default/app1/overlays/staging/": admission webhook "validation.gatekeeper.sh" denied the request: [denied by deny-deployment] expected: production, actual: staging

$ kubectl apply -k manifests/default/app1/overlays/production/
deployment.apps/echoserver created
```