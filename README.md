# Nerc-Cluster-Templating
This repo has an Ansible playbook to create an overlay dir for a standard NERC cluster.

There a few variable to be set in the [cluster.yaml](group_vars/all/cluster.yaml) file.

There are two example outputs in the outputs directory.

## Usage
After setting the variables in the [cluster.yaml](group_vars/all/cluster.yaml) file, run the playbook `ansible-playbook playbook.yaml`.

The resulting cluster dir, which would be transferred to the [cluster-scope overlays dir](https://github.com/OCP-on-NERC/nerc-ocp-config/tree/main/cluster-scope/overlays) is outputted to the outputs dir.
