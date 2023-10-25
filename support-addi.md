---

copyright:
  years: 2023
lastupdated: "2023-10-25"

keywords: responsibilities

subcollection: watson-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Supporting additional ADDI projects
{: #addi-supp}

{{site.data.keyword.wca_full}} can work with multiple ADDI projects in your organization.
{: shortdesc}

Each project requires:

* A dedicated Service ID
* A dedicated IBM Db2 instance

If you want to create an additional ADDI project, follow the same instructions as in [Set up {{site.data.keyword.wca_full_notm}} for Z in {{site.data.keyword.cloud_notm}}](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-cloud-setup-z), but make sure that you adhere to the following conditions:

* Create a new Service ID. Do not reuse the same Service ID for two ADDI projects.
* Create a new Db2 instance. Do not reuse the Db2 instance from your existing ADDI project.
* Create a new Deployment Space. Do not reuse the deployment space that you created for your existing ADDI project.
