---

copyright:
  years: 2023
lastupdated: "2023-10-10"

keywords:

subcollection: watson-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Learning about watsonx Code Assistant architecture and data isolation
{: #compute-isolation}

Review the following sample architecture for {{site.data.keyword.wca_full}}, and learn more about different isolation levels so that you can choose the solution that best meets the requirements of the workloads that you want to run in the cloud.
{: shortdesc}

## {{site.data.keyword.wca_full_notm}} architecture
{: #architecture}

The following architectural diagram illustrates the architecture of the {{site.data.keyword.wcaal_full}} use case.

![Architectural diagram for {{site.data.keyword.wca_full_notm}}](./images/wca_arch.png){: caption="Architectural diagram for WCA"}

For more information about the {{site.data.keyword.wca_full_notm}} for Z use case's architecture, see [Solution architecture](https://ibm.com/docs/en/watsonx-code-assistant-4z/1.0?topic=overview-solution-architecture).

## {{site.data.keyword.wca_full_notm}} data isolation
{: #workload-isolation}

Workloads, in {{site.data.keyword.wca_full_notm}}, are shared across your organization. That is, you share microservices and resources.

[{{site.data.keyword.wcaal_full_notm}}]{: tag-red}

For {{site.data.keyword.wcaal_full_notm}}, NEED INPUT


[watsonx Code Assistant for Z]{: tag-purple}

For {{site.data.keyword.wca_full_notm}} for Z, your application architect is responsible for supplying an instance of Db2 on IBM Cloud. They are responsible for associating that instance of Db2 with your instance of {{site.data.keyword.wca_full_notm}}.
