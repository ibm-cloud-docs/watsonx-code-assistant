---

copyright:
   years: 2023, 2024
lastupdated: "2024-03-27"

keywords: responsibilities

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Understanding your responsibilities when you use {{site.data.keyword.wca_short}}
{: #shared-resp}

Learn about the management responsibilities and terms and conditions that you have when you use {{site.data.keyword.wca_short}}.
{: #shortdesc}

Review the following sections for the specific responsibilities for you and for IBM. For the overall terms of use, see [{{site.data.keyword.Bluemix_notm}} Notices](https://cloud.ibm.com/docs/overview?topic=overview-notices){: external} and [{{site.data.keyword.Bluemix_notm}} Terms of Use](https://cloud.ibm.com/docs/overview?topic=overview-terms){: external}. For a high-level view of the service types in {{site.data.keyword.Bluemix_notm}} and the breakdown of responsibilities between the client and IBM for each type, see [Shared responsibilities for {{site.data.keyword.Bluemix_notm}} offerings](https://cloud.ibm.com/docs/databases-for-postgresql?topic=databases-for-postgresql-responsibilities-cloud-databases){: external}.

## Incident and operations management
{: #incident-operation}

Incident and operations management includes tasks such as monitoring, event management, high availability, problem determination, recovery, and full state backup and recovery.

| Task | IBM responsibilities | Your responsibilities |
| --- | --- | --- |
| IBM Db2 | - For paid plans, provide daily encrypted backups of the database. Daily backups are kept for 14 days. \n - For Enterprise and Standard HADR plans, provide failover capability. | - Provide more manual backups if required. \n - Provide end-of-backup and point-in-time restore operations in the Db2 web console UI. |
{: caption="Incident and operations management roles and responsibilities"}

## Change management
{: #change}

Change management includes tasks such as deployment, configuration, upgrades, patching, configuration changes, and deletion.

| Task | IBM responsibilities | Your responsibilities |
| --- | ---- | ---- |
| {{site.data.keyword.wca_short}} Service | Provide updates for the {{site.data.keyword.wca_short}} service and base model. | Subscribe to change notifications for {{site.data.keyword.wca_short}}. |
| {{site.data.keyword.Db2_on_Cloud_long_notm}}: {{site.data.keyword.wcaz_short}} | Verify that {{site.data.keyword.wcaz_short}} works with the current version of {{site.data.keyword.Db2_on_Cloud_short}}. | - Provision a required plan level of {{site.data.keyword.Db2_on_Cloud_short}} in your cloud account, and set up encryption of Db2 data and user management according to your policies. \n - Apply required updates for {{site.data.keyword.Db2_on_Cloud_short}}. \n - Ensure network connectivity between your instance of {{site.data.keyword.Db2_on_Cloud_short}} and {{site.data.keyword.wca_short}}. \n - Rotate the username and password for Db2 according to your requirements. \n - Update the Db2 connection in {{site.data.keyword.wca_short}} when the username and password change. |
| {{site.data.keyword.cos_full_notm}} | - Verify that {{site.data.keyword.wca_short}} works with the current version of {{site.data.keyword.cos_full_notm}}. \n - Create {{site.data.keyword.cos_short}} buckets within your {{site.data.keyword.cos_short}} instance. | - Provision an instance of {{site.data.keyword.cos_short}} with one of the required plans in your {{site.data.keyword.Bluemix_notm}} account, and set up data encryption and user management according to your policies. \n - Grant {{site.data.keyword.wca_short}} access to your {{site.data.keyword.cos_short}} instance to ensure that it can write and read from your {{site.data.keyword.cos_short}} buckets. \n - Delete {{site.data.keyword.cos_short}} buckets that were created by {{site.data.keyword.wca_short}} after you delete your instance of {{site.data.keyword.wca_short}}.  |
{: caption="Change management roles and responsibilities"}

## Identity and access management
{: #iam}

Identity and access management includes tasks such as authentication, authorization, access control policies, and approving, granting, and revoking access.

| Task | IBM responsibilities | Your responsibilities |
| --- | ----- | ----- |
| {{site.data.keyword.iamshort}} (IAM) | Provide the function to restrict access to resources through the {{site.data.keyword.Bluemix_notm}} console and REST APIs. | Manage access to resources through {{site.data.keyword.iamshort}} (IAM). |
| Service authentication: Ansible | Ensure that only authenticated users have access to your instance of {{site.data.keyword.wca_short}}. | - Create a Service ID and API key, enter the API key into Red Hat Ansible Lightspeed, and safeguard your API key from unauthorized access. \n - Rotate and update your API keys according to your security policy requirements. |
| Service authentication: {{site.data.keyword.wcaz_short}} | Ensure that only authenticated users have access to your instance of {{site.data.keyword.wca_short}}. | - Create a Service ID and API key, enter the API key into the IBM Open Editor for Z settings UI, and safeguard your API key from unauthorized access. \n - Rotate and update your API keys according to your security policy requirements. |
{: caption="IAM roles and responsibilities"}

For more information about identity and access management, see [Managing IAM access for {{site.data.keyword.wca_short}}](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-wca-iam).

## Security and regulatory compliance
{: #sec}

Security and regulatory compliance includes tasks such as security controls implementation and compliance certification.

| Task | IBM responsibilities | Your responsibilities |
| --- | ----- | ----- |
| General | - Maintain controls commensurate to various industry compliance standards. \n - Monitor, isolate, and recover instances. \n - Monitor and report the health of instances in the various interfaces. \n - Secure cluster access through TLS/SSH (data plane in the IBM Services account). \n - Integrate {{site.data.keyword.wca_short}} with {{site.data.keyword.iamshort}} (IAM). | Set up and maintain security and regulation compliance for the {{site.data.keyword.wca_short}} instances. |
| Vulnerabilities | Monitor stock images to detect vulnerability and security compliance issues. | Keep informed about possible vulnerabilities and security issues through security bulletins that provide potential remediation actions. You can check out the [{{site.data.keyword.Bluemix_notm}} status website](https://cloud.ibm.com/docs/get-support?topic=get-support-viewing-cloud-status){: external} to find announcements and security bulletins about key events that affect the {{site.data.keyword.Bluemix_notm}} platform, infrastructure, and major services. |
| Encryption | Encrypt data when it is transmitted on any public networks and within the Cloud Service's private data center network. Encryption methods such as HTTPS, SSL, and TLS are used to protect data in motion. | Ensure, as required, that your connection is encrypted end-to-end. |
{: caption="Security and regulatory compliance roles and responsibilities"}

## Disaster recovery
{: #hadr}

Disaster recovery includes tasks such as providing dependencies on disaster recovery sites, provisioning disaster recovery environments, data and configuration backup, replicating data and configuration, and fail over on disaster events.

| Task | IBM responsibilities | Your responsibilities |
| --- | ----- | ----- |
| General | - Restore or rebuild the provisioning environments in the affected regions. \n - Restore existing {{site.data.keyword.wca_short}} instances, where possible. | - Track instance state. \n - Provision new {{site.data.keyword.wca_short}} instances in alternatively available regions. |
| Service recovery | - Restore the {{site.data.keyword.wca_short}} service. | - No action required on your part. |
{: caption="Disaster recovery roles and responsibilities"}
