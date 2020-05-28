# anisble_inventory

Create an Ansible Inventory with groups derived from host names

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
        name: anisble_inventory
      vars:
        ar_inv_hostname_machines: "{{ server_hostname_list }}"
        ar_inv_hostname_dest_dir: "{{ dest_directory }}"
```
