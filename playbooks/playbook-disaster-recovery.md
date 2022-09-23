

## Playbook: Disaster Recovery

Assign steps to individuals or teams to work concurrently, when possible; this playbook is not purely sequential. Use your best judgment.

### Investigate

1. What system/cluster went down or was compromised on which cloud
2. Which SME is responsible for managing that cloud/cluster
3. Which individual namespaces, capsules or virtual networks were compromised

### Remediate

* **Plan remediation events** where these steps are launched together (or in coordinated fashion), with appropriate teams ready to respond to any disruption.
* **Consider the timing and tradeoffs** of remediation actions: your response has consequences.

#### Contain

1. Disable any access to the cluster/cloud except for the SME investigating
2. Disable any ingress/egress into/out of the cluster
3. Reconfigure DNS if necessary

#### Eradicate / Recover

1. Ensure backups of cluster and/or databases within the cluster are secure and available
2. If necessary, spin up a new environment in another cloud/cluster and apply the cluster and database backups
3. Reconfigure DNS settings to redirect ingress/egress into that cluster.


