# Home Cluster

This repository _is_ my home Kubernetes cluster in a declarative state. [Flux](https://github.com/fluxcd/flux2) watches my [cluster](./cluster/) folder and makes the changes to my cluster based on the YAML manifests.

This repository is built off the [k8s-at-home/template-cluster-k3s](https://github.com/k8s-at-home/template-cluster-k3s) repository.

## Cluster setup

My cluster is [k3s](https://k3s.io/) provisioned overtop Raspbian Lite using the [K3Sup]()

## Cluster components


- [cert-manager](https://cert-manager.io/docs/): Configured to create TLS certs for all ingress services automatically using LetsEncrypt.

## Repository structure

The Git repository contains the following directories under `cluster` and are ordered below by how Flux will apply them.

- **base** directory is the entrypoint to Flux
- **crds** directory contains custom resource definitions (CRDs) that need to exist globally in your cluster before anything else exists
- **core** directory (depends on **crds**) are important infrastructure applications (grouped by namespace) that should never be pruned by Flux
- **apps** directory (depends on **core**) is where your common applications (grouped by namespace) could be placed, Flux will prune resources here if they are not tracked by Git anymore

```
./cluster
├── ./apps
├── ./base
├── ./core
└── ./crds
```

## Tools

| Tool                                                   | Purpose                                                      |
| ------------------------------------------------------ | ------------------------------------------------------------ |
| [direnv](https://github.com/direnv/direnv)             | Sets environment variable based on present working directory |
| [go-task](https://github.com/go-task/task)             | Makefiles except in YAML                                     |
| [pre-commit](https://github.com/pre-commit/pre-commit) | Enforce code consistency and verifies no secrets are pushed  |
| [stern](https://github.com/stern/stern)                | Tail logs in Kubernetes                                      |

## Thanks

A lot of inspiration for my cluster came from the people that have shared their clusters over at [awesome-home-kubernetes](https://github.com/k8s-at-home/awesome-home-kubernetes)
