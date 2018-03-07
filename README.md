# nondeterministic-charts

Example chart for demonstrating nondeterministic `helm package` for [https://github.com/kubernetes/helm/issues/3612]().

```bash
# working dir: parent
$ helm dep update
$ for i in {1..1000}; do helm package . && sha256sum parent-1.0.0.tgz && rm parent-1.0.0.tgz; done
```

