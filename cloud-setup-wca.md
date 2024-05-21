---

copyright:
   years: 2024
lastupdated: "2024-05-21"

keywords:

subcollection: watsonx-code-assistant
content-type: tutorial
completion-time: 20m

---

{{site.data.keyword.attribute-definition-list}}

# Setting up WCA@IBM
{: #cloud-setup-wca}
{: toc-content-type="tutorial"}
{: toc-completion-time="20m"}

[{{site.data.keyword.wcaz_short}}]{: tag-blue}

As a cloud administrator, you must generate an API key to connect the service with a deployment space through {{site.data.keyword.cloud_notm}}. After you set up your environment, your users can enable Visual Studio Code to interact with {{site.data.keyword.wcaz_short}}.
{: shortdesc}

## Before you begin
{: #cloud-setup-wca-prereqs}

- Make sure that you have an [{{site.data.keyword.cloud_notm}} account](https://cloud.ibm.com/registration/){: external}.

- Provision an instance of {{site.data.keyword.wca_short}} through the [{{site.data.keyword.cloud_notm}} catalog](https://cloud.ibm.com/catalog){: external} page or by working with an IBM sales representative.

When you finish provisioning your instance, click **Setup** to open an onboarding checklist page to help you configure the instance. Or, you can select **Administration** and then **Setup** to access this onboarding checklist.

Items in that checklist correspond to each of the following steps. Click the action arrows on the checklist page that are associated with each item to complete the steps.

## Create a Service ID and API key
{: #cloud-setup-wca-apikey}
{: step}

You can use this API key later to enable Visual Studio Code to communicate with {{site.data.keyword.wca_short}}.

1. On the [Service IDs](https://cloud.ibm.com/iam/serviceids){: external} page, click **Create**.

1. Enter `{{site.data.keyword.wca_full_notm}} user` as the name for your service ID. Optionally, enter a description.

1. Click **Create**.

   You are redirected to the dashboard for your service ID, which includes tabs for **Access** and **API keys**.

1. Click the **API Keys** tab.

1. Click **Create**.

1. Enter `{{site.data.keyword.wca_full_notm}} API key` as the name for your API key. Optionally, enter a description.

1. Click **Create**.

1. Click **Download** or **Copy** and store the API key in a safe location.

   The key is only available for 296 seconds. Make sure to store it somewhere you can find it later.
   {: important}

   Although {{site.data.keyword.wca_short}} supports allowing multiple users to share the API key for the Service ID, the best practice is for each user to have their own API key. For more information about adding users to your instance, see [Managing IAM access for {{site.data.keyword.wcaz_short}}](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-wca-iam).


