# Ansible config

# Install
First, you have to clone this repo. Then, you will have to enter the following command because you need to install some roles specifies in the file `requierements.yml`:
```
$ ansible-galaxy install -r requirements.yml
```

Run `ansible-playbooks file.yml`, execute the defined tasks on the targeted hosts.

Check mode (`--check`) is just a simulation. It will not generate output for tasks. When you run in diff (`--diff`) mode, any module that supports diff mode reports the changes made or, if used with --check, the changes that would have been made.

```
$ ansible-playbook --check --diff playbooks/config.yml

```
# ZeroTier controller (central server)

The ZeroTier controller works with ZeroUI which implements the following features:
- A better user experience.
- ZeroUI has an API that is compatible with ZeroTier Central. This means you can use CLI tools and custom applications designed only for ZeroTier Central to manage your networks.
- ZeroUI implements controller-specific workarounds that solve some existing problems.

Install : https://github.com/m4rcu5nl/ansible-role-zerotier

# Zerotier (other server)

The Ansible role used adds the ZeroTier repository and installs the `zerotier-one` package using the package manager on your system. Depending on the variables provided, this role can also add and authorize new members to (existing) ZeroTier networks, and tell the new member to join the network.

Install : https://github.com/dec0dOS/zero-ui

# Kubernetes

Once the deployment of kubernetes is done with Ansible, you will have to run the following command on your local machine. This will allow you to access the cluster directly from your machine without having to go through the server.

```
$ ssh ubuntu@152.228.211.254 "mkdir -p ~/.kube && sudo cp /etc/rancher/k3s/k3s.yaml ~/.kube/config && sudo chown ubuntu:ubuntu ~/.kube/config" && mkdir -p ~/.kube && scp ubuntu@152.228.211.254:~/.kube/config ~/.kube/config
```
To use the kubernetes command line tool, kubectl, which allows you to run commands in Kubernetes clusters. You will have to install it with the following command:

```
$ apt-get install kubectl
```
