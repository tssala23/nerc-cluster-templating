# Nerc-Cluster-Templating
This repo has an Ansible playbook to create an overlay dir for a standard NERC cluster.

Jinja2 is used to add insert variables into existing templates stored in the [templates](roles/cluster-template/templates) dir. Each dir inside of the [templates](roles/cluster-template/templates) dir corresponds to a defining variable of a NERC cluster. These are address_type (external or internal) and access_type (admin or public). By changing these varibles there are 4 possible cluster types that can be created:

- External public e.g. prod
- Extenral admin e.g. obs
- Internal public
- Internal admin e.g. infra

There a few variable to be set in the [cluster.yaml](group_vars/all/cluster.yaml) file. These variables are:
```
clusters:
  - name: #Name of the cluster
    address_type: #external or internal
    access_type: #admin or public
    oauth: #Options list: [keycloak, github] or [keycloak] or [github]
    vlanID: # used in templates/nodenetworkconfigurationpolicies
    clusterVersion: #used in clusterversion
    clusterID: #used in clusterversion
    cephstoragePool: #for ocs external storage cluster
    apiCertDuration:
    apiCertRenewBefore:
    apiCertDnsName:
    ingressCertDuration:
    ingressCertRenewBefore:
    ingressCertDnsName:
```

## Usage
After setting the variables in the [cluster.yaml](group_vars/all/cluster.yaml) file, run the playbook `ansible-playbook playbook.yaml`.

The resulting cluster dir, which would be transferred to the [cluster-scope overlays dir](https://github.com/OCP-on-NERC/nerc-ocp-config/tree/main/cluster-scope/overlays) is outputted to the [outputs](outputs) dir.

## Adding New Templates
New templates can be added by inserting the template file into the correct dir inside of the [templates](roles/cluster-template/templates) dir. If the template requires a new variable it can be added to the [cluster.yaml](group_vars/all/cluster.yaml) file.