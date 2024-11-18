---

copyright:
   years: 2024
lastupdated: "2024-11-14"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Setting up your {{site.data.keyword.wca_short}} service in {{site.data.keyword.cloud_notm}}
{: #cloud-setup-wca}



[{{site.data.keyword.wca_short}}]{: tag-blue}

Set up your service instance of {{site.data.keyword.wca_short}}.
{: shortdesc}

## Provision the service instance
{: #cloud-setup-wca-prereqs}

Use the [{{site.data.keyword.cloud_notm}} catalog](https://cloud.ibm.com/catalog/services/ibm-watsonx-code-assistant){: external} to provision a service instance of {{site.data.keyword.wca_short}}.

When you finish provisioning your instance, click **Setup** to open an onboarding checklist page to help you with configuration. Or, you can select **Administration**, and then **Setup** to access this onboarding checklist.

Items in the onboarding checklist correspond to each of the following steps. Click the action arrows on the checklist page that are associated with each item to complete the steps.

## Choose the installation type
{: #cloud-setup-wca-install-type}

The setup steps are different depending on how you're going to use the service instance.

| Type | Description |
| --- | --- |
| [Organizational users]{: tag-dark-teal} | Multiple developers |
| [Single user]{: tag-teal} | One developer |
{: caption="Installation types" caption-side="bottom"}

## Create an access group
{: #cloud-setup-wca-access-group}

[Organizational users]{: tag-dark-teal}

Create an access group where you can add your developers.

1. Open the **Access groups** page in [{{site.data.keyword.iamshort}}](/iam/groups){: external}.

1. Click **Create**.

1. Enter a name for your access group, for example `wca-instance-access`, and then click **Create**.

1. In your new access group, click the **Access** tab.

1. Click **Assign access** to start a policy.

1. For **Service**, select **{{site.data.keyword.wca_full_notm}}**, then click **Next**.

1. For **Resources**, select **Specific resources**.

1. Select the resource group where you created your instance, then click **Next**.

1. For **Resource Group Access**, select **Viewer**, then click **Next**.

1. For **Roles and actions**, select **Viewer**.

1. **Conditions** aren't required, so click **Add**.

1. In the **Access summary**, click **Assign**.

## Create a deployment space
{: #cloud-setup-wca-deploy-space}

[Single user]{: tag-teal} [Organizational users]{: tag-dark-teal}

The deployment space is the serving environment for {{site.data.keyword.wca_short}}.

1. In your {{site.data.keyword.wca_short}} instance, click the **Navigation Menu** icon ![Navigation Menu](images/menu.svg), then select **Deployments**.

1. Click **New deployment space**.

1. Enter `Code Assistant` as the name for your deployment space. Optionally, enter a description.

1. In **Code assistant service**, select your instance name.

   ![Code assistant service](images/cloud-setup-wcaej-code-assistant-service.png){: caption="Code assistant service"}

1. Click **Create**.

1. A status window appears. After the space is created, click **Close**.

## Add the access group to the deployment space
{: #cloud-setup-wca-access-group-to-deployment}

[Organizational users]{: tag-dark-teal}

Add your new access group to the deployment space.

1. In your {{site.data.keyword.wca_short}} instance, click the **Navigation Menu** icon ![Navigation Menu](images/menu.svg), then select **Deployments**.

1. Open the deployment space for your service instance.

1. On the **Manage** tab of your deployment space, click **Access control**.

1. Click **Add collaborators** and select **Add access groups** from the menu.

1. Select your new access group.

1. For **Role**, select **Editor**, then click **Add**.

## Select your license preferences for code suggestions
{: #cloud-setup-wca-licenses}

[Single user]{: tag-teal} [Organizational users]{: tag-dark-teal}

{{site.data.keyword.wca_short_cap}} checks whether a generated code suggestion is similar to other code sources. By default, the code suggestion includes a reference to the similar code source and its license. 

You can set how code suggestions are displayed in the IDE. For more information, see [Configuring how code suggestions are displayed](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-cloud-setup-configurations).

## Add developers to your access group
{: #cloud-setup-wca-invite-users}

[Organizational users]{: tag-dark-teal}

Use {{site.data.keyword.iamshort}} to add developers to your access group.

1. Open the **Access groups** page in [{{site.data.keyword.iamshort}}](/iam/groups){: external}.

1. Select the access group that you created.

1. On the **Users** tab, click **Add**.

1. Select the members of your {{site.data.keyword.cloud_notm}} account who should get access to {{site.data.keyword.wca_short}}.

1. Click **Add**.

## Instruct developers to add an IDE extension
{: #cloud-setup-wca-install-extension}

[Organizational users]{: tag-dark-teal}

Developers need to add the {{site.data.keyword.wca_short}} Microsoft Visual Studio Code extension or the Eclipse IDE plugin.

For the instructions, see [Installing the IDE extension](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-cloud-setup-wca-extensions).

Copy this link to send the instructions to your developers:

```html
https://cloud.ibm.com/docs/watsonx-code-assistant?topic=watsonx-code-assistant-cloud-setup-wca-extensions
```
{: codeblock}