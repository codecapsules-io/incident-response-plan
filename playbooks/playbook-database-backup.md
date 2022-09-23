

## Playbook: Database Backup and Data Protection

Assign steps to individuals or teams to work concurrently, when possible; this playbook is not purely sequential. Use your best judgment.

### General

There are many components that need to be backed up at Code Capsules.

1. Main Kubernetes Cluster
2. Main Application databases
3. Customer managed shared clusters
4. Customer managed private clusters

All of these clusters and systems sit on various clouds (AWS, Google, Azure, OVH and +OneX).

### Database Backup

* **Full Backup of Main Clusters** making use of [velero](https://velero.io/) every month
* **Full Backup of Main Databases** the internal cluster database controllers backup main databases weekly into external storage outside of the cluster in case the cluster is compromised, we are then able to recover on another cloud/environment.
* **Full Backup of Customer Databases** the internal cluster database controllers allow individual customer spaces and capsules to manually backup their databases or set them to be backed up every week. These backups are also stored external to the cluster in case of cluster compromise.

### Data Protection

We take all data at Code Capsules seriously.

1. Only essential devops engineers have access to any cloud/clusters for maintenance purposes
2. Staff do not have rights to accessing, copying or viewing customer databases and clusters
3. Sensitive data stored in our main clusters are only exposed via secure endpoints (if necessary) through HTTPS and JWT-based auth tokens, for example our admin reporting
4. Sensitive billing and payment information is outsourced to external accounting and payment providers, in the event that main clusters are compromised, we can fallback on to the managed providers

### Resources

#### Additional Information

1. <a name="database-backup-playbook-ref-1"></a>["Developing a backup plan"](https://www.red-gate.com/simple-talk/databases/sql-server/database-administration-sql-server/developing-a-backup-plan/)

