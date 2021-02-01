# Introduction 
This is a Vagrant file and an ansible playbook to run FreeIPA server on VirtualHost environment.
Based on [post from the internet](https://medium.com/netdef/using-vagrants-ansible-provisioner-to-build-a-freeipa-server-1007fbafd595) and on [official FreeIPA ansible playbook](https://github.com/freeipa/ansible-freeipa.git).

# Dependencies
- vagrant have to be installed on host (have been tested on version 2.2.14).
- ansible have to be installed on host (have been tested on version 2.9.6).
- Future VM have to be reachable from host by FQDN (by default - test.my.domain)

# Build and Test
Just run `vagrant up` to build the VM.
To connect enter the Web-UI (https://test.my.domain).
- username: admin
- password: password

# Update
To update the playbook:
- Clone the latest version of the playbook.
  - For example: `git clone --branch v0.3.4 https://github.com/freeipa/ansible-freeipa.git`
- Copy `roles` folder to provisioning.
  - `cp -r ansible-freeipa/roles provisioning/`
- Run new VM
  - `vagrant up`
