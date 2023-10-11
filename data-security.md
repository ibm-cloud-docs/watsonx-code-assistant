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


To ensure that you can securely manage your data when you use {{site.data.keyword.wca_full}} , it is important to know exactly what data is stored and encrypted and how you can delete any stored data. Depending on your security requirements, you can encrypt data with customer-managed keys by integrating with {{site.data.keyword.cloud_notm}} key management services such as {{site.data.keyword.keymanagementserviceshort}}, which supports the bring your own key (BYOK) method, or {{site.data.keyword.hscrypto}}, which supports the keep your own key (KYOK) method.
{: shortdesc}


## How your data is stored and encrypted in {{site.data.keyword.wca_full_notm}}
{: #data-storage}

_


## Protecting your sensitive data in {{site.data.keyword.wca_full_notm}}
{: #data-encryption}



### About customer-managed keys
{: #about-encryption}

{{site.data.keyword.wca_full_notm}}  uses [envelope encryption](#x9860393){: term} to implement customer-managed keys. Envelope encryption describes encrypting one encryption key with another encryption key. The key used to encrypt the actual data is known as a [data encryption key (DEK)](#x4791827){: term}. The DEK itself is never stored but is wrapped by a second key that is known as the key encryption key (KEK) to create a wrapped DEK. To decrypt data, the wrapped DEK is unwrapped to get the DEK. This process is possible only by accessing the KEK, which in this case is your root key that is stored in {{site.data.keyword.keymanagementserviceshort}} or {{site.data.keyword.hscrypto}}.

You own the KEK, which you create as a root key in the {{site.data.keyword.keymanagementserviceshort}} or {{site.data.keyword.hscrypto}} service. The {{site.data.keyword.wca_full_notm}}  service never sees the root (KEK) key. Its storage, management, and use to wrap and unwrap the DEK is performed entirely within the key management service. If you disable or delete the key, the data can no longer be decrypted.

{{site.data.keyword.keymanagementserviceshort}} keys are secured by FIPS 140-2 Level 3 certified cloud-based [hardware security modules (HSMs)](#x6704988){: term}. For more information, see [Bringing your encryption keys to the cloud](/docs/key-protect?topic=key-protect-importing-keys).

{{site.data.keyword.hscrypto}} is a single-tenant, dedicated hardware security module that is controlled by you. {{site.data.keyword.hscrypto}} features KYOK encryption capabilities backed by FIPS 140-2 Level 4-certified hardware, which is the highest offered by any cloud provider in the industry. For more information, see [Getting started with {{site.data.keyword.hscrypto}}](/docs/hs-crypto?topic=hs-crypto-get-started).


### Enabling customer-managed keys for {{site.data.keyword.wca_full_notm}}
{: #using-byok}


### Working with customer-managed keys for {{site.data.keyword.wca_full_notm}}
{: #working-with-keys}


You can use {{site.data.keyword.cloudaccesstraillong}} to audit the lifecycle events of your keys, such as creating a key, deleting a key, rotating a key, and more. For more information, see [{{site.data.keyword.cloudaccesstraillong_notm}} events for {{site.data.keyword.keymanagementserviceshort}}](/docs/key-protect?topic=key-protect-at-events) and [{{site.data.keyword.cloudaccesstraillong_notm}} events for {{site.data.keyword.hscrypto}}](/docs/hs-crypto?topic=hs-crypto-at-events).
{: tip}

## Deleting your data in {{site.data.keyword.wca_full_notm}}
{: #data-delete}



### Deleting {{site.data.keyword.wca_full_notm}}  instances
{: #service-delete}


The {{site.data.keyword.wca_full_notm}}  data retention policy describes how long your data is stored after you delete the service. The data retention policy is included in the _service-name_ service description, which you can find in the [{{site.data.keyword.cloud_notm}} Terms and Notices](/docs/overview?topic=overview-terms).

### Restoring deleted data for {{site.data.keyword.wca_full_notm}}
{: #data-restore}
