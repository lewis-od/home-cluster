# Home Cluster
Configuration-as-Code for deploying [k3s] & [tailscale] to a raspberry pi, along
with k8s manifests for [Home Assistant] and [Pi-hole]

[k3s]: https://k3s.io/
[tailscale]: https://tailscale.com/
[Home Assistant]: https://www.home-assistant.io/
[Pi-hole]: https://pi-hole.net/

## Components
- [ansible/](ansible) - Ansible playbook to deply k3s and tailscale
- [k8s/](k8s) - Kubernetes manifests for Home Assistant and Pi-hole

## Instructions
Follow the instructions in [ansible/](ansible/README.md), then run
`kubectl apply -k k8s`
