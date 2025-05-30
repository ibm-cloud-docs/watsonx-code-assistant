---

copyright:
   years: 2023, 2025
lastupdated: "2025-05-30"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Setting up your {{site.data.keyword.wcaal_short}} service in {{site.data.keyword.cloud_notm}}
{: #cloud-setup-a}

[Red Hat Ansible Lightspeed]{: tag-red}

Set up your {{site.data.keyword.cloud_notm}} service instance of {{site.data.keyword.wcaal_short}} so you can use it with your full installation of Red Hat Ansible Lightspeed.
{: shortdesc}

## Before you begin
{: #prereqs-a}

- Make sure you have an [{{site.data.keyword.cloud_notm}} account](https://cloud.ibm.com/registration/){: external}.

- Provision an instance of {{site.data.keyword.wcaal_short}} through the [{{site.data.keyword.cloud_notm}} catalog](https://cloud.ibm.com/catalog/services/ibm-watsonx-code-assistant){: external} page or by working with an IBM sales representative. 

   The service is available in these data centers:
   - Dallas (`us-south`)
   - Frankfurt (`eu-de`) 
    (Model tuning not available)

   For more information about data centers, see the {{site.data.keyword.BluSoftlayer_notm}} documentation for [Service and infrastructure availability by location](https://cloud.ibm.com/docs/overview?topic=overview-services_region){: external}.

When you finish provisioning your instance, click **Setup** to open an onboarding checklist page to help you configure the instance. Or, you can select **Administration** and then **Setup** to access this onboarding checklist.

Items in that checklist correspond to each of the following steps. Click the action arrows on the checklist page that are associated with each item to complete the steps.

## Create a service ID and API key
{: #sid_apikey}

You use this API key later to enable Visual Studio Code to communicate with {{site.data.keyword.wca_short}}.

1. On the [Service IDs](https://cloud.ibm.com/iam/serviceids){: external} page, click **Create**.

1. Enter `{{site.data.keyword.wca_full_notm}} user` as the name for your service ID. Optionally, enter a description.

1. Click **Create**.

   You are redirected to the dashboard for your service ID, which includes tabs for **Access** and **API keys**.

1. Click the **API keys** tab.

1. Click **Create**.

1. Enter `{{site.data.keyword.wca_full_notm}} API key` as the name for your API key. Optionally, enter a description.

1. Click **Create**.

1. Click **Download** or **Copy** and store the API key in a safe location.

   The key is only available for 296 seconds. Make sure to store it somewhere you can find it later.
   {: important}

## Create a deployment space and model ID
{: #deploy_space-a}

The deployment space is the serving environment for {{site.data.keyword.wca_short}}. The model ID determines which model generates code recommendations in the Ansible extension for Visual Studio Code.

1. In your {{site.data.keyword.wca_short}} instance, click the **Navigation Menu** icon ![Navigation Menu](images/menu.svg), then select **Deployments**.

1. Click **New deployment space**.

1. Enter `Code Assistant Models` as the name for your deployment space. Optionally, enter a description.

1. In **Code assistant service**, select your instance name.

1. Click **Create**.

1. A status window appears. After the space is created, click **Close**.

1. Copy your model ID. After you create the deployment space, your model ID is provided in a field after the **Create a deployment space** checklist item. Copy this ID and store it in a safe location as you need to add it to the Red Hat Ansible Lightspeed Admin portal in a later step.

## Add the service ID to the deployment space
{: #space_collab}

Enable the API to connect to your deployment space.

1. On the **Manage** tab of your deployment space, click **Access control**.

1. Click **Add collaborators** and select **Add service IDs** from the menu.

   A list of service IDs that are associated with your account appears.

1. Click the checkbox for the **{{site.data.keyword.wca_full_notm}} user** service ID that you created, and select **Editor** for the role.

1. Click **Add**.

   The service ID is added to the list of collaborators.

## Configure Red Hat Ansible Lightspeed to connect with {{site.data.keyword.wca_short}}
{: #rh-admin}

Add the API key and the model ID to the Red Hat Ansible Lightspeed Admin Portal to connect {{site.data.keyword.wca_short}} with the Ansible extension for Visual Studio Code. Follow the onboarding checklist and the instructions from Red Hat.

To add the API key and model ID to the Red Hat Ansible Lightspeed Admin Portal, see [Configuring Red Hat Ansible Lightspeed cloud service](https://docs.redhat.com/en/documentation/red_hat_ansible_lightspeed_with_ibm_watsonx_code_assistant/2.x_latest/html/red_hat_ansible_lightspeed_with_ibm_watsonx_code_assistant_user_guide/set-up-lightspeed_lightspeed-user-guide#obtain-config-wca-and-model-id_configure-lightspeed-cloud-service){: external} in the Red Hat documentation.

## Add the instance to a project
{: #create-project}

[Standard plan]{: tag-purple}

If you purchased a [Standard plan](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-ansible-pricing#standard-plan), you can tune the IBM base code model with your own data so that it generates code suggestions that are customized for your organizational context. All your assets are stored in a project, including your uploaded data and tuned models. After you create a project, you can work with data and other resources to tune models.


1. In your {{site.data.keyword.wca_short}} instance, click the **Navigation Menu** icon ![Navigation Menu](images/menu.svg), then select **Projects**.

1. Click **New project**.

1. Enter a meaningful name and description for your project so you can easily identify it.

1. Click **Create**.

1. In the new project, click the **Manage** tab, then select **Services & integrations**.

1. Click **Associate service**.

1. Select your instance, then click **Associate**.

You're now ready to create a tuning experiment to tune the IBM base code model with your own data. For more information, see [Tuning the IBM base code model for {{site.data.keyword.wcaal_short}}](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-tutorial-tune-ansible).

## Set up your network
{: #cloud-setup-a-network-setup}

To ensure that your developers can connect the IDE extension or plug-in, you need to allow access to {{site.data.keyword.cloud_notm}} URLs. Make sure your organization's network allows access to:

- `https://iam.cloud.ibm.com/`
- `https://api.dataplatform.cloud.ibm.com/`

## Next steps
{: #next_steps}

See [Installing and configuring the Ansible VS Code extension](https://docs.redhat.com/en/documentation/red_hat_ansible_lightspeed_with_ibm_watsonx_code_assistant/2.x_latest/html/red_hat_ansible_lightspeed_with_ibm_watsonx_code_assistant_user_guide/developing-ansible-content_lightspeed-user-guide#con-configure-vs-code-extension_developing-ansible-content){: external} to start generating code recommendations.
