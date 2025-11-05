# aap-portal-bootstrap

Ansible playbook to install the Ansible Automation Platform Self-Service Portal on Openshift. Based on the Red Hat Ansible Automation Platform [documentation](https://docs.redhat.com/en/documentation/red_hat_ansible_automation_platform/2.6/html-single/installing_self-service_automation_portal/index).

## Pre-requisites

- RHSM API Offline Token -> [Instructions](https://access.redhat.com/articles/3626371)

## Requirements

_These are the tested versions of collections used in the bootstrap.yml playbook (other versions may work)_

```yaml
collections:
  - name: ansible.platform
    version: 2.6.20250924
  - name: redhat.openshift
    version: 2.3.0
```