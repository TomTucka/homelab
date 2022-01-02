# Installing Kubernetes

!!! info "Update Ansible inventory configuration and run the `k3s-install` playbook"

Running a multi-master cluster with embedded etcd

Create the first server
```sh
k3sup install \
  --ip <ip> \
  --user <user> \
  --ssh-key ~/.ssh/<key> \
  --context homelab \
  --local-path ~/.kube/config \
  --merge \
  --cluster \
  --k3s-version v1.22.5+k3s1 \
  --k3s-extra-args '--disable traefik --disable servicelb --disable metrics-server –flannel-backend=none' \
```

Join more servers

```sh
k3sup join \
  --ip <ip> \
  --user <user> \
  --ssh-key ~/.ssh/homelab \
  --server \
  --server-user <server_user> \
  --server-ip <server_ip> \
  --k3s-version v1.22.5+k3s1 \
  --k3s-extra-args '--disable traefik --disable servicelb --disable metrics-server –flannel-backend=none'
```

Join some other nodes
```sh
k3sup join \
  --ip <ip> \
  --user <user> \
  --ssh-key ~/.ssh/homelab \
  --server-ip <server_ip> \
  --k3s-version v1.22.5+k3s1 \
  --k3s-extra-args '--disable traefik --disable servicelb --disable metrics-server –flannel-backend=none'
```
