---

copyright:
  years: 2023
lastupdated: "2023-10-18"

keywords: responsibilities

subcollection: watson-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Understanding your responsibilities when using watsonx Code Assistant
{: #shared-resp}

Learn about the management responsibilities and terms and conditions that you have when you use {{site.data.keyword.wca_full}}.
{: #shortdesc}

Review the following sections for the specific responsibilities for you and for IBM when you use {{site.data.keyword.wca_full_notm}}. For the overall terms of use, see [IBM Cloud Notices](https://cloud.ibm.com/docs/overview?topic=overview-notices) and [IBM Cloud Terms of Use](https://cloud.ibm.com/docs/overview?topic=overview-terms). For a high-level view of the service types in IBM Cloud and the breakdown of responsibilities between the client and IBM for each type, see [Shared responsibilities for IBM Cloud offerings](https://cloud.ibm.com/docs/databases-for-postgresql?topic=databases-for-postgresql-responsibilities-cloud-databases).

## Incident and operations management
{: #incident-operation}

Incident and operations management includes tasks such as monitoring, event management, high availability, problem determination, recovery, and full state backup and recovery.

| Task | IBM responsibilities | Your responsibilities |
| --- | ----- | ----- |
| IBM Db2 | * For paid plans, perform daily encrypted backups of the database. Daily backups are kept for 14 days. \n * For Enterprise and Standard HADR plans, provide failover capability. | * Perform additional manual backups if required. \n * Perform end-of-backup and and point-in-time restore operations in the Db2 web console UI. |
{: caption="Table 1: Incident and operations management roles and responsibilities"}

## Change management
{: #change}

Change management includes tasks such as deployment, configuration, upgrades, patching, configuration changes, and deletion.

| Task | IBM responsibilities | Your responsibilities |
| --- | ----- | ----- |
| watsonx Code Assistant Service | * Provide updates for the watsonx Code Assistant service and base model. | * Subscribe to change notifications for watsonx Code Assistant in IBM Cloud. |
| IBM Db2 on Cloud: watsonx Code Assistant for IBM Z | * Ensure that watsonx Code Assistant for Z works with the current version of Db2 on Cloud. | * Provision a required plan level of Db2 on Cloud in your cloud account, and set up encryption of Db2 data and user management according to your policies. \n * Apply required updates for Db2 on Cloud. \n * Ensure network connectivity between your instance of Db2 on Cloud and watsonx Code Assistant. \n * Rotate the username and password for Db2 according to your requirements. \n * Update the Db2 connection in watsonx Code Assistant when the username and password change. |
| IBM Cloud Object Storage | * Ensure that watsonx Code Assistant works with the current version of IBM Cloud Object Storage. \n * Create Cloud Object Storage buckets within your Cloud Object Storage instance. | * Provision an instance of Cloud Object Storage with one of the required plans in your IBM Cloud account, and set up data encryption and user management according to your policies. \n * Grant watsonx Code Assistant access to your Cloud Object Storage instance to ensure that it can write and read from your Cloud Object Storage buckets. \n * Delete Cloud Object Storage buckets that were created by watsonx Code Assistant after you delete your instance of watsonx Code Assistant.  |
{: caption="Table 2: Change management roles and responsibilities"}

## Identity and access management
{: #iam}

Identity and access management includes tasks such as authentication, authorization, access control policies, and approving, granting, and revoking access.

| Task | IBM responsibilities | Your responsibilities |
| --- | ----- | ----- |
| IBM Cloud IAM | * Provide the function to restrict access to resources through the IBM Cloud console and REST APIs. | * Manage access to resources through IBM Cloud Identity and Access Management (IAM). |
| Service authentication: Ansible | * Ensure that only authenticated users have access to your instance of watsonx Code Assistant. | * Create a Service ID and API key, enter the API key into Red Hat Ansible Lightspeed, and safeguard your API key from unauthorized access. \n * Rotate and update your API keys according to your security policy requirements. |
| Service authentication: watsonx Code Assistant for IBM Z | * Ensure that only authenticated users have access to your instance of watsonx Code Assistant. | * Create a Service ID and API key, enter the API key into the IBM Open Editor for Z settings UI, and safeguard your API key from unauthorized access. \n * Rotate and update your API keys according to your security policy requirements. |
{: caption="Table 3: IAM roles and responsibilities"}

For more information about identity and access management, see [Managing IAM access for watsonx Code Assistant](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-wca-iam).

## Security and regulatory compliance
{: #sec}

Security and regulatory compliance includes tasks such as security controls implementation and compliance certification.

| Task | IBM responsibilities | Your responsibilities |
| --- | ----- | ----- |
| General | * Maintain controls commensurate to various industry compliance standards. \n * Monitor, isolate, and recover instances. \n * Monitor and report the health of instances in the various interfaces. \n * Secure cluster access through TLS/SSH (data plane in the IBM Services account). \n * Integrate watsonx Code Assistant with IBM Cloud Identity and Access Management (IAM). | * Set up and maintain security and regulation compliance for the watsonx Code Assistant instances. |
| Vulnerabilities | * Monitor stock images to detect vulnerability and security compliance issues. | * Keep informed about possible vulnerabilities and security issues through security bulletins that provide potential remediation actions. You can check out the [IBM Cloud status website](https://cloud.ibm.com/docs/get-support?topic=get-support-viewing-cloud-status) to find announcements and security bulletins about key events that affect the IBM Cloud platform, infrastructure, and major services. |
| Encryption | * Encrypt data when it is transmitted on any public networks and within the Cloud Service's private data center network. Encryption methods such as HTTPS, SSL, and TLS are used to protect data in motion. | * Ensure, as required, that your connection is encrypted end-to-end. |
{: caption="Table 4: Security and regulatory compliance roles and responsibilities"}

## Disaster recovery
{: #hadr}

Disaster recovery includes tasks such as providing dependencies on disaster recovery sites, provisioning disaster recovery environments, data and configuration backup, replicating data and configuration to the disaster recovery environment, and fail over on disaster events.

| Task | IBM responsibilities | Your responsibilities |
| --- | ----- | ----- |
| General | * Restore or rebuild the provisioning environments in the affected regions. \n * Restore existing watsonx Code Assistant instances, where possible.  | * Track instance state. \n * Provision new watsonx Code Assistant instances in alternatively available regions. |
| Service recovery | * Restore the watsonx Code Assistant service. | * No action required on your part. |
{: caption="Table 5: Disaster recovery roles and responsibilities"}

<!--For more information about disaster recovery with {{site.data.keyword.wca_full_notm}}, see Understanding business continuity and disaster recovery for watsonx Code Assistant.-->
