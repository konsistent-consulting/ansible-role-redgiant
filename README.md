# Ansible Role: Red Giant

Ansible role for installing Red Giant (`redgiant`)

## Requirements

This role has been tested on Ansible 2.16.0+ against the Distributions:

  - Windows 11
  - Windows 2022
  - Windows 2025  

## Dependencies

Nvidia drivers must be installed before installing Cinema 4D

## Example Playbook

Make sure to include "selected_option" in your playbook to select the version of
Blender you want to install. Please see vars/main.yml for the available versions.

Example playbook for installing:

```yaml
---
- name: Install Red Giant
  hosts: all
  vars:
    selected_option: "2025.2.1"  # Set the required version here
  roles:
    - redgiant  
```

## Adding to requirements.yml

If you need to bring this into another Ansible Project you can add it to the `requirements.yml` file examples below:

```yaml
- name: redgiant
  src: https://github.com/konsistent-consulting/ansible-role-redgiant.git
  version: main
```

## Adding to vars/main.yml

If you have a new version of Red Giant to add, please add the following section to vars/main.yml
within the blender role folder:

```yaml
versions:
  - '2023.2.2'
  - '2024.1.0'
  - '2024.2.0'
```

Please replace the version code with the new version (i.e 2024.3.2), replace the download
link with the correct link to the .tar.xz file from within our Nexus repository and update
the major and minor version appropriately.

You will need to run the below in your project to clone the role:

```bash
ansible-galaxy install -r requirements.yml
```
