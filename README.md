# tls-lets-encrypt-kubernetes-job
A Kubernetes Job docker image that generates necessary Let's Encrypt certificates
and adds them to their corresponding Secrets in Kubernetes.

The idea of this is to be passed a ConfigMap of virtual host domains (a.example.com, b.example.com, etc.), and a corresponging secret name for each of these, i.e.
```
a.example.com -> a-tls-cert
b.example.com -> b-tls-cert
...
```

Given this information, whenever this container is run,
it will download and launch the certbot from Let's Encrypt,
run a challenge, obtain a certificate for each of the subdomains,
and then overwrite the given secret with that certificate,
thus updating/refreshing the TLS certificate for each of the given domains.
Automatically.
So you don't have to worry about it.

# How to run

TBD
