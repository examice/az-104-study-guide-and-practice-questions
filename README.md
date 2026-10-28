# AZ-104 study guide and practice questions

AZ-104: Microsoft Azure Administrator is the exam for people who run an organization's Azure environment day to day: identities and governance, storage, compute, virtual networks, and monitoring and backup. Passing it earns the Microsoft Certified: Azure Administrator Associate certification. This repository holds a study guide mapped to the skills measured as of April 17, 2026, a six week study plan, a cheat sheet of the details people forget, and 15 original practice questions with explanations.

> Unofficial study notes by [Examice](https://examice.com/exams/microsoft/az-104?utm_source=github&utm_medium=social&utm_campaign=az-104-study-guide-and-practice-questions&utm_content=link_1). Not affiliated with or endorsed by Microsoft. The practice questions are original, written for this repository, and not taken from the exam.

## Contents

- [Exam at a glance](#exam-at-a-glance)
- [What the exam covers](#what-the-exam-covers)
- [Study plan](#study-plan)
- [Cheat sheet](#cheat-sheet)
- [Free official resources](#free-official-resources)
- [Practice questions](#practice-questions)
- [Exam day tips](#exam-day-tips)
- [FAQ](#faq)
- [Contributing](#contributing)
- [License](#license)

## Exam at a glance

| Fact | Detail |
| --- | --- |
| Exam | AZ-104: Microsoft Azure Administrator |
| Certification | Microsoft Certified: Azure Administrator Associate |
| Level | Intermediate |
| Skills outline in force | Skills measured as of April 17, 2026 |
| Time to answer | 100 minutes |
| Passing score | 700 on a scale of 1–1,000. It is a scaled score, so it does not mean 70% correct. |
| Price | USD 165 in the United States. The price depends on the country or region where the exam is proctored. |
| Delivery | Proctored, scheduled through Pearson VUE |
| Languages | English, Chinese (Simplified), Chinese (Traditional), French, German, Italian, Japanese, Korean, Portuguese (Brazil), and Spanish |
| Microsoft Learn during the exam | Available on associate exams. No extra time is added and the clock keeps running. |
| Renewal | Every 12 months, by passing a free online renewal assessment on Microsoft Learn |
| Retakes | Wait 24 hours after the first failed attempt and 14 days after each later one. At most 5 attempts in 12 months. |

Source: Microsoft Learn [certification page](https://learn.microsoft.com/en-us/credentials/certifications/azure-administrator/), [AZ-104 study guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/az-104), [exam scoring](https://learn.microsoft.com/en-us/credentials/certifications/exam-scoring-reports), [exam duration and experience](https://learn.microsoft.com/en-us/credentials/support/exam-duration-exam-experience), [retake policy](https://learn.microsoft.com/en-us/credentials/support/retake-policy), and [renewal](https://learn.microsoft.com/en-us/credentials/certifications/renew-your-microsoft-certification), checked October 28, 2026.

## What the exam covers

| Domain | Weight |
| --- | --- |
| Manage Azure identities and governance | 20–25% |
| Implement and manage storage | 15–20% |
| Deploy and manage Azure compute resources | 20–25% |
| Implement and manage virtual networking | 15–20% |
| Monitor and maintain Azure resources | 10–15% |

Source: [AZ-104 study guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/az-104), skills measured as of April 17, 2026, checked October 28, 2026. Microsoft says most questions cover generally available features, with preview features possible when they are in common use.

### Manage Azure identities and governance (20–25%)

- **Users and groups in Microsoft Entra ID.** Create users and groups, change their properties, assign licenses, invite people from other organizations as guests, and turn on self-service password reset. Docs: [groups and membership types](https://learn.microsoft.com/en-us/entra/fundamentals/concept-learn-about-groups), [dynamic membership rules](https://learn.microsoft.com/en-us/entra/identity/users/groups-dynamic-membership), [group-based licensing](https://learn.microsoft.com/en-us/microsoft-365/admin/manage/manage-group-licenses), [B2B collaboration](https://learn.microsoft.com/en-us/entra/external-id/what-is-b2b), [enable SSPR](https://learn.microsoft.com/en-us/entra/identity/authentication/tutorial-enable-sspr).
- **Access to Azure resources.** Choose the right built-in Azure role, assign it at the narrowest scope that works, and read a list of assignments to work out what someone can actually do. Docs: [built-in roles](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles), [scope](https://learn.microsoft.com/en-us/azure/role-based-access-control/scope-overview), [Azure roles vs. Microsoft Entra roles](https://learn.microsoft.com/en-us/azure/role-based-access-control/rbac-and-directory-admin-roles).
- **Subscriptions and governance.** Assign Azure Policy, lock resources, tag them, organize resource groups, subscriptions, and management groups, and keep spending in check with budgets, cost alerts, and Azure Advisor. Docs: [Azure Policy](https://learn.microsoft.com/en-us/azure/governance/policy/overview), [resource locks](https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/lock-resources), [tags](https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/tag-resources), [management groups](https://learn.microsoft.com/en-us/azure/governance/management-groups/overview), [budgets](https://learn.microsoft.com/en-us/azure/cost-management-billing/costs/tutorial-acm-create-budgets), [Advisor](https://learn.microsoft.com/en-us/azure/advisor/advisor-overview).

### Implement and manage storage (15–20%)

- **Access to storage.** Limit an account to chosen networks, hand out SAS tokens and control them with stored access policies, rotate account keys, and set up identity-based SMB access to Azure Files. Docs: [network security](https://learn.microsoft.com/en-us/azure/storage/common/storage-network-security), [SAS overview](https://learn.microsoft.com/en-us/azure/storage/common/storage-sas-overview), [stored access policies](https://learn.microsoft.com/en-us/rest/api/storageservices/define-stored-access-policy), [access keys](https://learn.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage), [Azure Files identity-based access](https://learn.microsoft.com/en-us/azure/storage/files/storage-files-active-directory-overview).
- **Storage accounts.** Create accounts, pick a redundancy option, replicate blobs between accounts, decide who holds the encryption keys, and move data with Storage Explorer and AzCopy. Docs: [account overview](https://learn.microsoft.com/en-us/azure/storage/common/storage-account-overview), [redundancy](https://learn.microsoft.com/en-us/azure/storage/common/storage-redundancy), [object replication](https://learn.microsoft.com/en-us/azure/storage/blobs/object-replication-overview), [encryption](https://learn.microsoft.com/en-us/azure/storage/common/storage-service-encryption), [AzCopy](https://learn.microsoft.com/en-us/azure/storage/common/storage-use-azcopy-v10), [Storage Explorer](https://learn.microsoft.com/en-us/azure/storage/storage-explorer/vs-azure-tools-storage-manage-with-storage-explorer).
- **Azure Files and Blob Storage.** Create file shares and containers, set access tiers, protect data with soft delete, share snapshots, and versioning, and automate tiering and deletion with lifecycle rules. Docs: [access tiers](https://learn.microsoft.com/en-us/azure/storage/blobs/access-tiers-overview), [blob soft delete](https://learn.microsoft.com/en-us/azure/storage/blobs/soft-delete-blob-overview), [container soft delete](https://learn.microsoft.com/en-us/azure/storage/blobs/soft-delete-container-overview), [share snapshots](https://learn.microsoft.com/en-us/azure/storage/files/storage-snapshots-files), [blob versioning](https://learn.microsoft.com/en-us/azure/storage/blobs/versioning-overview), [lifecycle management](https://learn.microsoft.com/en-us/azure/storage/blobs/lifecycle-management-overview).

### Deploy and manage Azure compute resources (20–25%)

- **ARM templates and Bicep.** Read and edit a template or Bicep file, deploy it, export what is already deployed, and convert JSON templates to Bicep. Docs: [template structure](https://learn.microsoft.com/en-us/azure/azure-resource-manager/templates/syntax), [Bicep](https://learn.microsoft.com/en-us/azure/azure-resource-manager/bicep/overview), [deployment modes](https://learn.microsoft.com/en-us/azure/azure-resource-manager/templates/deployment-modes), [export a template](https://learn.microsoft.com/en-us/azure/azure-resource-manager/templates/export-template-portal), [decompile JSON to Bicep](https://learn.microsoft.com/en-us/azure/azure-resource-manager/bicep/decompile).
- **Virtual machines.** Create VMs, turn on encryption at host, move VMs to another resource group, subscription, or region, resize them, manage disks, spread them across availability zones or an availability set, and run scale sets. Docs: [availability options](https://learn.microsoft.com/en-us/azure/virtual-machines/availability), [encryption at host](https://learn.microsoft.com/en-us/azure/virtual-machines/disks-enable-host-based-encryption-portal), [resize](https://learn.microsoft.com/en-us/azure/virtual-machines/sizes/resize-vm), [move resources](https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/move-resource-group-and-subscription), [disk types](https://learn.microsoft.com/en-us/azure/virtual-machines/disks-types), [scale set orchestration modes](https://learn.microsoft.com/en-us/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-orchestration-modes).
- **Containers.** Run a container registry, start containers on Azure Container Instances and Azure Container Apps, and size and scale them. Docs: [Container Registry tiers](https://learn.microsoft.com/en-us/azure/container-registry/container-registry-skus), [Container Instances](https://learn.microsoft.com/en-us/azure/container-instances/container-instances-overview), [Container Apps](https://learn.microsoft.com/en-us/azure/container-apps/overview), [Container Apps scaling](https://learn.microsoft.com/en-us/azure/container-apps/scale-app).
- **App Service.** Create plans and apps, scale plans, add TLS certificates and custom domains, back up apps, configure networking, and use deployment slots. Docs: [App Service plans](https://learn.microsoft.com/en-us/azure/app-service/overview-hosting-plans), [scale up](https://learn.microsoft.com/en-us/azure/app-service/manage-scale-up), [custom domains](https://learn.microsoft.com/en-us/azure/app-service/app-service-web-tutorial-custom-domain), [TLS certificates](https://learn.microsoft.com/en-us/azure/app-service/configure-ssl-certificate), [backup and restore](https://learn.microsoft.com/en-us/azure/app-service/manage-backup), [networking features](https://learn.microsoft.com/en-us/azure/app-service/networking-features), [deployment slots](https://learn.microsoft.com/en-us/azure/app-service/deploy-staging-slots).

### Implement and manage virtual networking (15–20%)

- **Virtual networks.** Plan address spaces and subnets, peer networks, assign public IP addresses, write user-defined routes, and troubleshoot connectivity. Docs: [virtual networks](https://learn.microsoft.com/en-us/azure/virtual-network/virtual-networks-overview), [virtual network FAQ](https://learn.microsoft.com/en-us/azure/virtual-network/virtual-networks-faq), [peering](https://learn.microsoft.com/en-us/azure/virtual-network/virtual-network-peering-overview), [public IP addresses](https://learn.microsoft.com/en-us/azure/virtual-network/ip-services/public-ip-addresses), [traffic routing](https://learn.microsoft.com/en-us/azure/virtual-network/virtual-networks-udr-overview).
- **Secure access.** Write NSG and application security group rules, work out the effective rules on a network interface, deploy Azure Bastion, and choose between service endpoints and private endpoints. Docs: [network security groups](https://learn.microsoft.com/en-us/azure/virtual-network/network-security-groups-overview), [how NSGs filter traffic](https://learn.microsoft.com/en-us/azure/virtual-network/network-security-group-how-it-works), [application security groups](https://learn.microsoft.com/en-us/azure/virtual-network/application-security-groups), [Bastion settings](https://learn.microsoft.com/en-us/azure/bastion/configuration-settings), [service endpoints](https://learn.microsoft.com/en-us/azure/virtual-network/virtual-network-service-endpoints-overview), [private endpoints](https://learn.microsoft.com/en-us/azure/private-link/private-endpoint-overview).
- **Name resolution and load balancing.** Host public and private DNS zones, deploy public and internal load balancers, and find out why one is not distributing traffic. Docs: [Azure DNS](https://learn.microsoft.com/en-us/azure/dns/dns-overview), [private DNS zones](https://learn.microsoft.com/en-us/azure/dns/private-dns-overview), [Load Balancer](https://learn.microsoft.com/en-us/azure/load-balancer/load-balancer-overview), [health probes](https://learn.microsoft.com/en-us/azure/load-balancer/load-balancer-custom-probe-overview), [troubleshoot Load Balancer](https://learn.microsoft.com/en-us/troubleshoot/azure/load-balancer/troubleshoot-common-problems/load-balancer-troubleshoot).

### Monitor and maintain Azure resources (10–15%)

- **Monitoring.** Read metrics, route logs with diagnostic settings, query logs with KQL, build alert rules, action groups, and alert processing rules, use the Insights views for VMs, storage, and networks, and run Network Watcher and Connection monitor. Docs: [Azure Monitor](https://learn.microsoft.com/en-us/azure/azure-monitor/fundamentals/overview), [diagnostic settings](https://learn.microsoft.com/en-us/azure/azure-monitor/data-collection/diagnostic-settings), [Log Analytics tutorial](https://learn.microsoft.com/en-us/azure/azure-monitor/logs/log-analytics-tutorial), [alerts](https://learn.microsoft.com/en-us/azure/azure-monitor/alerts/alerts-overview), [action groups](https://learn.microsoft.com/en-us/azure/azure-monitor/alerts/action-groups), [alert processing rules](https://learn.microsoft.com/en-us/azure/azure-monitor/alerts/alerts-processing-rules), [Network Watcher](https://learn.microsoft.com/en-us/azure/network-watcher/network-watcher-overview), [Connection monitor](https://learn.microsoft.com/en-us/azure/network-watcher/connection-monitor-overview).
- **Backup and recovery.** Create Recovery Services vaults and Backup vaults, write backup policies, back up and restore, replicate VMs to another region with Azure Site Recovery and fail them over, and read backup reports and alerts. Docs: [Recovery Services vaults](https://learn.microsoft.com/en-us/azure/backup/backup-azure-recovery-services-vault-overview), [Backup vaults](https://learn.microsoft.com/en-us/azure/backup/backup-vault-overview), [back up Azure VMs](https://learn.microsoft.com/en-us/azure/backup/backup-azure-arm-vms-prepare), [Site Recovery replication](https://learn.microsoft.com/en-us/azure/site-recovery/azure-to-azure-tutorial-enable-replication), [Site Recovery failover](https://learn.microsoft.com/en-us/azure/site-recovery/azure-to-azure-tutorial-failover-failback), [backup reports](https://learn.microsoft.com/en-us/azure/backup/configure-reports).

## Study plan

Six weeks at about 10 hours a week, 60 hours in total. Each week pairs one official learning path with lab work in your own subscription, because AZ-104 measures what an administrator implements and manages, not only what a service is. If you already run Azure at work, compress weeks 1–4 and keep the time for networking.

Labs cost money. Put each week's lab in its own resource group and delete the group when you finish. A budget alert tells you when spending crosses a threshold, but it does not stop any resource.

### Week 1: identity and governance (10 hours)

- Work through [Prerequisites for Azure administrators](https://learn.microsoft.com/en-us/training/paths/az-104-administrator-prerequisites/) and [Manage identities and governance in Azure](https://learn.microsoft.com/en-us/training/paths/az-104-manage-identities-governance/) (6 hours).
- Lab (4 hours): create users and a security group; build a dynamic membership group from the Department attribute; assign Contributor at a resource group scope and Reader at the subscription, then check what the user can do in each; add a Delete lock and try to delete the group; assign the Allowed locations policy and the Inherit a tag from the resource group policy, then run a remediation task; create a budget with an email alert.

### Week 2: storage (10 hours)

- Work through [Implement and manage storage in Azure](https://learn.microsoft.com/en-us/training/paths/az-104-manage-storage/) (5 hours).
- Lab (5 hours): create a general-purpose v2 account and change its redundancy; upload files with AzCopy; create a stored access policy, issue a SAS that uses it, then revoke it by deleting the policy; restrict the account to one subnet; turn on blob soft delete and versioning and restore a deleted blob; write a lifecycle rule; create a file share and take a share snapshot.

### Week 3: ARM templates, Bicep, and virtual machines (10 hours)

- Work through the template, VM, and scale set modules of [Deploy and manage Azure compute resources](https://learn.microsoft.com/en-us/training/paths/az-104-manage-compute-resources/) (5 hours).
- Lab (5 hours): export a resource group as a template; decompile the JSON to Bicep and redeploy it; deploy a VM, add a data disk, and resize it; enable encryption at host on a deallocated VM; create a Flexible scale set with a CPU autoscale rule.

### Week 4: containers and App Service (10 hours)

- Finish the compute learning path: containers and App Service modules (4 hours).
- Lab (6 hours): push an image to Azure Container Registry; run it on Container Instances with the OnFailure restart policy; run it on Container Apps with an HTTP scale rule and a minimum of zero replicas; create a Standard App Service plan, add a staging slot, mark one app setting as a slot setting, and swap; configure a backup.

### Week 5: virtual networking (10 hours)

- Work through [Configure and manage virtual networks for Azure administrators](https://learn.microsoft.com/en-us/training/paths/az-104-manage-virtual-networks/) (5 hours).
- Lab (5 hours): build two virtual networks and peer them; put one NSG on a subnet and another on a NIC, then use IP flow verify and effective security rules to see which rule wins; add a route table and check the result with Next hop; deploy Bastion; create a private endpoint for a storage account with its private DNS zone; deploy an internal Standard load balancer with a health probe.

### Week 6: monitoring, backup, and review (10 hours)

- Work through [Monitor and back up Azure resources](https://learn.microsoft.com/en-us/training/paths/az-104-monitor-backup-resources/) (4 hours).
- Lab (3 hours): send the activity log to a Log Analytics workspace and query it with KQL; create a metric alert with an action group and an alert processing rule that suppresses it during a maintenance window; back up a VM to a Recovery Services vault and restore a file; replicate a VM with Site Recovery and run a test failover.
- Review (3 hours): take the free practice assessment, reread this cheat sheet, answer the [practice questions](practice-questions.md), and repeat the labs for the domain where you scored lowest.

## Cheat sheet

### Identity and governance

Built-in roles to tell apart ([built-in roles](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles)):

| Role | Manage resources | Assign Azure roles |
| --- | --- | --- |
| Owner | Yes | Yes |
| Contributor | Yes | No |
| Reader | View only | No |
| User Access Administrator | No | Yes |
| Role Based Access Control Administrator | No | Yes, through Azure RBAC only, not through other means such as Azure Policy |

- Role assignments apply at four scopes: management group, subscription, resource group, and resource. Lower scopes inherit from higher ones ([scope](https://learn.microsoft.com/en-us/azure/role-based-access-control/scope-overview)).
- Azure roles control Azure resources; Microsoft Entra roles such as User Administrator control the directory. Nobody has default access to the root management group: a Global Administrator must elevate access first ([management groups](https://learn.microsoft.com/en-us/azure/governance/management-groups/overview)).

Resource locks ([lock resources](https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/lock-resources)):

| Lock (CLI name) | Portal name | Read | Change | Delete |
| --- | --- | --- | --- | --- |
| CanNotDelete | Delete | Yes | Yes | No |
| ReadOnly | Read-only | Yes | No | No |

- A lock overrides every user's permissions, Owner included. Owner and User Access Administrator can create and remove locks.
- Locks apply to control plane operations only, so they do not protect the data inside a storage account or database.
- A Read-only lock blocks POST requests: on a storage account it stops anyone listing the keys, and on a resource group it stops VMs from starting or restarting.
- A Delete lock on any resource blocks deleting its resource group. Azure does not do partial deletes.

Azure Policy effects ([effect basics](https://learn.microsoft.com/en-us/azure/governance/policy/concepts/effect-basics), [remediation](https://learn.microsoft.com/en-us/azure/governance/policy/how-to/remediate-resources)):

| Effect | What it does |
| --- | --- |
| deny | Blocks a create or update that breaks the rule |
| audit | Allows the request and marks the resource noncompliant |
| append, modify | Change the request, for example to add a tag. Modify can fix existing resources through a remediation task. |
| auditIfNotExists | Marks a resource noncompliant when a related resource is missing |
| deployIfNotExists | Deploys the missing related resource. Existing resources need a remediation task. |
| disabled | Turns the policy off without deleting the assignment |

Limits worth memorizing:

- Tags: 50 name and value pairs per resource, resource group, or subscription. Names up to 512 characters (128 on storage accounts), values up to 256. Resources do not inherit tags from their resource group or subscription; use a policy such as Inherit a tag from the resource group ([tags](https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/tag-resources), [tag policies](https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/tag-policies)).
- Management groups: 10,000 per directory, up to six levels deep not counting the root and subscription levels, and one parent per management group or subscription ([management groups](https://learn.microsoft.com/en-us/azure/governance/management-groups/overview)).

Microsoft Entra ID:

- Security groups can hold users, devices, and service principals. Microsoft 365 groups hold users only ([groups](https://learn.microsoft.com/en-us/entra/fundamentals/concept-learn-about-groups)).
- Dynamic membership groups take members from a rule only, so you cannot add or remove members by hand. One rule covers users or devices, never both. Each unique user in a dynamic group needs a Microsoft Entra ID P1 license ([dynamic membership](https://learn.microsoft.com/en-us/entra/identity/users/groups-dynamic-membership)).
- A license cannot be assigned until the user has a usage location. In group-based licensing, users without one take the tenant's location ([group licensing](https://learn.microsoft.com/en-us/microsoft-365/admin/manage/manage-group-licenses)).
- B2B guests sign in with their own identity; their user type is usually Guest and their user principal name contains `#EXT#` ([B2B collaboration](https://learn.microsoft.com/en-us/entra/external-id/what-is-b2b)).
- SSPR can be enabled for None, Selected (one group), or All users. Administrator accounts always use a fixed two-gate policy that needs two methods and bans security questions ([SSPR policy](https://learn.microsoft.com/en-us/entra/identity/authentication/concept-sspr-policy)).

Cost:

- Budgets send alerts on actual or forecast cost. They never stop or delete resources ([budgets](https://learn.microsoft.com/en-us/azure/cost-management-billing/costs/tutorial-acm-create-budgets)).
- Azure Advisor groups recommendations into Reliability, Security, Performance, Cost, and Operational excellence ([Advisor](https://learn.microsoft.com/en-us/azure/advisor/advisor-overview)).

### Storage

Redundancy ([storage redundancy](https://learn.microsoft.com/en-us/azure/storage/common/storage-redundancy)):

| Option | Primary region | Copy in a secondary region | Read the secondary without a failover | Designed durability per year |
| --- | --- | --- | --- | --- |
| LRS | One datacenter | No | No | At least 11 nines |
| ZRS | Three or more availability zones | No | No | At least 12 nines |
| GRS | LRS | Yes | No | At least 16 nines |
| RA-GRS | LRS | Yes | Yes | At least 16 nines |
| GZRS | ZRS | Yes | No | At least 16 nines |
| RA-GZRS | ZRS | Yes | Yes | At least 16 nines |

Copies to the secondary region are asynchronous, so a regional disaster can lose recent writes.

Blob access tiers ([access tiers](https://learn.microsoft.com/en-us/azure/storage/blobs/access-tiers-overview)):

| Tier | Online | Minimum stay before an early deletion charge |
| --- | --- | --- |
| Hot | Yes | None |
| Cool | Yes | 30 days |
| Cold | Yes | 90 days |
| Archive | No | 180 days |

- Hot is the default tier for a new general-purpose v2 account. Archive cannot be the account default.
- An archived blob cannot be read until you rehydrate it to an online tier, which can take up to 15 hours. Lifecycle rules cannot rehydrate.
- Only LRS, GRS, and RA-GRS accounts support the archive tier.

Shared access signatures ([SAS overview](https://learn.microsoft.com/en-us/azure/storage/common/storage-sas-overview), [stored access policies](https://learn.microsoft.com/en-us/rest/api/storageservices/define-stored-access-policy)):

| Type | Signed with | Covers | Stored access policy |
| --- | --- | --- | --- |
| User delegation SAS | A user delegation key from Microsoft Entra credentials | Blob, Queue, Table, or Files | No |
| Service SAS | The account key | One storage service | Yes |
| Account SAS | The account key | One or more services | No |

- Microsoft recommends the user delegation SAS whenever you use a SAS.
- Up to 5 stored access policies per container, share, queue, or table. Revoke every SAS tied to one by deleting it, renaming its identifier, or moving its expiry into the past. Changes can take up to 30 seconds.

Data protection:

- Blob soft delete and container soft delete each keep deleted data for 1–365 days; containers default to 7 ([blob soft delete](https://learn.microsoft.com/en-us/azure/storage/blobs/soft-delete-blob-overview), [container soft delete](https://learn.microsoft.com/en-us/azure/storage/blobs/soft-delete-container-overview)).
- File share soft delete keeps deleted shares for 1–365 days, default 7 ([share soft delete](https://learn.microsoft.com/en-us/azure/storage/files/storage-files-prevent-file-share-deletion)).
- Share snapshots are read-only and incremental, and deleting a share deletes its snapshots ([share snapshots](https://learn.microsoft.com/en-us/azure/storage/files/storage-snapshots-files)).
- Object replication copies block blobs asynchronously. It needs blob versioning on both accounts and change feed on the source ([object replication](https://learn.microsoft.com/en-us/azure/storage/blobs/object-replication-overview)).
- A new or edited lifecycle policy can take up to 24 hours to start running ([lifecycle management](https://learn.microsoft.com/en-us/azure/storage/blobs/lifecycle-management-overview)).

Accounts and Azure Files:

- Account names are 3–24 characters, lowercase letters and numbers only, and unique across Azure ([account overview](https://learn.microsoft.com/en-us/azure/storage/common/storage-account-overview)).
- Encryption at rest is always on (256-bit AES) with Microsoft-managed keys by default. Customer-managed keys live in Key Vault or Managed HSM. Infrastructure encryption can only be chosen when you create the account ([encryption](https://learn.microsoft.com/en-us/azure/storage/common/storage-service-encryption), [infrastructure encryption](https://learn.microsoft.com/en-us/azure/storage/common/infrastructure-encryption-enable)).
- Identity-based SMB access to Azure Files uses one source per account: on-premises AD DS, Microsoft Entra Domain Services, or Microsoft Entra Kerberos. Users need a share-level permission and file or directory permissions. SMB uses TCP port 445 ([Azure Files identity](https://learn.microsoft.com/en-us/azure/storage/files/storage-files-active-directory-overview), [SMB troubleshooting](https://learn.microsoft.com/en-us/troubleshoot/azure/azure-storage/files/connectivity/files-troubleshoot)).

### Compute

VM availability ([availability options](https://learn.microsoft.com/en-us/azure/virtual-machines/availability), [availability sets](https://learn.microsoft.com/en-us/azure/virtual-machines/availability-set-overview), [orchestration modes](https://learn.microsoft.com/en-us/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-orchestration-modes)):

| Option | What it spreads VMs across | Facts to remember |
| --- | --- | --- |
| Availability set | Fault domains (shared power and network switch) and update domains (restarted together) | Up to 3 fault domains and 20 update domains, fixed at creation. A VM joins a set only when it is created. 99.95% SLA with two or more VMs. |
| Availability zones | Separate datacenters in the region | Each zone has its own power, cooling, and networking |
| Scale set, Flexible orchestration | Zones or fault domains | Microsoft's recommended mode, up to 1,000 VMs, mixed VM types allowed |

- Resizing a running VM restarts it. If the new size is not on the current hardware cluster, deallocate the VM first; in an availability set, you may have to deallocate every VM in the set. Deallocation releases dynamic IP addresses ([resize](https://learn.microsoft.com/en-us/azure/virtual-machines/sizes/resize-vm)).
- Moving a VM to another resource group or subscription does not change its region. Use Azure Resource Mover to change regions. Both resource groups are locked during a move ([move resources](https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/move-resource-group-and-subscription)).
- Ultra Disks and Premium SSD v2 cannot be OS disks. Standard HDD OS disks retire on September 8, 2028 ([disk types](https://learn.microsoft.com/en-us/azure/virtual-machines/disks-types)).
- Encryption at host needs the `EncryptionAtHost` feature registered on the subscription, and an existing VM must be deallocated to turn it on. It also encrypts temporary disks and disk caches ([encryption at host](https://learn.microsoft.com/en-us/azure/virtual-machines/disks-enable-host-based-encryption-portal)).

ARM templates and Bicep ([deployment modes](https://learn.microsoft.com/en-us/azure/azure-resource-manager/templates/deployment-modes), [template structure](https://learn.microsoft.com/en-us/azure/azure-resource-manager/templates/syntax)):

- The main template sections are `$schema`, `contentVersion`, `parameters`, `variables`, `functions`, `resources`, and `outputs`. Only `$schema`, `contentVersion`, and `resources` are required.
- Incremental is the default mode. It leaves resources that are not in the template alone, but it reapplies every property of the resources it does list, so properties you leave out go back to their defaults.
- Complete mode deletes resources that are not in the template. Microsoft is deprecating it gradually and points to deployment stacks for deletions.
- `az bicep decompile` turns a JSON template into a Bicep file that may need cleanup ([decompile](https://learn.microsoft.com/en-us/azure/azure-resource-manager/bicep/decompile)).

Containers:

| Service | Facts to remember |
| --- | --- |
| Container Registry | Basic, Standard, and Premium tiers. Geo-replication and private endpoints need Premium ([tiers](https://learn.microsoft.com/en-us/azure/container-registry/container-registry-skus)). |
| Container Instances | Restart policies: Always (the default), OnFailure, and Never ([restart policy](https://learn.microsoft.com/en-us/azure/container-instances/container-instances-restart-policy)) |
| Container Apps | Scale rules are HTTP, TCP, or custom (KEDA scalers). Apps can scale to zero, which stops usage charges. Up to 1,000 replicas per revision ([scaling](https://learn.microsoft.com/en-us/azure/container-apps/scale-app)). |

App Service plan tiers ([plans](https://learn.microsoft.com/en-us/azure/app-service/overview-hosting-plans), [scale up](https://learn.microsoft.com/en-us/azure/app-service/manage-scale-up), [deployment slots](https://learn.microsoft.com/en-us/azure/app-service/deploy-staging-slots), [backup](https://learn.microsoft.com/en-us/azure/app-service/manage-backup), [autoscale](https://learn.microsoft.com/en-us/azure/azure-monitor/autoscale/autoscale-get-started)):

| Tier | Maximum instances | Autoscale rules | Deployment slots | Backups |
| --- | --- | --- | --- | --- |
| Free, Shared | Cannot scale out | No | No | No |
| Basic | 3 | No | No | Production slot only |
| Standard | 10 | Yes | 5 | Yes |
| Premium | 30 | Yes | Yes | Yes |
| Isolated v2 | 100 | Yes | Yes | Yes |

- Custom domains need a paid tier, not Free (F1). Map a root domain with an A record and a subdomain with a CNAME, plus a TXT record for verification ([custom domains](https://learn.microsoft.com/en-us/azure/app-service/app-service-web-tutorial-custom-domain)).
- App settings and connection strings swap with the slot unless you mark them as slot settings.
- Virtual network integration is outbound only and needs Basic or higher. For private inbound access, use a private endpoint ([VNet integration](https://learn.microsoft.com/en-us/azure/app-service/overview-vnet-integration)).

### Virtual networking

- Azure reserves 5 addresses in every subnet: the first four and the last. The smallest IPv4 subnet is /29 and the largest is /2. IPv6 subnets are exactly /64 ([VNet FAQ](https://learn.microsoft.com/en-us/azure/virtual-network/virtual-networks-faq)).

NSG default rules ([NSG overview](https://learn.microsoft.com/en-us/azure/virtual-network/network-security-groups-overview)):

| Direction | Priority | Rule |
| --- | --- | --- |
| Inbound | 65000 | AllowVNetInBound |
| Inbound | 65001 | AllowAzureLoadBalancerInBound |
| Inbound | 65500 | DenyAllInbound |
| Outbound | 65000 | AllowVnetOutBound |
| Outbound | 65001 | AllowInternetOutBound |
| Outbound | 65500 | DenyAllOutBound |

- Custom rules take priorities 100–4096. The lowest number wins and processing stops at the first match. NSGs are stateful, so return traffic needs no rule.
- Inbound traffic meets the subnet NSG first, then the NIC NSG. Outbound runs NIC first, then subnet. Traffic must be allowed by both ([how NSGs filter traffic](https://learn.microsoft.com/en-us/azure/virtual-network/network-security-group-how-it-works)).
- Peering is not transitive and needs address spaces that do not overlap. Global peering connects regions. Gateway transit lets a peered network use the other network's VPN or ExpressRoute gateway ([peering](https://learn.microsoft.com/en-us/azure/virtual-network/virtual-network-peering-overview), [manage peering](https://learn.microsoft.com/en-us/azure/virtual-network/virtual-network-manage-peering)).
- Azure picks a route by longest prefix match. User-defined routes can point to a virtual appliance (with its IP address), a virtual network gateway, the virtual network, the internet, or None, which drops the traffic ([traffic routing](https://learn.microsoft.com/en-us/azure/virtual-network/virtual-networks-udr-overview)).
- Bastion needs a subnet named `AzureBastionSubnet`, /26 or larger, and a Standard public IP. The Developer offering needs neither. Host scaling and custom ports need Standard or higher; session recording needs Premium ([Bastion settings](https://learn.microsoft.com/en-us/azure/bastion/configuration-settings)).
- Basic SKU public IPs and the Basic Load Balancer retired on September 30, 2025. Standard public IPs are static and closed to inbound traffic until an NSG allows it ([public IP addresses](https://learn.microsoft.com/en-us/azure/virtual-network/ip-services/public-ip-addresses), [Load Balancer SKUs](https://learn.microsoft.com/en-us/azure/load-balancer/skus)).

Service endpoint vs. private endpoint ([service endpoints](https://learn.microsoft.com/en-us/azure/virtual-network/virtual-network-service-endpoints-overview), [private endpoints](https://learn.microsoft.com/en-us/azure/private-link/private-endpoint-overview), [private endpoint DNS](https://learn.microsoft.com/en-us/azure/private-link/private-endpoint-dns)):

| | Service endpoint | Private endpoint |
| --- | --- | --- |
| What it is | A subnet setting: traffic to the service uses the subnet's private source address over the Azure backbone | A network interface with a private IP address from your subnet, mapped to one resource |
| Address clients connect to | The service's public endpoint | The private IP address |
| Works from on-premises | No | Yes, over VPN or ExpressRoute |
| DNS change | None | Names must resolve to the private IP, usually through a `privatelink` private DNS zone |

DNS and load balancing:

- To host a public domain in Azure DNS, create the zone and set NS records at your registrar ([delegation](https://learn.microsoft.com/en-us/azure/dns/dns-delegate-domain-azure-dns)).
- Private zone autoregistration creates records for VMs only. A virtual network can have autoregistration on only one private zone, but one zone can link to many networks ([autoregistration](https://learn.microsoft.com/en-us/azure/dns/private-dns-autoregistration)).
- Load Balancer distribution: the default hash uses five values (source and destination IP and port, plus protocol). Session persistence can use Client IP (two values) or Client IP and protocol (three values) ([distribution modes](https://learn.microsoft.com/en-us/azure/load-balancer/distribution-mode-concepts)).
- Standard Load Balancer health probes use TCP, HTTP, or HTTPS, and IPv4 probes come from 168.63.129.16. Microsoft does not support blocking probes with NSG rules ([health probes](https://learn.microsoft.com/en-us/azure/load-balancer/load-balancer-custom-probe-overview)).

Network Watcher ([overview](https://learn.microsoft.com/en-us/azure/network-watcher/network-watcher-overview)):

| Question | Tool |
| --- | --- |
| Is this packet allowed to or from the VM, and by which rule? | IP flow verify |
| Where does traffic to this address go next? | Next hop |
| Which NSG rules apply to this NIC, subnet and NIC combined? | Effective security rules |
| Can this VM reach that address right now? | Connection troubleshoot |
| Is the connection healthy over time? | Connection monitor |
| What exactly is on the wire? | Packet capture |
| What traffic flowed through the network? | Virtual network flow logs. NSG flow logs accept no new configurations and retire on September 30, 2027. |

### Monitoring and backup

- The activity log keeps events for 90 days. Send it to a Log Analytics workspace, storage account, or event hub with a diagnostic setting to keep it longer ([activity log](https://learn.microsoft.com/en-us/azure/azure-monitor/fundamentals/activity-log)).
- Platform metrics are kept for 93 days ([metrics](https://learn.microsoft.com/en-us/azure/azure-monitor/metrics/data-platform-metrics)).
- A diagnostic setting has at most one destination of each type: Log Analytics workspace, storage account, event hub, or partner solution. For regional resources, the storage account or event hub must be in the same region ([diagnostic settings](https://learn.microsoft.com/en-us/azure/azure-monitor/data-collection/diagnostic-settings)).
- Alert types: metric, log search, and activity log. Service Health and Resource Health alerts are activity log alerts ([alerts](https://learn.microsoft.com/en-us/azure/azure-monitor/alerts/alerts-overview)).
- Action groups say who is notified (email, SMS, voice, push) and what runs (webhook, Azure Functions, Logic Apps, and others) ([action groups](https://learn.microsoft.com/en-us/azure/azure-monitor/alerts/action-groups)).
- Alert processing rules add or suppress action groups on alerts that already fired, for example during a maintenance window. They work within their own subscription ([alert processing rules](https://learn.microsoft.com/en-us/azure/azure-monitor/alerts/alerts-processing-rules)).

Which vault holds what ([Azure Backup FAQ](https://learn.microsoft.com/en-us/azure/backup/backup-azure-backup-faq)):

| Recovery Services vault | Backup vault |
| --- | --- |
| Azure VMs, SQL Server in Azure VMs, SAP HANA in Azure VMs, Azure Files, the MARS agent, Azure Backup Server, and DPM | Azure Disks, Azure Blobs, Azure Database for PostgreSQL, and newer workloads |

- A backup vault must be in the same region as the data it protects ([prepare VM backup](https://learn.microsoft.com/en-us/azure/backup/backup-azure-arm-vms-prepare)).
- Soft delete keeps deleted backup data for 14 more days at no cost ([Recovery Services vaults](https://learn.microsoft.com/en-us/azure/backup/backup-azure-recovery-services-vault-overview)).
- Site Recovery order for Azure VMs: enable replication, run a test failover into a network that is not production, fail over, commit (which deletes the VM's recovery points), reprotect, then fail back ([test failover](https://learn.microsoft.com/en-us/azure/site-recovery/azure-to-azure-tutorial-dr-drill), [failover and reprotect](https://learn.microsoft.com/en-us/azure/site-recovery/azure-to-azure-tutorial-failover-failback)).

## Free official resources

- [AZ-104 certification page](https://learn.microsoft.com/en-us/credentials/certifications/azure-administrator/): exam details, languages, scheduling, and price for your country.
- [AZ-104 study guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/az-104): the skills measured and the change log between versions.
- Learning paths: [Prerequisites for Azure administrators](https://learn.microsoft.com/en-us/training/paths/az-104-administrator-prerequisites/), [Manage identities and governance in Azure](https://learn.microsoft.com/en-us/training/paths/az-104-manage-identities-governance/), [Implement and manage storage in Azure](https://learn.microsoft.com/en-us/training/paths/az-104-manage-storage/), [Deploy and manage Azure compute resources](https://learn.microsoft.com/en-us/training/paths/az-104-manage-compute-resources/), [Configure and manage virtual networks for Azure administrators](https://learn.microsoft.com/en-us/training/paths/az-104-manage-virtual-networks/), and [Monitor and back up Azure resources](https://learn.microsoft.com/en-us/training/paths/az-104-monitor-backup-resources/).
- [Course AZ-104T00](https://learn.microsoft.com/en-us/training/courses/az-104t00): the same content taught by an instructor over 4 days.
- [AZ-104 lab instructions](https://microsoftlearning.github.io/AZ-104-MicrosoftAzureAdministrator/) from Microsoft Learning on GitHub.
- [Free practice assessment](https://aiskillsnavigator.microsoft.com/credentials/cert-43cb319ee6436b163afb130cedc008b5af26d82c4921b4bab5b265d83bc33907): the AZ-104 assessment now runs on AI Skills Navigator, and you must sign in to launch it.
- [Exam sandbox](https://aka.ms/examdemo): try the question types and the exam interface before test day.
- [AZ-104 exam prep videos](https://aka.ms/AZ104-ExamPrep) and [Exam Readiness Zone](https://learn.microsoft.com/en-us/shows/exam-readiness-zone/?terms=az-104).
- [Azure free account](https://azure.microsoft.com/en-us/pricing/purchase-options/azure-account): as of October 28, 2026, a $200 credit to use within 30 days, free monthly amounts of more than 20 popular services for 12 months (new customers only), and more than 65 services that stay free within monthly limits. Students can use [Azure for Students](https://azure.microsoft.com/en-us/free/students) with a school email and no credit card.

## Practice questions

[practice-questions.md](practice-questions.md) has 15 original questions spread across the five domains by weight, each with the reasoning behind every option and a link to the Microsoft Learn page that backs it.

For more, the [Examice AZ-104 practice bank](https://examice.com/exams/microsoft/az-104?utm_source=github&utm_medium=social&utm_campaign=az-104-study-guide-and-practice-questions&utm_content=link_2) has 600+ questions, each with a written explanation and a discussion; the first 5 are free, explanations included.

## Exam day tips

- Microsoft does not publish a question count for AZ-104. Its exam duration page says most of its exams have 40–60 questions.
- You get 100 minutes to answer. Microsoft's duration page sets 120 minutes of seat time for associate exams of this length, which covers the instructions, the candidate agreement, and optional comments.
- Microsoft Learn opens in a split screen from the left pane. You can reach anything on learn.microsoft.com except Q&A, practice assessments, and your profile, and Ctrl+F (Command+F on a Mac) searches the open page. The clock keeps running, so save it for a CLI parameter or a limit you cannot recall.
- Five minutes of break time are built into the exam. The clock runs during a break, and once you start one you cannot go back to any question you have already seen. Breaks are not allowed in the middle of a lab or a set of problem and solution questions.
- The exam may contain interactive components. Microsoft does not say which exams include labs, so read the overview screens at the start.
- There is no penalty for a wrong answer and some questions are unscored, so answer every question.
- Schedule with a personal Microsoft account. Records tied to a work or school account are lost if you leave that organization.
- If AZ-104 is not offered in your preferred language, you can request 30 extra minutes.

## FAQ

### How hard is AZ-104?

Microsoft rates it Intermediate. The audience profile expects you to know operating systems, networking, servers, and virtualization, and to have worked with PowerShell, the Azure CLI, the Azure portal, ARM templates or Bicep, and Microsoft Entra ID. Passing takes a scaled 700 out of 1,000 ([study guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/az-104)).

### How long should I study for AZ-104?

Microsoft's classroom version, [course AZ-104T00](https://learn.microsoft.com/en-us/training/courses/az-104t00), runs 4 days. Studying on your own takes longer because you also need lab time. The plan above budgets 6 weeks at about 10 hours a week.

### Does the Azure Administrator Associate certification expire?

Yes, after 12 months. Renewal is free: a renewal assessment opens on Microsoft Learn 6 months before the expiry date. It is online, unproctored, open book, and takes about 45 minutes, and you can retry it as often as you need, with a 24 hour wait after the second attempt. If the certification expires, you must pass AZ-104 again ([renewal](https://learn.microsoft.com/en-us/credentials/certifications/renew-your-microsoft-certification), [renewal FAQ](https://learn.microsoft.com/en-us/credentials/certifications/renew-your-microsoft-certification-faq)).

### What is the AZ-104 retake policy?

After a first failed attempt you wait 24 hours, and after each later failure you wait 14 days. You can take the exam at most 5 times in 12 months from your first attempt, you pay for each retake, and you cannot retake an exam you passed unless the certification has expired. Microsoft waives the wait only for internet or equipment failures that have a Pearson VUE case number ([retake policy](https://learn.microsoft.com/en-us/credentials/support/retake-policy)).

### Is AZ-104 being retired?

No retirement has been announced. AZ-104 is not on Microsoft's [list of exams scheduled to retire](https://learn.microsoft.com/en-us/credentials/support/retired-certification-exams) as of October 28, 2026, and its skills outline was last updated on April 17, 2026. Localized versions of the exam are usually updated about eight weeks after the English version.

### Do I need AZ-900 before AZ-104?

The [certification page](https://learn.microsoft.com/en-us/credentials/certifications/azure-administrator/) lists AZ-104 as the only exam for the Azure Administrator Associate and names no prerequisite certification. AZ-900 covers cloud and Azure basics, which helps if you are new to Azure, but it is optional.

## Contributing

Corrections are welcome. If a fact is wrong or out of date, open an issue or a pull request and include a link to the official source.

## License

Text and questions © Examice, licensed under [CC BY 4.0](LICENSE).

Microsoft, Azure, and Microsoft Entra are trademarks of the Microsoft group of companies. This repository is not affiliated with or endorsed by Microsoft.
