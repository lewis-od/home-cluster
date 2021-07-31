# k3s
Ansible playbook to install k3s on raspberry pi

## Instructions
- Flash fresh version of Raspbian onto the pi
- Setup networking & sshd
  - `sudo raspi-config`
- Setup a static IP
  - `sudo vim /etc/dhcpcd.conf`
- Setup passwordless ssh
  - `ssh-copy-id pi@192.168.1.150`
- Run playbook to install k3s
  - `ansible-playbook site.yml -i inventory/hosts.ini`
- Copy kubeconfig file from pi
  - `scp pi@192.168.1.150 ~/.kube/config ./config-pi.yml`
