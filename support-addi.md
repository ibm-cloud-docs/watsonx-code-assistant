---

copyright:
  years: 2023, 2024
lastupdated: "2024-03-26"

keywords: ADDI

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Supporting more ADDI projects
{: #addi-supp}

{{site.data.keyword.wca_full}} can work with multiple IBM Application Discovery and Delivery Intelligence (ADDI) projects in your organization.
{: shortdesc}

Each project requires:

* A dedicated Service ID
* A dedicated IBM Db2 instance

If you want to create an extra ADDI project, follow the same instructions as in [Set up {{site.data.keyword.wcaz_full_notm}} in {{site.data.keyword.cloud_notm}}](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-cloud-setup-z), but make sure that you create new:

- Service ID. Do not reuse the same Service ID for two ADDI projects.
- Db2 instance. Do not reuse the Db2 instance from your existing ADDI project.
- Deployment space. Do not reuse the deployment space that you created for your existing ADDI project.
