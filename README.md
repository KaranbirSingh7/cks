# cks

Course Preparation: https://killer.sh/r?d=cks-course

### aliases

```shell
# set alias or export following
export do="--dry-run=client -oyaml"
export now="--grace-period 0 --force"

# time savers
kubectl config set-context --current --namespace $NAMESPACE

# recreate all secrets inside a k8s cluster, useful when setting up an etcd encryptionConfig
kubectl get secrets -A -o json | kubectl replace -f -

# read a secret and decode on fly
kubectl -n $NAMESPACE get secrets $SECRET -ojsonpath="{.data.creditcard}" | base64 -d 

# STATIC Analyze YAML
# if kubesec isn't installed on machine, use/set below alias
# USAGE: kubesec < pod-spec.yaml
alias kubesec="docker run -i kubesec/kubesec:512c5e0 scan /dev/stdin"
```

- [ ] TODO upload notes from _roam research_

References:
- https://github.com/walidshaari/Certified-Kubernetes-Security-Specialist
- https://github.com/ascode-com/wiki/tree/main/certified-kubernetes-administrator
