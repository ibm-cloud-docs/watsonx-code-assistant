---

copyright:
   years: 2024
lastupdated: "2024-06-25"

keywords:

subcollection: watsonx-code-assistant
content-type: tutorial
completion-time: 20m

---

{{site.data.keyword.attribute-definition-list}}

# Setting up {{site.data.keyword.wcaej_short}}
{: #cloud-setup-wcaej}
{: toc-content-type="tutorial"}
{: toc-completion-time="20m"}

[{{site.data.keyword.wcaej_short}}]{: tag-purple}

As a cloud administrator, you must connect the service with a deployment space through {{site.data.keyword.cloud_notm}}. After you set up your environment, your users can enable Visual Studio Code to interact with {{site.data.keyword.wcaej_short}}.
{: shortdesc}

## Before you begin
{: #cloud-setup-wcaej-prereqs}

- Make sure that you have an [{{site.data.keyword.cloud_notm}} account](https://cloud.ibm.com/registration/){: external}.

- Provision an instance of {{site.data.keyword.wcaej_short}} through the [{{site.data.keyword.cloud_notm}} catalog](https://cloud.ibm.com/catalog){: external} page or by working with an IBM sales representative.

When you finish provisioning your instance, click **Setup** to open an onboarding checklist page to help you configure the instance. Or, you can select **Administration** and then **Setup** to access this onboarding checklist.

Items in that checklist correspond to each of the following steps. Click the action arrows on the checklist page that are associated with each item to complete the steps.

## Create a deployment space
{: #cloud-setup-wcaej-deploy-space}
{: step}

The deployment space is the serving environment for {{site.data.keyword.wcaej_short}}.

1. In your {{site.data.keyword.wcaej_short}} instance, click the **Navigation Menu** icon ![Navigation Menu](images/menu.svg), then select **Deployments**.

1. Click **New deployment space**.

1. Enter `Code Assistant` as the name for your deployment space. Optionally, enter a description.

1. In **Code assistant service**, select your instance name.

   ![Code assistant service](images/cloud-setup-wcaej-code-assistant-service.png){: caption="Code assistant service"}

1. Click **Create**.

1. A status window appears. After the space is created, click **Close**.

## Invite developers to your {{site.data.keyword.cloud_notm}} account
{: #cloud-setup-wcaej-invite-users}
{: step}

Use {{site.data.keyword.iamshort}} to invite developers to your {{site.data.keyword.cloud_notm}} account.

1. Open the Users page in [{{site.data.keyword.iamshort}}](/iam/users){: external}.

1. Click **Invite users**.

1. Enter the email addresses of the users that you want to provide full access to. Separate email addresses with commas, spaces, or line breaks.

1. Click **Invite**.

After you click **Submit**, any user that you invite receives an email to access the instance.

Ensure that each developer accepts the access invitation before you proceed to the next step of adding them to the deployment space.
{: note}

## Add developers to the deployment space
{: #cloud-setup-wcaej-add-users-deploy-space}
{: step}

After developers accept the invitation to your {{site.data.keyword.cloud_notm}} account, add them to the deployment space.

1. On the **Manage** tab of your deployment space, click **Access control**.

1. Click **Add collaborators** and select **Add users** from the menu.

1. Press the space bar to see a list of all users in your account.

1. Select the users that you want to add.

1. Choose the **Editor** role for each user, then click **Add**.

## Instruct developers to create an API key
{: #cloud-setup-wcaej-create-api-key}
{: step}

Each developer needs a personal API key to sign in to the extension for Microsoft Visual Studio Code or plugin for the Eclipse IDE. 

Use these instructions with your developers:

1. Sign in to [IBM Cloud API Keys](https://cloud.ibm.com/iam/apikeys){: external}

1. Click **Create**.

1. Enter `{{site.data.keyword.wca_full_notm}} API key` as the name for your API key. Optionally, enter a description.

1. Click **Create**.

1. Click **Download** or **Copy** and store the API key in a safe location.

   The key is only available for 296 seconds. Make sure to store it somewhere you can find it later.
   {: important} 

## Next step
{: #cloud-setup-wcaej-next_steps}

Developers can add the {{site.data.keyword.wca_short}} extension for Microsoft Visual Studio Code or plugin for the Eclipse IDE and start generating code recommendations. For more information, see the [private preview of {{site.data.keyword.wcaej_full_notm}}](https://early-access.ibm.com/software/support/trial/cst/welcomepage.wss?siteId=2044){: external}.
