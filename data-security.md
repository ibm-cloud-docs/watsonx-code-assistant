---

copyright:
  years: 2023
lastupdated: "2023-10-11"

keywords:

subcollection: watson-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Securing your data in {{site.data.keyword.wca_full_notm}}
{: #mng-data}


To ensure that you can securely manage your data when you use {{site.data.keyword.wca_full}}, it is important to know what data is stored and encrypted and how you can delete any stored data. Depending on your security requirements, you can encrypt data with customer-managed keys by integrating with {{site.data.keyword.cloud_notm}} key management services. Such services include {{site.data.keyword.keymanagementserviceshort}}, which supports the bring-your-own-key (BYOK) method, or {{site.data.keyword.hscrypto}}, which supports the keep-your-own-key (KYOK) method.
{: shortdesc}


## How your data is stored and encrypted in {{site.data.keyword.wca_full_notm}}
{: #data-storage}

{{site.data.keyword.wca_full_notm}} stores customer-specific metadata, such as the connection asset for Db2, in a deployment space that the customer's cloud administrator creates. This space is reflected within IBM Cloud Object Storage as a folder in a Cloud Object Storage bucket. This bucket uses a Cloud Object Storage instance that is owned by the customer. The customer can encrypt this data at rest by BYOK, or use the automatic encryption with keys that are provided by IBM Cloud Object Storage. {{site.data.keyword.wca_full_notm}} accesses this data by using the customer-provided credentials. {{site.data.keyword.wca_full_notm}} has no way to access this data without these credentials.

### Configuring Cloud Object Storage
{: #cos-configure}

IBM Cloud Object Storage provides storage for projects, catalogs, and deployment spaces. You are required to associate an IBM Cloud Object Storage instance when you create projects, catalogs, or deployment spaces to store files for assets, such as uploaded data files or notebook files. The Lite plan instance is free to use for storage capacity up to 25 GB per month.

You can also access data sources in an IBM Cloud Object Storage instance. To access IBM Cloud Object Storage, you create an IBM Cloud Object Storage connection when you want to connect to data stored in IBM Cloud Object Storage. An IBM Cloud Object Storage connection has a different purpose from the IBM Cloud Object Storage instance that you associate with a project, deployment space, or catalog. For more information, see [Getting started with IBM Cloud Object Storage](https://cloud.ibm.com/docs/cloud-object-storage?topic=cloud-object-storage-getting-started-cloud-object-storage).

The IBM Cloud Identity and Access Management (IAM) service securely authenticates users and controls access to IBM Cloud Object Storage. For instructions to set up access control for Cloud Object Storage on IBM Cloud, see [Getting Started with IAM](/docs/cloud-object-storage?topic=cloud-object-storage-iam).

### Encrypting data at rest
{: #dar-encrypt}

By default, data at rest is encrypted with randomly generated keys that IBM manages. If the default keys are sufficient protection for your data, no additional action is needed. To provide extra protection for at rest data, you can create and manage your own keys with [{{site.data.keyword.keymanagementservicefull}}](/docs/key-protect). {{site.data.keyword.keymanagementserviceshort}} is a full-service encryption solution that allows data to be secured and stored in IBM Cloud Object Storage.

For more information, see [Encrypting data with your own keys](/docs/overview?topic=overview-key-encryption).

### Encrypting data in motion
{: #dar-encrypt-motion}

 IBM encrypts data that is transmitted on any public networks and within the Cloud Service's private data center network. Encryption methods such as HTTPS, SSL, and TLS are used to protect data in motion.


## Deleting your data in {{site.data.keyword.wca_full_notm}}
{: #data-delete}



### Deleting {{site.data.keyword.wca_full_notm}} instances
{: #service-delete}

The {{site.data.keyword.wca_full_notm}} data retention policy describes how long your data is stored after you delete the service. The data retention policy is included in the {{site.data.keyword.wca_full_notm}} service description, which you can find in the [{{site.data.keyword.cloud_notm}} Terms and Notices](/docs/overview?topic=overview-terms).

### Restoring deleted data for {{site.data.keyword.wca_full_notm}}
{: #data-restore}
