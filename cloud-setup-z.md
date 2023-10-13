---

copyright:
  years: 2023
lastupdated: "2023-09-06"

keywords:

subcollection: watson-code-assistant
content-type: tutorial
completion-time: 20m

---

{{site.data.keyword.attribute-definition-list}}

# Set up {{site.data.keyword.wca_full_notm}} for Z in {{site.data.keyword.cloud_notm}}
{: #cloud-setup}
{: toc-content-type="tutorial"}
{: toc-completion-time="20m"}

[{{site.data.keyword.wca_full_notm}} for Z]{: tag-purple}

You must generate an API key to connect the {{site.data.keyword.wca_full}} for Z service with a deployment space through {{site.data.keyword.cloud_notm}}. After you set up your {{site.data.keyword.cloud_notm}} environment, you can enable Visual Studio Code to interact with {{site.data.keyword.wca_full_notm}} for Z locally.
{: shortdesc}

## Before you begin
{: #prereqs}

* Make sure you have an [{{site.data.keyword.cloud_notm}} account](https://cloud.ibm.com/registration/).

* Provision an instance of **{{site.data.keyword.wca_full_notm}}** through the [{{site.data.keyword.cloud_notm}} catalog](https://cloud.ibm.com/catalog) page or by working with an IBM sales representative.

* Watch the _getting started video_, which walks through the process to integrate {{site.data.keyword.wca_full_notm}} with your {{site.data.keyword.cloud_notm}} and Visual Studio Code environments.

When you finish provisioning your **{{site.data.keyword.wca_full_notm}}** instance, you are redirected to an onboarding checklist page to help you prepare {{site.data.keyword.wca_full_notm}} for your Visual Studio Code environment. Items in that checklist correspond to each of the following steps. Click the action arrows that are associated with each checklist item to go to the IBM Cloud pages where you complete the steps.

## Create a Service ID and API key
{: #apikey}
{: step}

You can use this API key later to enable Visual Studio Code to communicate with the {{site.data.keyword.wca_full_notm}}.

1. On the [Service IDs](https://cloud.ibm.com/iam/serviceids) page, click **Create**.

1. Enter **{{site.data.keyword.wca_full_notm}} user** as the name for your service ID. Optionally, enter a description.

1. Click **Create**.

   You are redirected to the dashboard for your service ID, which includes tabs for **Access** and **API keys**.

1. Click the **API Keys** tab.

1. Click **Create**.

1. Enter **{{site.data.keyword.wca_full_notm}} API key** as the name for your API key. Optionally, enter a description.

1. Click **Create**.

1. Click **Download** or **Copy** and store the API key in a safe location.

   The key is only available from this panel for 296 seconds. Make sure to store it somewhere you can find it later.

   Although {{site.data.keyword.wca_full_notm}} supports allowing multiple users to share the API key for the Service ID, the best practice is for each user to have their own API key. For more information about adding users to your {{site.data.keyword.wca_full_notm}} instance, see [Managing IAM access for {{site.data.keyword.wca_full_notm}}](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-iam).


## Sign up for Db2 and create service credentials
{: #db2}
{: step}

{{site.data.keyword.wca_full_notm}} for Z uses Db2 to store code input and output. If you don't already have an instance of Db2, {{site.data.keyword.cloud_notm}} can help you create one that is optimized for {{site.data.keyword.wca_full_notm}} for Z. If you already have a Db2 instance, or if you don't plan to use {{site.data.keyword.wca_full_notm}} for Z, you can skip this step.

1. Select a region from the list of available regions.

1. Review the preselected Db2 pricing plan.

   {{site.data.keyword.cloud_notm}} preselects a pricing plan for {{site.data.keyword.wca_full_notm}} instances.

1. Click **Create**.


## Create a deployment space
{: #deploy_space}
{: step}

The deployment space is the serving environment for {{site.data.keyword.wca_full_notm}}.

1. Enter **Code Assistant Models** as the name for your deployment space. Optionally, enter a description.

1. Click **Create**.

1. A status window appears. After the space is created, click **Close**.

Your {{site.data.keyword.wca_full_notm}} instance is automatically associated with your new deployment space.

## Add the service ID as a space collaborator
{: #space_cowboy}
{: step}

Enable the API to connect to your deployment space.

1. On the **Manage** tab of the **Code Assistant Models** page, select **Access control**.

1. Click **Add collaborators** and select **Add service IDs** from the menu.

   A list of service IDs that are associated with your account appears.

1. Click the checkbox for your **{{site.data.keyword.wca_full_notm}} user** service ID and select **Editor** for the role.

1. Click **Add**


The service ID is added to the list of collaborators.

## Add the Db2 connection to your space
{: #your_space}
{: step}

[{{site.data.keyword.wca_full_notm}} for Z]{: tag-purple} This step is for {{site.data.keyword.wca_full_notm}} for Z only.

If you plan to use {{site.data.keyword.wca_full_notm}} for Z, enable the deployment space to send and retrieve code from Db2 storage.

1. On the **Code Assistant Models** page, select the **Assets** tab.

1. Click **Import Assets**.

1. On the **Import Assets** > **Data access** panel, click **Connection**.

1. Click **Import**.

1. On the **Connect to a data source** panel, select the **Deployed services** tab.

1. Select your **Db2-wz** service instance and click **Select**.

   A **Connect to a data source: IBM Db2 on Cloud** panel appears with pre-populated information from your service instance.

1. Click **Create**.

   If you did not set a location and sovereignty, a window appears where you can confirm that you want to create the connection without setting these values. To accept, click **Create**. If you need to set the values, click **Cancel** and select **Location and sovereignty**.

You deployed and connected your {{site.data.keyword.cloud_notm}} components to your provisioned {{site.data.keyword.wca_full_notm}} instance. You're ready to take your next steps and integrate {{site.data.keyword.wca_full_notm}} with your Open Z Editor in Visual Studio Code.

## Next steps
{: #anchor_value}

To get started coding with {{site.data.keyword.wca_full_notm}} for Z, you must enable your instance to connect to Open Z Editor in your local Visual Studio Code environment. For more information, see [Refactoring and transforming COBOL code with IBM {{site.data.keyword.wca_full_notm}} for Z].
