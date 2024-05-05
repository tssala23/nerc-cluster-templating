# Nerc-Cluster-Templating
This repo has an Anisble playbook to create overlay dir to be applied on NERC for new clusters.

There a few variable to be set in the [vars.yaml](https://github.com/tssala23/nerc-cluster-templating/blob/main/roles/cluster_template/vars/vars.yaml) file.

There are two example outputs in the outputs directory.

## Usage
After setting the variables in the [vars.yaml](https://github.com/tssala23/nerc-cluster-templating/blob/main/roles/cluster_template/vars/vars.yaml) file, run the playbook `ansible-playbook playbook.yaml`.

The resulting cluster dir, which would be transferred to the [overlays dir](https://github.com/OCP-on-NERC/nerc-ocp-config/tree/main/cluster-scope/overlays) is outputted to the outputs dir.
