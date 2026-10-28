# AZ-104 practice questions

Fifteen scenario questions in the style of AZ-104, spread across the five domains by their weights: 3 on identities and governance, 3 on storage, 4 on compute, 3 on networking, and 2 on monitoring and backup. Each answer explains why the correct option works, why the others do not, and links the Microsoft Learn page that backs it. The behavior described was checked against Microsoft Learn on October 28, 2026.

> Unofficial study notes by Examice. Not affiliated with or endorsed by Microsoft. The practice questions are original, written for this repository, and not taken from the exam.

### Question 1

*Manage Azure identities and governance*

You need a Microsoft Entra security group named Sales-All whose membership updates on its own when a user's Department attribute is set to Sales. Two contractors whose Department attribute is empty must also be members. Every user has a Microsoft Entra ID P1 license. What should you do?

- A. Create a dynamic membership group with the rule `user.department -eq "Sales"`, then add the two contractors as members by hand.
- B. Create a dynamic membership group with the rule `(user.department -eq "Sales") -or (user.jobTitle -eq "Sales contractor")`, then set that job title on the two contractors.
- C. Create a dynamic device group with the rule `user.department -eq "Sales"`.
- D. Create a group with assigned membership and add the Sales users and the contractors. The group then follows changes to the Department attribute.

<details><summary>Show answer</summary>

**B.** A dynamic membership group gets its members from its rule only, and a rule can join several expressions with `-or`. Giving the contractors an attribute value that the rule matches brings them in, and they leave the group if that value changes.

- A is wrong because you cannot add or remove members of a dynamic membership group by hand.
- C is wrong because a device rule can reference device attributes only, and one rule cannot mix users and devices.
- D is wrong because an assigned group changes only when someone edits its membership. It never reads user attributes.

