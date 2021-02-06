# infra

To my future self: Just follow this guide to set up your servers.

## First steps

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

### Install k3s

Install k3sup locally via `brew install k3sup`

Add the new server and run `scripts/bootstrap_k3s.sh` 