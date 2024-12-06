---

copyright:
  years: 2023, 2024
lastupdated: "2024-12-06"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Securing your data in {{site.data.keyword.wca_short}}
{: #mng-data}

To ensure that you can securely manage your data when you use {{site.data.keyword.wca_short}}, it is important to know what data is stored and encrypted and how you can delete any stored data. Depending on your security requirements, you can encrypt data with customer-managed keys by integrating with {{site.data.keyword.cloud_notm}} key management services. Such services include {{site.data.keyword.keymanagementserviceshort}}, which supports the bring-your-own-key (BYOK) method, or {{site.data.keyword.hscrypto}}, which supports the keep-your-own-key (KYOK) method.
{: shortdesc}

## Securing your IDE extension setup
{: #mng-data-extensions}

[{{site.data.keyword.wca_short}}]{: tag-blue}

Developers should follow instructions to secure the setup of the {{site.data.keyword.wca_short}} IDE extension. 

For more information, see:

| IDE | Instructions |
| --- | --- |
| Visual Studio Code | [Securing your setup](https://cloud.ibm.com/docs/watsonx-code-assistant?topic=watsonx-code-assistant-cloud-setup-wca-vscode#cloud-setup-wca-vscode-securing) |
{: caption="Securing extension setup" caption-side="bottom"}


## How your data is stored and encrypted in {{site.data.keyword.wca_full_notm}}
{: #data-storage}

{{site.data.keyword.wca_short_cap}} stores customer-specific metadata, such as the connection asset for Db2, in a deployment space that the customer's cloud administrator creates. This space is reflected within {{site.data.keyword.cos_full_notm}} as a folder in a {{site.data.keyword.cos_short}} bucket. This bucket uses an {{site.data.keyword.cos_full_notm}} instance that is owned by the customer. The customer can encrypt this data at rest by BYOK, or use the automatic encryption with keys that are provided by {{site.data.keyword.cos_short}}. {{site.data.keyword.wca_short_cap}} accesses this data by using the customer-provided credentials. {{site.data.keyword.wca_short_cap}} has no way to access this data without these credentials.

### Configuring {{site.data.keyword.cos_full_notm}}
{: #cos-configure}

{{site.data.keyword.cos_full_notm}} provides storage for projects, catalogs, and deployment spaces. You are required to associate an {{site.data.keyword.cos_full_notm}} instance when you create projects, catalogs, or deployment spaces to store files for assets, such as uploaded data files or notebook files. The Lite plan instance is a no-cost option with storage capacity up to 25 GB per month.

You can also access data sources in an {{site.data.keyword.cos_full_notm}} instance. To access {{site.data.keyword.cos_full_notm}}, you create a {{site.data.keyword.cos_short}} connection when you want to connect to data stored in {{site.data.keyword.cos_short}}. A {{site.data.keyword.cos_short}} connection has a different purpose from the {{site.data.keyword.cos_short}} instance that you associate with a project, deployment space, or catalog. For more information, see [Getting started with {{site.data.keyword.cos_full_notm}}](https://cloud.ibm.com/docs/cloud-object-storage?topic=cloud-object-storage-getting-started-cloud-object-storage){: external}.

The {{site.data.keyword.iamshort}} service securely authenticates users and controls access to {{site.data.keyword.cos_full_notm}}. For instructions to set up access control for {{site.data.keyword.cos_full_notm}} on {{site.data.keyword.cloud}}, see [Getting Started with IAM](/docs/cloud-object-storage?topic=cloud-object-storage-iam){: external}.

### Encrypting data at rest
{: #dar-encrypt}

[Red Hat Ansible Lightspeed]{: tag-red}

By default, data at rest is encrypted with randomly generated keys that IBM manages. If the default keys are sufficient protection for your data, no additional action is needed. To provide more protection for at rest data, you can create and manage your own keys with [{{site.data.keyword.keymanagementservicefull}}](/docs/key-protect){: external}, which is an encryption solution that securely stores data in {{site.data.keyword.cos_full_notm}}.

For more information, see [Encrypting data with your own keys](/docs/overview?topic=overview-key-encryption){: external}.

### Encrypting data in motion
{: #dar-encrypt-motion}

 IBM encrypts data that is transmitted on any public networks and within the Cloud Service's private data center network. Encryption methods such as HTTPS, SSL, and TLS are used to protect data in motion.

### Event logging
{: #data-security-event-logging}

{{site.data.keyword.wca_full_notm}} services on {{site.data.keyword.cloud_notm}} do not have event logging available.
