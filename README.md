# ar_inv_hostname

Create an Ansible Inventory with groups derived from host names
For the ansible inventory, server hostnames are processed using a '-' 
delimiter and associated groups are defined, e.g
dc1-os-node-1 would result in the following groups:
- dc1             Contains all hosts with 'dc1'
- dc1_os          Contains all hosts with 'dc1-os'
- dc1_os_node     Contains all hosts with 'dc1-os-node'
- dc1_os_node_1   Contains only the host 'dc1-os-node-1'

## Requirements

## Role Variables
The following details:
- the parameters that should be passed to the role (aka vars)
- the defaults that are held
- the secrets that should generally be sourced from an ansible vault.

### Parameters:

Mandatory variables:

| Variable                 | Description                                   | Default |
| --------                 | -----------                                   | ------- |
| ar_inv_hostname_machines | List of hostnames to include in the inventory | None    |
| ar_inv_hostname_dest_dir | Directory in which to create the inventory    | None    |


### Defaults
| Variable | Description | Default |
| -------- | ----------- | ------- |


### Secrets
The following variables should be provided through an encrypted source:

## Example Playbook

```
- hosts: localhost
  tasks:
    - name: Generate AWS Infra
      include_role:
        name: ar_inv_hostname
      vars:
        ar_inv_hostname_machines: "{{ server_hostname_list }}"
        ar_inv_hostname_dest_dir: "{{ dest_directory }}"
```
