# Debian installer

My Debian i3 installer
---
Compatible with Debian 12 and versions later
---

### When installed on host
First we need add user to sudoers

```bash
su -
```

Next we need add user to sudoers. Please change name_of_user to your username

```bash
apt update && apt install sudo -y && usermod -aG sudo name_of_user
```

```bash
sudo apt update \
&& sudo DEBIAN_FRONTEND=noninteractive apt full-upgrade -y \
&& sudo DEBIAN_FRONTEND=noninteractive apt install ansible -y \
&& mkdir -p ~/.gc \
&& cd ~/.gc \
&& git clone https://github.com/pietryszak/ubuntu-installer \
&& cd ubuntu-installer \
&& ansible-playbook --ask-become-pass --connection=local --inventory 127.0.0.1, all.yml host.yml
```