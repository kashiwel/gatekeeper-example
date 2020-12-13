# 概要

Qiitaの

# 試し方

```
$ kind create cluster
$ kubectl apply -f https://raw.githubusercontent.com/open-policy-agent/gatekeeper/release-3.1/deploy/gatekeeper.yaml
$ kubectl apply -f manifests/gatekeeper-system/base/constrainttemplate.yaml
$ kubectl apply -k manifests/gatekeeper-system/overlays/production
```