<div align="center">

<img src="https://camo.githubusercontent.com/5b298bf6b0596795602bd771c5bddbb963e83e0f/68747470733a2f2f692e696d6775722e636f6d2f7031527a586a512e706e67" align="center" width="144px" height="144px"/>

### Homelab Configuration :sailboat:

_... managed with Flux and Renovate_ :robot:

</div>


---

## :book:&nbsp; Overview

This is home to my homelab configuration. For Kubernetes, [Flux](https://github.com/fluxcd/flux2) watches this Git repository and makes the changes to my cluster based on the manifests in the [cluster](./cluster/) directory. [Renovate](https://github.com/renovatebot/renovate) also watches this Git repository and creates pull requests when it finds updates to Docker images, Helm charts, and other dependencies.


## :file_cabinet: Hardware

This cluster runs on the following hardware:

| Device                  | Count | OS Disk Size | Data Disk Size       | Ram  | Purpose                       |
|-------------------------|-------|--------------|----------------------|------|-------------------------------|
| RaspberryPi 4           | 16    | 500gb        |                      | 4GB  | k3s                           |
| Dell R720               | 1     | 3tb          | 18tb                 | 48GB | Esxi                          |

## :handshake:&nbsp; Community

Thanks to all the people who donate their time to the [Kubernetes @Home](https://github.com/k8s-at-home/) community.
