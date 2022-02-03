# Ansible config

# Install

To use an existing role on https://galaxy.ansible.com/, you have to modify the `requirements.yml` file with the role name and the desired version. Once this modification is done, you will have to enter the following command to install the role:
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
