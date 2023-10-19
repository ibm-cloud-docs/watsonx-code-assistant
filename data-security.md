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

## Deleting your data in {{site.data.keyword.wca_full_notm}}
{: #data-delete}



### Deleting {{site.data.keyword.wca_full_notm}} instances
{: #service-delete}


The {{site.data.keyword.wca_full_notm}} data retention policy describes how long your data is stored after you delete the service. The data retention policy is included in the {{site.data.keyword.wca_full_notm}} service description, which you can find in the [{{site.data.keyword.cloud_notm}} Terms and Notices](/docs/overview?topic=overview-terms).

### Restoring deleted data for {{site.data.keyword.wca_full_notm}}
{: #data-restore}
