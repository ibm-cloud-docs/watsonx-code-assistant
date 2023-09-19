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

# Getting started with watsonx Code Assistant
{: #getting-started}
{: toc-content-type="tutorial"}
{: toc-completion-time="20m"}

<!-- The title of your H1 should be Getting started with Watson Code Assistant, where Watson Code Assistant is the non-trademarked short version keyref. -->

<!-- The goal should be a tutorial of 10 minutes or less. -->

No matter which variant of IBM watsonx Code Assistant you want to use, you must provision instances of watsonx Code Assistant and IBM Db2. After you set up your environment, you can enable Visual Studio Code to interact with watsonx Code Assistant locally.
{: shortdesc}

## Before you begin
{: #prereqs}

Make sure you have an [{{site.data.keyword.cloud_notm}} account](https://cloud.ibm.com/registration/) and a w3id.

<!-- For each step in your tutorial, add an H2 section. The title should be task-oriented and descriptive. Recommendation is no more than 9 steps. -->

## Provision an instance
{: #provision}
{: step}

1. Go to the [{{site.data.keyword.cloud_notm}} catalog](https://cloud.ibm.com/catalog) page.

1. Find the **watsonx Code Assistant** tile and click it. You are redirected to the provisioning page.

1. Select a location from the list of available locations.

1. Select a pricing plan that aligns with your source code and expected use volume.

1. Enter the service name. The service name can be any string. This service name is used in the web console to identify the instance.

1. Optional: select a resource group. If you are organizing your services into resource groups, specify the resource group.

1. Optional: enter any tag or access management tag names.

1. Click **Create**.

   After you click **Create**, the system displays a message to say that the instance is being provisioned, which returns you to the **Resource list**. _From the **Resource list**, under the **Databases** category, you see that the status for your instance is, `Provision in progress`_.

1.  When the status changes to `Active`, select the instance.

1. Review the resource units and authorized users that you were allocated based on the pricing plan that you selected.

1. Click **Register and activate now**.

The system provisions a Cloud Object Storage Lite plan and creates a user profile. When your instance is ready, you are taken to a checklist page to help you prepare watsonx Code Assistant for your Visual Studio Code environment.

## Create a Service ID and API key
{: #apikey}
{: step}

1. On the [Service IDs](https://cloud.ibm.com/iam/serviceids) page, click **Create**.

1. Enter **watsonx Code Assistant user** as the name for your service ID. Optionally, enter a description.

1. Click **Create**.

   You are taken to the dashboard for your service ID, which includes tabs for **Access** and **API keys**.

1. Click the **API Keys** tab.

1. Click **Create**.

1. Enter **watsonx Code Assistant API key** as the name for your API key. Optionally, enter a description.

1. Click **Create**.

1. Click **Download** or **Copy** and store the API key in a safe location.

   You use this API key in a later step to enable Visual Studio Code to communicate with the watsonx Code Assistant service and serving environment.

## Sign up and create service credentials for Db2
{: #db2}
{: step}

1. Select a region from the list of available regions.

1. Review the preselected Db2 pricing plan.

   IBM Cloud preselects a pricing plan for watsonx Code Assistant instances.

1. Click **Create**.


## Create a deployment space and associate it with watsonx Code Assistant
{: #deploy_space}
{: step}

1. Enter **Code Assistant Models** as the name for your deployment space. Optionally, enter a description.

1. Click **Create**.

1. A status window appears. After the space is created, click **Close**.

   You are taken to a dashboard where you can associate your watsonx Code Assistant instance with the deployment space.

1. Click the **Manage** tab.

1. In the **watsonx Code Assistant** panel, click **Associate instance**.

1. In the **watsonx Code Assistant** panel, select **watsonx Code Assistant service** and click **Save**.

The instance is now associated with your deployment space.

## Add the service ID as a space collaborator
{: #space_cowboy}
{: step}

1. On the **Manage** tab of the **Code Assistant Models** page, select **Access control**.

1. Click **Add collaborators** and select **Add service IDs** from the menu.

   A list of service IDs that are associated with your account appears.

1. Select the checkbox for your **watsonx Code Assistant user** service ID.

1. Select an **Editor** for the role.

1. Click **Add**.

The service ID is added to the list of collaborators.

## Add the Db2 connection to your space
{: #your_space}
{: step}

1. On the **Code Assistant Models** page, select the **Assets** tab.

1. Click **Import Assets**.

1. On the **Data access** panel, click **Connection**.

1. Click **Import**.

1. On the **Connect to a data source** panel, select the **Deployed services** tab.

1. Select your **Db2-wz** service instance and click **Select**.

   A **Connect to a data source: IBM Db2 on Cloud** panel appears with pre-populated information from your service instance.

1. Click **Create**.

   If you did not set a location and sovereignty, a window appears where you can confirm that you want to create the connection without setting these values. To accept, click **Create**. If you need to set the values, click **Cancel** and select **Location and sovereignty**.



You deployed and connected your IBM Cloud components to your provisioned watsonx Code Assistant instance. You're ready to take your next steps by integrating watsonx Code Assistant with Microsoft Visual Studio Code environment for Ansible or Z.

## Next steps
{: #anchor_value}

Pick either Ansible or WCA4Z. For more information, see [WCA4Z](../usecase_products/wca4z.md).
