---

copyright:
  years: 2023
lastupdated: "2023-09-06"

keywords:

subcollection: watsonx-code-assistant
content-type: tutorial
completion-time: 20m

---

{{site.data.keyword.attribute-definition-list}}

# Set up {{site.data.keyword.wcaal_full_notm}} in {{site.data.keyword.cloud_notm}}
{: #cloud-setup-a}
{: toc-content-type="tutorial"}
{: toc-completion-time="20m"}

As a cloud administrator, you must generate an API key to connect your {{site.data.keyword.wcaal_full}} instance with a deployment space through {{site.data.keyword.cloud}}.
{: shortdesc}

## Before you begin
{: #prereqs-a}

* Make sure you have an [{{site.data.keyword.cloud_notm}} account](https://cloud.ibm.com/registration/).

* Provision an instance of {{site.data.keyword.wca_full_notm}} through the [{{site.data.keyword.cloud_notm}} catalog](https://cloud.ibm.com/catalog) page or by working with an IBM sales representative.

When you finish provisioning your {{site.data.keyword.wca_full_notm}} instance, you are redirected to an onboarding checklist page to help you configure the instance. Items in that checklist correspond to each of the following steps. Click the action arrows on the checklist page that are associated with each item to go to the {{site.data.keyword.cloud_notm}} pages where you complete the steps.

## Create a Service ID and API key
{: #sid_apikey}
{: step}

You use this API key later to enable Visual Studio Code to communicate with the {{site.data.keyword.wca_full_notm}}.

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



## Create a deployment space and model ID
{: #deploy_space-a}
{: step}

The deployment space is the serving environment for {{site.data.keyword.wca_full_notm}}. The model ID determines which model generates code recommendations in the Ansible VS Code Extension by Red Hat.

1. Enter **Code Assistant Models** as the name for your deployment space. Optionally, enter a description.

1. Click **Create**.

1. A status window appears. After the space is created, click **Close**.

   Your {{site.data.keyword.wca_full_notm}} instance is automatically associated with your new deployment space.

1. Copy your Model ID

   After you create the deployment space, your Model ID is provided in a field after the **Create a deployment space** checklist item. Copy this ID and store it in a safe location as you need to add it to the Red Hat Ansible Lightspeed Admin portal in a later step.


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

## Add the API key and Model ID to the Ansible Lightspeed Admin Portal
{: #rh-admin}
{: step}

Adding these resources in the Ansible Lightspeed Admin Portal connects {{site.data.keyword.wca_full_notm}} with the Ansible extension for Visual Studio Code and activates the model for your authorized users.

1. Follow the link in the onboarding checklist to the Ansible Lightspeed Admin Portal.

1. Log in with Red Hat single sign-on (SSO).

1. Select **Model settings** from the sidebar menu.

1. Enter the API key in the **IBM Cloud API Key** field and click **Update Key**.

1. Enter the Model ID in the **Model Id** field and click **Update Model Id**.


For more information, see [Configuring Red Hat Ansible Lightspeed to connect with IBM watsonx Code Assistant](https://access.redhat.com/documentation/en-us/red_hat_ansible_lightspeed_with_ibm_watsonx_code_assistant/2.x_latest/html-single/red_hat_ansible_lightspeed_with_ibm_watsonx_code_assistant_user_guide/index#configure-code-assistant_lightspeed-user-guide) in the Red Hat documentation.




<!--
## Create a project
{: #your_project}
{: step}



## Add the {{site.data.keyword.wca_full_notm}} instance to your project
{: #add_project}
{: step}
-->


## Next steps
{: #next_steps}

Follow the [instructions from Red Hat](https://access.redhat.com/documentation/en-us/red_hat_ansible_lightspeed_with_ibm_watsonx_code_assistant/2.x_latest/html-single/red_hat_ansible_lightspeed_with_ibm_watsonx_code_assistant_user_guide/index#assigning-seat-licenses_lightspeed-user-guide) to finish setting up the instance for your developers.

If you purchased a {{site.data.keyword.wcaal_full_notm}} Standard plan, you can tune the IBM base code model with your own data so that it generates code suggestions that are customized for your organizational context. For more information, see [Customizing IBM base code models for {{site.data.keyword.wcaal}}](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-tutorial-tune-ansible).

For more information about {{site.data.keyword.wcaal_full_notm}} purchasing and pricing plans, see the [{{site.data.keyword.wcaal}} product page](https://www.ibm.com/products/watsonx-code-assistant-ansible-lightspeed).
