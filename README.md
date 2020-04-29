# Ansible role to install and restore prometheus alertmanager
This repository installes and configs alertmanager

## Usage
```bash
ansible-playbook -i inventory alertmanager.yml
```

## Test
You can use vagrant to install this role on both ubuntu and centos:
`vagrant up`

## Tags
- `update_alertmanager_conf`: Update the `alertmanager.yml` file.

## Variables
- `alertmanager_version`: The version of alertmanager to be installed.
- `alertmanager_external_address`: The external address which alertmanager is accessible through (HTTP or HTTPS).