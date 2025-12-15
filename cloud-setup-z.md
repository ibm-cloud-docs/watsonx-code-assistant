---

copyright:
   years: 2023, 2025
lastupdated: "2025-12-15"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Setting up your {{site.data.keyword.wcaz_short}} service in {{site.data.keyword.cloud_notm}}
{: #cloud-setup-z}

[{{site.data.keyword.wcaz_short}}]{: tag-dark-teal}

Set up your {{site.data.keyword.cloud_notm}} service instance of {{site.data.keyword.wcaz_short}} so you can use it with your full installation of the product.
{: shortdesc}

## Before you begin
{: #prereqs-z}

- Make sure that you have an [{{site.data.keyword.cloud_notm}} account](https://cloud.ibm.com/registration/){: external}.

- Provision an instance of {{site.data.keyword.wcaz_short}} through the [{{site.data.keyword.cloud_notm}} catalog](https://cloud.ibm.com/catalog/services/ibm-watsonx-code-assistant){: external} page or by working with an IBM sales representative. 

   The service is available in these data centers:
   - Dallas (`us-south`)
   - Frankfurt (`eu-de`)
   
   For more information about data centers, see the {{site.data.keyword.BluSoftlayer_notm}} documentation for [Service and infrastructure availability by location](/docs/overview?topic=overview-services_region){: external}.

- Download the most recent `IBM watsonx Code Assistant for Z Multiplatform Multilingual eAssembly` from [IBM Passport Advantage](https://www.ibm.com/software/passportadvantage/){: external}.

When you finish provisioning your instance, click **Setup** to open an onboarding checklist page to help you configure the instance. Or, you can select **Administration** and then **Setup** to access this onboarding checklist.

Items in that checklist correspond to each of the following steps. Click the action arrows on the checklist page that are associated with each item to complete the steps.

## Create a service ID
{: #service-id}

Create a service ID that will be used to connect the deployment space to the {{site.data.keyword.wca_short}} service.

1. On the [Service IDs](https://cloud.ibm.com/iam/serviceids){: external} page, click **Create**.

1. Enter `{{site.data.keyword.wca_full_notm}} user` as the name for your service ID. Optionally, enter a description.

1. Click **Create**.

   You are redirected to the dashboard for your service ID, which includes tabs for **Access** and **API keys**.

## Create a deployment space
{: #deploy_space-z}

The deployment space is the serving environment for {{site.data.keyword.wca_short}}.

1. In your {{site.data.keyword.wca_short}} instance, click the **Navigation Menu** ![Navigation Menu](images/menu.svg) icon, then select **Deployments**.

1. Click **New deployment space**.

1. Enter `Code Assistant` as the name for your deployment space. Optionally, enter a description.

1. In **Code assistant service**, select your instance.

1. Click **Create**.

1. A status window appears. After the space is created, click **Close**.

## Add the service ID as a space collaborator
{: #space_collab_z}

Enable the API to connect to your deployment space.

1. On the **Manage** tab of your deployment space, click **Access control**.

1. Click **Add collaborators** and select **Add service IDs** from the menu.

   A list of service IDs that are associated with your account appears.

1. Click the checkbox for the **{{site.data.keyword.wca_full_notm}} user** service ID that you created, and select **Editor** for the role.

1. Click **Add**.

   The service ID is added to the list of collaborators.

## Generate an API key
{: #apikey}

You need an API key to get Visual Studio Code to communicate with {{site.data.keyword.wca_short}}.

1. Navigate to the dashboard for your service ID. Find and click the **API keys** tab, then click **Create**.

1. Enter `{{site.data.keyword.wca_full_notm}} API key` as the name for your API key. Optionally, enter a description. Click **Create**.

1. Click **Download** or **Copy** and store the API key in a safe location.

   The key is only available for 296 seconds after creation. Make sure to store it somewhere you can find it later.
   {: important}

For more information on adding users and managing access, see [Managing IAM access for {{site.data.keyword.wcaz_short}}](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-wca-iam).

## Set up your network
{: #cloud-setup-z-network-setup}

To ensure that your developers can connect the IDE extension or plug-in, you need to allow access to {{site.data.keyword.cloud_notm}} URLs. Make sure your organization's network allows access to:

- `https://iam.cloud.ibm.com/`
- `https://api.dataplatform.cloud.ibm.com/`

## Next steps
{: #next_steps_z}

You deployed and connected your {{site.data.keyword.cloud_notm}} components to your provisioned {{site.data.keyword.wca_short}} instance. You're ready to take your next steps and integrate with your IBM Z Open Editor in Visual Studio Code. For information, see [Set up a development environment](https://www.ibm.com/docs/en/watsonx/watsonx-code-assistant-4z/latest?topic=transform-set-up-development-environment){: external}.
