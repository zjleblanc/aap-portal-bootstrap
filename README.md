# aap-portal-bootstrap

Ansible playbook to install the Ansible Automation Platform Self-Service Portal on Openshift. Based on the Red Hat Ansible Automation Platform [documentation](https://docs.redhat.com/en/documentation/red_hat_ansible_automation_platform/2.6/html-single/installing_self-service_automation_portal/index).

## Usage

Once you have satisfied the requirements outlined below, the playbook can be executed as:
```bash
ansible-playbook bootstrap.yml -e rhsm_offline_token=<token>
```

## Pre-requisites

- RHSM API Offline Token -> [Instructions](https://access.redhat.com/articles/3626371)
- Set the following Environment Variables
  | Env | Example |
  | --- | --- |
  | AAP_HOSTNAME | https://aap.example.com | 
  | AAP_USERNAME | admin (need admin privileges) |
  | AAP_PASSWORD | secret |
  | K8S_AUTH_HOST | https://api.ocp.example.com:6443 |
- Login to OpenShift<br>
  `oc login --token={token} --server=https://api.ocp.example.com:6443`<br>
- _You can use other supported methods to leverage the collections below (I have outlined what I used)_

## Requirements

_These are the tested versions of collections used in the bootstrap.yml playbook (other versions may work)_

```yaml
collections:
  - name: ansible.platform
    version: 2.6.20250924
  - name: redhat.openshift
    version: 2.3.0
  - name: kubernetes.core
    version: 6.2.0
```

```bash
$ oc version
Client Version: 4.15.9
Kustomize Version: v5.0.4-0.20230601165947-6ce0bf390ce3
Server Version: 4.18.27
Kubernetes Version: v1.31.13
```