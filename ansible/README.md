# k3s
Ansible playbook to install [k3s] & [tailscale] on a raspberry pi

[k3s]: https://k3s.io/
[tailscale]: https://tailscale.com

## Instructions
- Flash fresh version of Raspbian onto the pi
- Setup networking & sshd
  - On pi: `sudo raspi-config`
- Setup a static IP
  - On pi: `sudo vim /etc/dhcpcd.conf`
- Setup Ansible inventory
  - On laptop: `cp inventory/hosts.ini.example inventory/hosts.ini`
  - Replace `192.168.1.150` with static IP of pi
- Setup passwordless ssh
  - On laptop: `ssh-copy-id pi@192.168.1.150`
- Run playbook to install k3s
  - On laptop: `ansible-playbook site.yml -i inventory/hosts.ini`
- Copy kubeconfig file from pi
  - On laptop: `scp pi@192.168.1.150 ~/.kube/config ./config-pi.yml`
- Sign in to tailscale:
  - On pi: `sudo tailscale up --advertise-exit-node`
