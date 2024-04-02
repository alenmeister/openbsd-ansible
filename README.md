# Ansible playbook for OpenBSD

This playbook upgrades OpenBSD hosts to the next stable release, installs binary\
patches and updates all packages to the latest version. 

## Requirements
The following requirements apply for each host:
1. Latest version of Python installed
2. Your public SSH key is added to the `authorized_keys` file
3. Configuraton file for doas(1) is present

## Usage
```sh
# Run all tasks on all hosts
ansible-playbook playbook.yaml

# Run all tasks on a subset of hosts
ansible-playbook playbook.yaml -l vm1

# Run a set of tasks on all hosts
ansible-playbook playbook.yaml -t syspatch,syspatch_debug,syspatch_reboot
```

## Tags
All tasks are tagged with an appropriate name for ease of use (see above usage example).\
This way, you can easily run any task(s) based on your needs on any host(s).

To list all defined tags, run: `ansible-playbook playbook.yaml --list-tags`
