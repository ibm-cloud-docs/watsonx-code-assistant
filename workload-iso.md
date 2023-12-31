---

copyright:
  years: 2023
lastupdated: "2023-10-10"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Learning about watsonx Code Assistant architecture
{: #compute-isolation}

The architecture that your {{site.data.keyword.wca_full}} instance relies on depends on the use case that you implement.
{: shortdesc}

## {{site.data.keyword.wcaal_full_notm}} architecture
{: #architecture-a}

The following architectural diagram illustrates the architecture of the {{site.data.keyword.wcaal_full}} use case.

![Architectural diagram for {{site.data.keyword.wca_full_notm}}](./images/wca_arch.png){: caption="Architectural diagram for IBM watsonx Code Assistant"}

## {{site.data.keyword.wca_full_notm}} for Z architecture
{: #architecture-z}

For more information about the {{site.data.keyword.wca_full_notm}} for Z use case architecture, see [Solution architecture](https://ibm.com/docs/en/watsonx-code-assistant-4z/1.0?topic=overview-solution-architecture).

<!--
## {{site.data.keyword.wca_full_notm}} data isolation
{: #workload-isolation}

Workloads, in {{site.data.keyword.wca_full_notm}}, are shared across your organization. That is, you share microservices and resources.

[{{site.data.keyword.wcaal_full_notm}}]{: tag-red}

{{site.data.keyword.wcaal_full_notm}} does not keep or retain data.


[{{site.data.keyword.wca_full_notm}} for Z]{: tag-purple}

For {{site.data.keyword.wca_full_notm}} for Z, your application architect is responsible for supplying an instance of Db2 on IBM Cloud. They are responsible for associating that instance of Db2 with your instance of {{site.data.keyword.wca_full_notm}}.-->
