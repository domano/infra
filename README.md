# infra

To my future self: Just follow this guide to set up your servers.

# Initial setup

## SSH
### Copy public key
Copy ssh public keys to your new server.

Install `ssh-copy-id` if not available.

`ssh-copy-id root@host`

### Disable password login

`ssh root@host`

In `/etc/ssh/sshd_config` uncomment the following line
`#PasswordAuthentication no`

Restart ssh via
`service ssh restart`

## Updates

### Autoupdate

## Install unattended-upgrades
Install `sudo apt-get install unattended-upgrades` for automatic upgrades. If already installed configure via `sudo dpkg-reconfigure -plow unattended-upgrades` and enable updates.

## Configure unattended-upgrades
Overwrite the content of `/etc/apt/apt.config.d/50unattended-upgraded` with the [provided file](config/50unattended-upgrades) 


## Install k3s and join the cluster

Install k3sup locally via `brew install k3sup`

Add the new server and run `scripts/bootstrap_k3s.sh` 