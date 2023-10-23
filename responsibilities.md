---

copyright:
  years: 2023
lastupdated: "2023-10-18"

keywords: responsibilities

subcollection: watson-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Shared responsibilities for watsonx Code Assistant
{: #shared-resp}

Learn about the management responsibilities and terms and conditions that you have when you use {{site.data.keyword.wca_full}}.
{: #shortdesc}

Review the following sections for the specific responsibilities for you and for IBM when you use {{site.data.keyword.wca_full_notm}}. For the overall terms of use, see [IBM Cloud Notices](https://cloud.ibm.com/docs/overview?topic=overview-notices) and [IBM Cloud Terms of Use](https://cloud.ibm.com/docs/overview?topic=overview-terms).

## Change management
{: #change}

Change management includes tasks such as deployment, configuration, upgrades, patching, configuration changes, and deletion.

| Resource | IBM Cloud role | Your role |
| --- | ----- | ----- |
| Applications | Provide major, minor, and patch version updates for the watsonx Code Assistant service and base model. | Use the console tools to apply the provided updates, including version updates, new features, and security patches. |
{: caption="Table 1: Change management roles and responsibilities"}

## Identity and access management
{: #iam}

Identity and access management includes tasks such as authentication, authorization, access control policies, and approving, granting, and revoking access.

| Resource | IBM Cloud role | Your role |
| --- | ----- | ----- |
| IBM Cloud IAM | IBM provides the function to restrict access to resources through the IBM Cloud console and REST APIs. | The Customer is responsible for managing access to resources through IBM Cloud Identity and Access Management (IAM). |
| Service authentication: Ansible | IBM provides a service ID and API key to interact with the watsonx Code Assistant service. | The Customer is responsible for creating the service ID and API key, entering it into the Lightspeed settings UI, and maintaining responsibility for this service ID. |
| Service authentication: IBM zSystems | IBM provides a service ID and API key to interact with the watsonx Code Assistant service. | The Customer is responsible for creating the service ID and API key, entering it into the IBM Open Editor for Z settings UI, and maintaining responsibility for this service ID. |
| User management: Ansible | IBM provides support for the number of users based on the service plan. | The Customer is responsible for managing user access in the Red Hat administration portal. |
| Observability | IBM provides integration of IBM Cloud Activity Tracker to audit records. | The Customer uses IBM Cloud Activity Tracker tools to monitor audit records. |
{: caption="Table 2: IAM roles and responsibilities"}

For more information about identity and access management, see [Managing IAM access for watsonx Code Assistant](/wca-iam.md).

## Security and regulatory compliance
{: #sec}

Security and regulatory compliance includes tasks such as security controls implementation and compliance certification.

| Resource | IBM Cloud role | Your role |
| --- | ----- | ----- |
| General | * Maintain controls commensurate to various industry compliance standards. \n * Monitor, isolate, and recover instances. \n * Monitor and report the health of instances in the various interfaces. \n *Secure cluster access through TLS/SSH (data plane in the IBM Services account). \n * Integrate watsonx Code Assistant with IBM Cloud Identity and Access Management (IAM). | Set up and maintain security and regulation compliance for the watsonx Code Assistant instances. |
| Compliance | IBM maintains controls commensurate to current industry compliance standards. IBM also maintains General Data Protection Regulation (GDPR) readiness for customer compliance. See [Understanding compliance in IBM Cloud](https://cloud.ibm.com/docs/overview?topic=overview-compliance) for more information. | The Customer is responsible for ensuring their own compliance with various laws and regulations, including the European Union General Data Protection Regulation. |
| Security features | IBM enables security features, such as encrypted disks. | The Customer uses the provided security features, such as restricting user access to the appropriate resources and resource groups. |
| Vulnerabilities | IBM continuously monitors stock images to detect vulnerability and security compliance issues. | The Customer is responsible for their education on possible vulnerabilities and security issues through security bulletins that describe actions to remediate any vulnerabilities. A Customer view the [IBM Cloud status website](https://cloud.ibm.com/docs/get-support?topic=get-support-viewing-cloud-status) to find announcements and security bulletin notifications about key events that affect the IBM Cloud platform, infrastructure, and major services. |
| Activity tracker | IBM provides logging and monitoring tools. | The Customer integrates IBM Cloud Activity Tracker and IBM Cloud Monitoring data into their auditing and monitoring processes. |
| Encryption | NEED CONTENT | The Customer ensures that their connection is encrypted end-to-end, if required. |
{: caption="Table 3: Security and regulatory compliance roles and responsibilities"}

## Disaster recovery
{: #hadr}

Disaster recovery includes tasks such as providing dependencies on disaster recovery sites, provisioning disaster recovery environments, data and configuration backup, replicating data and configuration to the disaster recovery environment, and fail over on disaster events.

| Resource | IBM Cloud role | Your role |
| --- | ----- | ----- |
| General | * Restore or rebuild the provisioning environments in the affected regions. \n * Restore existing watsonx Code Assistant instances, where possible.  | * Track instance state. \n * Provision new watsonx Code Assistant instances in alternatively available regions. \n * Ensure that the watsonx Code Assistant instance is stateless by making sure that all data, metadata, and applications reside outside of the cluster. This activity must be completed before disaster recovery can be initiated. \n * Provision a new service instance in an alternatively available region if the current instances can't be accessed. |
| Service recovery | IBM restores the watsonx Code Assistant service by re-creating missing pipelines, recovering Cloudant databases, and redeploying container images. | NEED CONTENT |
{: caption="Table 4: Disaster recovery roles and responsibilities"}

For more information about disaster recovery with {{site.data.keyword.wca_full_notm}}, see [Understanding business continuity and disaster recovery for watsonx Code Assistant](./bc-dr.md).
