---

copyright:
   years: 2023, 2024
lastupdated: "2024-03-25"

keywords:

subcollection: watsonx-code-assistant
content-type: tutorial
completion-time: 20m

---

{{site.data.keyword.attribute-definition-list}}

# Set up {{site.data.keyword.wcaz_full_notm}} in {{site.data.keyword.cloud_notm}}
{: #cloud-setup-z}
{: toc-content-type="tutorial"}
{: toc-completion-time="20m"}

As a cloud administrator, you must generate an API key to connect the {{site.data.keyword.wca_full}} for Z service with a deployment space through {{site.data.keyword.cloud_notm}}. After you set up your {{site.data.keyword.cloud_notm}} environment, your users can enable Visual Studio Code to interact with {{site.data.keyword.wca_full_notm}} for Z.
{: shortdesc}

## Before you begin
{: #prereqs-z}

- Make sure that you have an [{{site.data.keyword.cloud_notm}} account](https://cloud.ibm.com/registration/){: external}.

- Provision an instance of {{site.data.keyword.wca_short}} through the [{{site.data.keyword.cloud_notm}} catalog](https://cloud.ibm.com/catalog){: external} page or by working with an IBM sales representative.

When you finish provisioning your {{site.data.keyword.wca_short}} instance, click **Setup** to open an onboarding checklist page to help you configure the instance. Or, you can select **Administration** and then **Setup** to access this onboarding checklist.

Items in that checklist correspond to each of the following steps. Click the action arrows on the checklist page that are associated with each item to go to the {{site.data.keyword.cloud_notm}} pages where you complete the steps.

## Create a Service ID and API key
{: #apikey}
{: step}

You can use this API key later to enable Visual Studio Code to communicate with {{site.data.keyword.wca_short}}.

1. On the [Service IDs](https://cloud.ibm.com/iam/serviceids){: external} page, click **Create**.

1. Enter **{{site.data.keyword.wca_full_notm}} user** as the name for your service ID. Optionally, enter a description.

1. Click **Create**.

   You are redirected to the dashboard for your service ID, which includes tabs for **Access** and **API keys**.

1. Click the **API Keys** tab.

1. Click **Create**.

1. Enter **{{site.data.keyword.wca_full_notm}} API key** as the name for your API key. Optionally, enter a description.

1. Click **Create**.

1. Click **Download** or **Copy** and store the API key in a safe location.

   The key is only available for 296 seconds. Make sure to store it somewhere you can find it later.
   {: important}

   Although {{site.data.keyword.wca_short}} supports allowing multiple users to share the API key for the Service ID, the best practice is for each user to have their own API key. For more information about adding users to your instance, see [Managing IAM access for {{site.data.keyword.wcaz_short}}](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-wca-iam).


## Sign up for Db2 and create service credentials
{: #db2}
{: step}

{{site.data.keyword.wcaz_short_cap}} uses Db2 to store code input and output. If you don't already have an instance of Db2, {{site.data.keyword.cloud_notm}} can help you create one that is optimized for {{site.data.keyword.wcaz_short}}. If you already have a Db2 instance, you can skip this step.

1. Select a region from the list of available regions.

1. Review the preselected Db2 pricing plan.

   {{site.data.keyword.cloud_notm}} preselects a pricing plan for {{site.data.keyword.wca_short}} instances.

1. Click **Create**.


## Create a deployment space
{: #deploy_space-z}
{: step}

The deployment space is the serving environment for {{site.data.keyword.wca_short}}.

1. Enter **Code Assistant Models** as the name for your deployment space. Optionally, enter a description.

1. Click **Create**.

1. A status window appears. After the space is created, click **Close**.

Your {{site.data.keyword.wca_short}} instance is automatically associated with your new deployment space.

## Add the service ID as a space collaborator
{: #space_collab_z}
{: step}

Enable the API to connect to your deployment space.

1. On the **Manage** tab of the **Code Assistant Models** page, select **Access control**.

1. Click **Add collaborators** and select **Add service IDs** from the menu.

   A list of service IDs that are associated with your account appears.

1. Click the checkbox for your **{{site.data.keyword.wca_full_notm}} user** service ID and select **Editor** for the role.

1. Click **Add**.


The service ID is added to the list of collaborators.

## Add the Db2 connection to your space
{: #your_space}
{: step}

Enable the deployment space to send and retrieve code from Db2 storage.

1. On the **Code Assistant Models** page, select the **Assets** tab.

1. Click **Import Assets**.

1. On the **Import Assets** > **Data access** panel, click **Connection**.

1. Click **Import**.

1. On the **Connect to a data source** panel, select the **Deployed services** tab.

1. Select your **Db2-wz** service instance and click **Select**.

   A **Connect to a data source: IBM Db2 on Cloud** panel appears with pre-populated information from your service instance.

1. Click **Create**.

   If you did not set a location and sovereignty, a window appears where you can confirm that you want to create the connection without setting these values. To accept, click **Create**. If you need to set the values, click **Cancel** and select **Location and sovereignty**.

   If your database is on another IBM Cloud account, or if the automated population fails, see [Why can't I connect {{site.data.keyword.wcaz_short}} to my Db2 database?](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-troubleshoot-db2).

You deployed and connected your {{site.data.keyword.cloud_notm}} components to your provisioned {{site.data.keyword.wca_short} instance. You're ready to take your next steps and integrate with your Open Z Editor in Visual Studio Code.


## Next steps
{: #next_steps_z}

For information about setting up your development environment, see the [{{site.data.keyword.wcaz_full_notm}} documentation](https://www.ibm.com/docs/en/watsonx-code-assistant-4z/){: external}.
