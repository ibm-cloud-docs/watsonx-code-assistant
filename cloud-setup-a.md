---

copyright:
   years: 2023, 2024
lastupdated: "2024-03-28"

keywords:

subcollection: watsonx-code-assistant
content-type: tutorial
completion-time: 20m

---

{{site.data.keyword.attribute-definition-list}}

# Setting up {{site.data.keyword.wcaal_short}} in {{site.data.keyword.cloud_notm}}
{: #cloud-setup-a}
{: toc-content-type="tutorial"}
{: toc-completion-time="20m"}

[{{site.data.keyword.wcaal_short}}]{: tag-red}

As a cloud administrator, you must generate an API key to connect your {{site.data.keyword.wcaal_short}} instance with a deployment space through {{site.data.keyword.cloud}}.
{: shortdesc}

## Before you begin
{: #prereqs-a}

- Make sure you have an [{{site.data.keyword.cloud_notm}} account](https://cloud.ibm.com/registration/){: external}.

- Provision an instance of {{site.data.keyword.wca_short}} through the [{{site.data.keyword.cloud_notm}} catalog](https://cloud.ibm.com/catalog){: external} page or by working with an IBM sales representative.

When you finish provisioning your instance, click **Setup** to open an onboarding checklist page to help you configure the instance. Or, you can select **Administration** and then **Setup** to access this onboarding checklist.

Items in that checklist correspond to each of the following steps. Click the action arrows on the checklist page that are associated with each item to complete the steps.

## Create a Service ID and API key
{: #sid_apikey}
{: step}

You use this API key later to enable Visual Studio Code to communicate with {{site.data.keyword.wca_short}}.

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

## Create a deployment space and model ID
{: #deploy_space-a}
{: step}

The deployment space is the serving environment for {{site.data.keyword.wca_short}}. The model ID determines which model generates code recommendations in the Ansible extension for Visual Studio Code.

1. Enter `Code Assistant Models` as the name for your deployment space. Optionally, enter a description.

1. Click **Create**.

1. A status window appears. After the space is created, click **Close**.

   Your instance is automatically associated with your new deployment space.

1. Copy your Model ID. After you create the deployment space, your Model ID is provided in a field after the **Create a deployment space** checklist item. Copy this ID and store it in a safe location as you need to add it to the Red Hat Ansible Lightspeed Admin portal in a later step.

## Add the service ID to the deployment space
{: #space_collab}
{: step}

Enable the API to connect to your deployment space.

1. On the **Manage** tab of the **Code Assistant Models** page, select **Access control**.

1. Click **Add collaborators** and select **Add service IDs** from the menu.

   A list of service IDs that are associated with your account appears.

1. Click the checkbox for your **{{site.data.keyword.wca_full_notm}} user** service ID and select **Editor** for the role.

1. Click **Add**.

   The service ID is added to the list of collaborators.

## Configure Red Hat Ansible Lightspeed to connect with {{site.data.keyword.wca_short}} and assign users access to it
{: #rh-admin}
{: step}

Add the API key and the model ID to the Red Hat Ansible Lightspeed Admin Portal to connect {{site.data.keyword.wca_short}} with the Ansible extension for Visual Studio Code. Then, you can assign seat licenses to users in your organization. Follow the onboarding checklist and the instructions from Red Hat.

- To add the API key and model ID to the Red Hat Ansible Lightspeed Admin Portal, see [Configuring Red Hat Ansible Lightspeed to connect with {{site.data.keyword.wcaal_full_notm}}](https://access.redhat.com/documentation/en-us/red_hat_ansible_lightspeed_with_ibm_watsonx_code_assistant/2.x_latest/html-single/red_hat_ansible_lightspeed_with_ibm_watsonx_code_assistant_user_guide/index#configure-code-assistant_lightspeed-user-guide){: external} in the Red Hat documentation.

- To assign seat licenses to users in your organization, see [Assigning and removing seat licenses](https://access.redhat.com/documentation/en-us/red_hat_ansible_lightspeed_with_ibm_watsonx_code_assistant/2.x_latest/html-single/red_hat_ansible_lightspeed_with_ibm_watsonx_code_assistant_user_guide/index#assigning-seat-licenses_lightspeed-user-guide){: external} in the Red Hat documentation.

## Create a project
{: #create-project}
{: step}

[Standard plan]{: tag-purple}

 If you purchased a [Standard plan](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-ansible-pricing#standard-plan), you can tune the IBM base code model with your own data so that it generates code suggestions that are customized for your organizational context. All your assets are stored in a project, including your uploaded data and tuned models. After you create a project, you can work with data and other resources to tune models.

1. On the resource page for your instance, click the navigation menu icon and select **Projects**.
1. Click **New project**.
1. Select **Create an empty project**
1. Enter a meaningful name and description for your project so you can easily identify it.

   Optionally, select control options:
   - **Mark as sensitive** prevents data from being moved out of the project.
   - **Allow reporting on asset metadata** allows system tools (like Reporting) to access and store metadata on assets in this project in an external database.
1. Click **Create**.

You're now ready to create a tuning experiment to tune the IBM base code model with your own data. For more information, see [Tuning the IBM base code model for {{site.data.keyword.wcaal_short}}](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-tutorial-tune-ansible).

## Next steps
{: #next_steps}

Follow the [instructions from Red Hat](https://access.redhat.com/documentation/en-us/red_hat_ansible_lightspeed_with_ibm_watsonx_code_assistant/2.x_latest/html-single/red_hat_ansible_lightspeed_with_ibm_watsonx_code_assistant_user_guide/index#configuring-with-code-assistant_lightspeed-user-guide){: external} to install and configure the Ansible extension for Visual Studio Code and start generating code recommendations.