Docs: [Dynamic membership rules for groups](https://learn.microsoft.com/en-us/entra/identity/users/groups-dynamic-membership)

</details>

### Question 2

*Manage Azure identities and governance*

Every resource group in Subscription1 has a CostCenter tag. You need every resource to carry the same CostCenter value as its resource group. The rule must cover new resources and the 400 resources that already exist, with the least administrative effort. What should you do?

- A. Nothing. Resources inherit the tags of their resource group.
- B. Assign the built-in policy Inherit a tag from the resource group to Subscription1, then create a remediation task.
- C. Assign the built-in policy Require a tag on resources to Subscription1.
- D. Apply a Read-only lock to each resource group.

<details><summary>Show answer</summary>

**B.** Inherit a tag from the resource group uses the modify effect. It writes the resource group's tag value onto resources as they are created or updated, and a remediation task applies the same change to resources that already exist.

- A is wrong because resources do not inherit tags from their resource group or subscription.
- C is wrong because that policy uses deny. It blocks new resources that lack the tag, but it does not copy the resource group's value and it does nothing for existing resources.
- D is wrong because a lock adds no tags, and a Read-only lock blocks the very updates you need.

Docs: [Assign policy definitions for tag compliance](https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/tag-policies), [Remediate noncompliant resources](https://learn.microsoft.com/en-us/azure/governance/policy/how-to/remediate-resources)

</details>

### Question 3

*Manage Azure identities and governance*

VM1 is in resource group RG1 and is stopped and deallocated. RG1 has a Read-only lock. Admin1 has the Owner role on the subscription and tries to start VM1 from the Azure portal. What happens?

- A. VM1 starts, because the Owner role overrides resource locks.
- B. VM1 starts, because starting a VM does not change its configuration.
- C. The start fails until someone removes the lock, because a Read-only lock blocks the POST request that starts a VM.
- D. The start fails, because a role assigned at the subscription does not apply to resource groups.

<details><summary>Show answer</summary>

**C.** A lock applies to every user and role. A Read-only lock blocks POST requests to Azure Resource Manager, and starting or restarting a VM is a POST. Admin1 can remove the lock, because Owner includes the lock permissions, and then start VM1.

- A is wrong because locks override user permissions, Owner included.
- B is wrong because the lock blocks the operation by its request type, not by whether it changes settings.
- D is wrong because role assignments at a subscription are inherited by its resource groups and resources.

Docs: [Lock your Azure resources](https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/lock-resources), [Understand scope for Azure RBAC](https://learn.microsoft.com/en-us/azure/role-based-access-control/scope-overview)

</details>

### Question 4

*Implement and manage storage*

You are creating a storage account for an order system in a region that has availability zones and a paired region. Writes must continue if one availability zone in the primary region fails. The data must also be copied to a second region, and the app must be able to read from that second region at any time without waiting for a failover. Which redundancy option should you choose?

- A. ZRS
- B. GRS
- C. RA-GRS
- D. RA-GZRS

<details><summary>Show answer</summary>

**D.** RA-GZRS replicates across availability zones in the primary region, copies the data to the secondary region, and keeps a readable endpoint in the secondary region at all times.

- A is wrong because ZRS keeps all copies in the primary region.
- B is wrong because GRS uses LRS in the primary region, and its secondary copy is readable only after a failover.
- C is wrong because RA-GRS uses LRS in the primary region, which does not spread copies across zones.

Docs: [Azure Storage redundancy](https://learn.microsoft.com/en-us/azure/storage/common/storage-redundancy)

</details>

### Question 5

*Implement and manage storage*

You gave a partner several service SAS tokens for container1. Every token references a stored access policy named partner-read on container1. One token was posted publicly. You must revoke every token that uses partner-read as fast as possible. Other applications authenticate with the storage account keys and must keep working. What should you do?

- A. Delete the partner-read stored access policy, or set its expiry time to a date in the past.
- B. Regenerate both storage account keys.
- C. Set the anonymous access level of container1 to Private.
- D. Apply a Read-only lock to the storage account.

<details><summary>Show answer</summary>

**A.** A service SAS that references a stored access policy takes its start time, expiry, and permissions from that policy. Deleting the policy, renaming its identifier, or moving its expiry into the past invalidates every SAS tied to it. The change can take up to 30 seconds.

- B is wrong because regenerating the keys would also revoke the tokens, but it breaks every application that uses the keys.
- C is wrong because the anonymous access level controls requests that carry no credentials. A SAS is a credential, so it keeps working.
- D is wrong because locks apply to control plane operations only. Reading blobs with a SAS is a data plane operation.

Docs: [Create a stored access policy](https://learn.microsoft.com/en-us/rest/api/storageservices/define-stored-access-policy), [Grant limited access with shared access signatures](https://learn.microsoft.com/en-us/azure/storage/common/storage-sas-overview)

</details>

### Question 6

*Implement and manage storage*

Storage1 is a general-purpose v2 account configured for GZRS. You add a lifecycle management rule that moves block blobs to the archive tier 180 days after they were last modified. Days later, no eligible blob has moved to archive. What is the cause?

- A. Lifecycle management can move blobs to the cool and cold tiers only.
- B. The archive tier is not supported on accounts that use ZRS, GZRS, or RA-GZRS.
- C. Blob versioning must be enabled before a lifecycle rule can change a blob's tier.
- D. A blob must spend 30 days in the cool tier before it can move to archive.

<details><summary>Show answer</summary>

**B.** Only accounts configured for LRS, GRS, or RA-GRS support moving blobs to the archive tier. To archive this data, use an account with one of those redundancy options.

- A is wrong because lifecycle rules can move blobs to the cool, cold, or archive tier. What they cannot do is rehydrate a blob out of archive.
- C is wrong because versioning is not a requirement for tiering rules.
- D is wrong because a blob can move from hot straight to archive. The 30 day figure is the minimum stay in cool before an early deletion charge, not a step you must pass through.

Docs: [Access tiers for blob data](https://learn.microsoft.com/en-us/azure/storage/blobs/access-tiers-overview), [Lifecycle management overview](https://learn.microsoft.com/en-us/azure/storage/blobs/lifecycle-management-overview)

</details>

### Question 7

*Deploy and manage Azure compute resources*

Resource group RG1 contains VM1 and storage1. You run `az deployment group create` against RG1 with an ARM template that defines only storage2, and you do not set a deployment mode. After the deployment succeeds, what does RG1 contain?

- A. storage2 only
- B. VM1, storage1, and storage2
- C. storage1 and storage2 only
- D. VM1 and storage1 only, because the deployment fails when the template leaves out existing resources

<details><summary>Show answer</summary>

**B.** Incremental is the default deployment mode. It adds or updates the resources in the template and leaves everything else in the resource group alone.

- A is wrong because only complete mode deletes resources that the template does not list, and you did not choose it. Microsoft is gradually deprecating complete mode and recommends deployment stacks when a deployment must delete resources.
- C is wrong because no mode removes some unlisted resources and keeps others.
- D is wrong because a template does not have to describe every resource in the group.

Docs: [Azure Resource Manager deployment modes](https://learn.microsoft.com/en-us/azure/azure-resource-manager/templates/deployment-modes)

</details>

### Question 8

*Deploy and manage Azure compute resources*

VM1 and VM2 run in availability set AS1. You need to resize VM1 to a size that the hardware cluster hosting AS1 does not offer. What must you do before you can resize VM1?

- A. Remove VM1 from AS1, resize it, and add it back.
- B. Deallocate VM1 and VM2.
- C. Deallocate VM1 only.
- D. Nothing. Resizing a running VM moves it to a cluster that offers the size.

<details><summary>Show answer</summary>

**B.** When the new size is not available on the cluster that hosts the availability set, you must deallocate every VM in the set before you resize. After the resize you may need to change the size of the other VMs too.

- A is wrong because a VM can be added to an availability set only when it is created. Changing its availability set means deleting and recreating the VM.
- C is wrong because the whole set moves to hardware that offers the size, which requires all of its VMs to be deallocated.
- D is wrong because a running VM can be resized in place only to sizes that its current cluster offers.

Docs: [Resize a virtual machine](https://learn.microsoft.com/en-us/azure/virtual-machines/sizes/resize-vm), [Change the availability set for a VM](https://learn.microsoft.com/en-us/azure/virtual-machines/windows/change-availability-set)

</details>

### Question 9

*Deploy and manage Azure compute resources*

You run a nightly export as a container in Azure Container Instances. The container should run until the export finishes and then stop. If the process exits with a nonzero exit code, it should start again. Which restart policy should you set?

- A. Always
- B. OnFailure
- C. Never
- D. None. Leave the default restart policy.

<details><summary>Show answer</summary>

**B.** OnFailure restarts a container only when its process exits with an error, so a successful export ends the run.

- A is wrong because Always restarts the container even after a successful exit, so the export would run again and again.
- C is wrong because Never only guarantees that a container is not restarted after a successful exit. It does not promise a restart after a failure; the platform might restart a failed container, but you cannot rely on it.
- D is wrong because the default policy is Always.

Docs: [Restart policies for Azure Container Instances](https://learn.microsoft.com/en-us/azure/container-instances/container-instances-restart-policy)

</details>

### Question 10

*Deploy and manage Azure compute resources*

A web app runs in an App Service plan on the Basic tier. You need a staging deployment slot that you can swap with production, and rules that add instances when CPU usage is high. You want the cheapest tier that supports both. To which tier should you scale the plan?

- A. A larger Basic size
- B. Standard
- C. Premium v3
- D. Isolated v2

<details><summary>Show answer</summary>

**B.** Deployment slots need the Standard, Premium, or Isolated tier, and autoscale rules need Standard or higher. Standard is the lowest tier that offers both, with up to 5 slots and up to 10 instances.

- A is wrong because every Basic size lacks deployment slots and autoscale rules. Basic scales out by hand to at most 3 instances.
- C is wrong because Premium v3 supports both features but costs more than Standard.
- D is wrong because Isolated v2 supports both but runs on dedicated infrastructure and is the most expensive option.

Docs: [Set up staging environments in App Service](https://learn.microsoft.com/en-us/azure/app-service/deploy-staging-slots), [Scale up an app](https://learn.microsoft.com/en-us/azure/app-service/manage-scale-up), [Get started with autoscale](https://learn.microsoft.com/en-us/azure/azure-monitor/autoscale/autoscale-get-started)

</details>

### Question 11

*Implement and manage virtual networking*

VM1 runs a web server in Subnet1 and has a Standard public IP address. NSG1 is associated with Subnet1 and has an inbound rule at priority 200 that allows TCP 443 from the Internet service tag. NSG2 is associated with the network interface of VM1 and contains only the default rules. Users on the internet cannot reach VM1 on port 443. What should you do?

- A. Add an inbound rule to NSG2 that allows TCP 443 from the internet.
- B. Change the priority of the NSG1 rule to 100.
- C. Add an outbound rule to NSG1 that allows the return traffic on TCP 443.
- D. Turn on IP forwarding on the network interface of VM1.

<details><summary>Show answer</summary>

**A.** For inbound traffic, Azure applies the subnet NSG first and then the NIC NSG, and both must allow the traffic. NSG1 allows it, but NSG2 has only the default rules, so its DenyAllInbound rule at priority 65500 drops the request.

- B is wrong because NSG1 already allows the traffic. Its priority is not the problem.
- C is wrong because NSGs are stateful, so return traffic for an allowed connection needs no rule.
- D is wrong because IP forwarding lets a VM route traffic addressed to other destinations, as a network appliance does. It does not affect filtering.

Docs: [How network security groups filter traffic](https://learn.microsoft.com/en-us/azure/virtual-network/network-security-group-how-it-works), [Network security groups](https://learn.microsoft.com/en-us/azure/virtual-network/network-security-groups-overview)

</details>

### Question 12

*Implement and manage virtual networking*

VNet1 is peered with VNet2, and VNet2 is peered with VNet3. VNet2 contains no network virtual appliance and no gateway. VMs in VNet1 must communicate with VMs in VNet3. The address spaces do not overlap. What should you do?

- A. Turn on Allow gateway transit on the VNet2 peerings.
- B. Create a peering between VNet1 and VNet3.
- C. Add a service endpoint to every subnet in VNet1 and VNet3.
- D. Add a route table to the VNet1 subnets with a route to the VNet3 prefix and the next hop type Virtual network.

<details><summary>Show answer</summary>

**B.** Peering is not transitive. Being peered with the same network does not connect VNet1 and VNet3, so they need their own peering. In hub and spoke designs, the alternative is a network virtual appliance in the hub with user-defined routes.

- A is wrong because gateway transit shares a VPN or ExpressRoute gateway, and VNet2 has none.
- C is wrong because service endpoints connect a subnet to Azure services such as Storage, not to other virtual networks.
- D is wrong because the Virtual network next hop sends traffic within the VNet's own address space. A route cannot create a path that no peering provides.

Docs: [Virtual network peering](https://learn.microsoft.com/en-us/azure/virtual-network/virtual-network-peering-overview), [Create, change, or delete a peering](https://learn.microsoft.com/en-us/azure/virtual-network/virtual-network-manage-peering)

</details>

### Question 13

*Implement and manage virtual networking*

Storage1 has public network access disabled. On-premises servers connect to VNet1 through a site-to-site VPN. The servers must reach the blob service of storage1 over the VPN by the name `storage1.blob.core.windows.net`. Which two actions should you take? Choose two.

- A. Create a private endpoint for the blob subresource of storage1 in a subnet of VNet1.
- B. Turn on a Microsoft.Storage service endpoint on the subnets of VNet1.
- C. Configure DNS so that on-premises servers resolve `storage1.blob.core.windows.net` to the private endpoint's IP address, for example with a `privatelink.blob.core.windows.net` private DNS zone linked to VNet1 and conditional forwarding from on-premises DNS to a resolver in VNet1.
- D. Add the public IP address of the on-premises VPN device to the storage1 firewall.

<details><summary>Show answer</summary>

**A and C.** A private endpoint gives storage1 a private IP address in VNet1, and that address is reachable from on-premises over the VPN. Clients still use the normal name, so DNS must resolve it to the private IP address instead of the public one.

- B is wrong because service endpoints cannot carry traffic from on-premises networks to Azure services.
- D is wrong because the firewall allow list applies to the public endpoint, which is disabled, and that traffic would cross the internet instead of the VPN.

Docs: [What is a private endpoint](https://learn.microsoft.com/en-us/azure/private-link/private-endpoint-overview), [Private endpoint DNS integration](https://learn.microsoft.com/en-us/azure/private-link/private-endpoint-dns-integration), [Virtual network service endpoints](https://learn.microsoft.com/en-us/azure/virtual-network/virtual-network-service-endpoints-overview)

</details>

### Question 14

*Monitor and maintain Azure resources*

Your security team must be able to find out who deleted resources in Subscription1 at any point in the last 12 months. Today the oldest activity log entries are 90 days old. What should you do so that future entries stay available for a year?

- A. Change the activity log retention setting of Subscription1 to 365 days.
- B. Create a diagnostic setting that sends the subscription's activity log to a Log Analytics workspace that retains data for at least 365 days.
- C. Create an activity log alert rule for delete operations.
- D. Enable Network Watcher in every region that holds resources.

<details><summary>Show answer</summary>

**B.** Azure keeps activity log events for 90 days and then deletes them. To keep them longer, a diagnostic setting copies new entries to a destination such as a Log Analytics workspace, where you can query them with KQL. Entries already older than 90 days cannot be recovered.

- A is wrong because the 90 day retention of the activity log itself is fixed. Longer retention needs a diagnostic setting.
- C is wrong because an alert notifies you when an event happens but stores nothing for later queries.
- D is wrong because Network Watcher diagnoses network traffic. It does not record control plane operations.

Docs: [Azure Monitor activity log](https://learn.microsoft.com/en-us/azure/azure-monitor/fundamentals/activity-log), [Diagnostic settings](https://learn.microsoft.com/en-us/azure/azure-monitor/data-collection/diagnostic-settings)

</details>

### Question 15

*Monitor and maintain Azure resources*

Your VMs run in East US. You create a Recovery Services vault named RSV1 in West US. When you configure backup in RSV1, none of the East US VMs appear in the list of VMs to protect. What should you do?

- A. Create a Recovery Services vault in East US and configure backup from that vault.
- B. Create a Backup vault in West US and configure backup from it.
- C. Change the storage redundancy of RSV1 to GRS.
- D. Turn on Cross Region Restore in RSV1.

<details><summary>Show answer</summary>

**A.** A vault must be in the same region as the data source it protects. Only VMs in the vault's region can be selected.

- B is wrong because Backup vaults protect workloads such as Azure Disks, Azure Blobs, and Azure Database for PostgreSQL. Azure VMs back up to a Recovery Services vault, and the region rule still applies.
- C is wrong because the vault's storage redundancy controls where backup data is copied, not which VMs the vault can protect.
- D is wrong because Cross Region Restore lets you restore backups in the paired region. It does not let a vault protect VMs in another region.

Docs: [Back up Azure VMs in a Recovery Services vault](https://learn.microsoft.com/en-us/azure/backup/backup-azure-arm-vms-prepare), [Azure Backup FAQ](https://learn.microsoft.com/en-us/azure/backup/backup-azure-backup-faq)

</details>

## More practice

The [Examice AZ-104 practice bank](https://examice.com/exams/microsoft/az-104?utm_source=github&utm_medium=social&utm_campaign=az-104-study-guide-and-practice-questions&utm_content=link_3) has 600+ questions, each with a written explanation and a discussion. The first 5 are free, explanations included.
