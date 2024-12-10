
---

copyright:
   years: 2024
lastupdated: "2024-12-10"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Installing the plugin for the Eclipse IDE
{: #cloud-setup-wca-eclipse}



[{{site.data.keyword.wca_short}}]{: tag-blue}

Create an API key and add the {{site.data.keyword.wca_short}} plugin to your Eclipse IDE.
{: shortdesc}

## Compatibility
{: #cloud-setup-wca-eclipse-compatibility}

The plugin is compatible with:

- Eclipse IDE for Java Developers or Eclipse IDE for Enterprise Java and Web Developers
- Package [2024-06](https://www.eclipse.org/downloads/packages/release/2024-06/r){: external}
- On Windows, the plugin requires the Microsoft Edge WebView2 runtime. In newer versions of Windows this might already be installed.

## Create an API key on {{site.data.keyword.cloud_notm}}
{: #cloud-setup-wca-eclipse-create-api-key}

Instead of a username and password, each developer uses a personal API key to log in. 

To create an API key:

1. Log in to [{{site.data.keyword.cloud_notm}} API Keys](https://cloud.ibm.com/iam/apikeys){: external}

   Ensure you are using the {{site.data.keyword.cloud_notm}} account where your organization's instance of {{site.data.keyword.wca_short}} is provisioned.
   {: note}

1. Click **Create**.

1. Enter `{{site.data.keyword.wca_full_notm}} API key` as the name for your API key. Optionally, enter a description.

1. Click **Create**.

1. Click **Download** or **Copy** and store the API key in a safe location.

   The key is only available for 296 seconds. Make sure to store it somewhere where you can find it later.
   {: important} 

## Install the plugin
{: #cloud-setup-wca-eclipse-install}

The plugin that you need depends upon the plan you are using. For plan details, see the [Pricing plans page](https://cloud.ibm.com/catalog/services/ibm-watsonx-code-assistant){: external}.

The following table lists the plans and a description of each plan.

| Plan | Description |
| --- | --- |
| [Trial plan]{: tag-magenta} | Limited free trial with integrated generative AI chat for code |
| [Essentials plan]{: tag-green} | Integrated generative AI for code suggestions, code explanations, code documentation, and unit tests |
| [Standard plan]{: tag-purple} | All the features of the Essentials plan, plus enterprise Java modernization capabilities, enhanced code explanation, and enhanced unit test generation |
{: caption="Plugins by plan" caption-side="bottom"}

For complete plan details, see:
- [Pricing plans](https://www.ibm.com/products/watsonx-code-assistant/pricing){: external}
- [IBM Cloud catalog](https://cloud.ibm.com/catalog/services/ibm-watsonx-code-assistant){: external}.



### From the Eclipse Marketplace
{: #cloud-setup-wca-eclipse-install-marketplace}

To install the plugin from the Eclipse Marketplace:

1. Open your Eclipse IDE.

1. Choose the installation for the plan that you are using:

   - [Trial plan]{: tag-magenta} [Essentials plan]{: tag-green} To install the plugin for Trial and Essentials plans, open the [{{site.data.keyword.wca_short}}](https://marketplace.eclipse.org/content/watsonx-code-assistant){: external} page in the Eclipse Marketplace.
   

1. Click and drag the **Install** button into the workspace in your Eclipse IDE.

1. On Confirm Features, review the items, then click **Confirm**.

1. On Review Licenses, read the license, click to agree, then click **Finish**.

1. On Trust Authorities, click the checkbox, then click **Trust Selected**.

1. On Trust Artifacts, click the **Type** checkbox, then click **Trust Selected**.

1. You need to restart Eclipse. On Software Updates, click **Restart Now**.

### From the Eclipse IDE
{: #cloud-setup-wca-eclipse-install-ide}

To install the plugin from your Eclipse IDE:

1. In your Eclipse IDE, click the **Help** menu, then choose **Eclipse Marketplace**.

1. Choose the installation for the plan that you are using:

   - [Trial plan]{: tag-magenta} [Essentials plan]{: tag-green} To install the plugin for Trial and Essentials plans, search for `{{site.data.keyword.wca_short}}`.
   

1. Click the **Install** button for the plugin you need.

1. On Confirm Features, review the items, then click **Confirm**.

1. On Review Licenses, read the license, click to agree, then click **Finish**.

1. On Trust Authorities, click the checkbox, then click **Trust Selected**.

1. On Trust Artifacts, click the **Type** checkbox, then click **Trust Selected**.

1. You need to restart Eclipse. On Software Updates, click **Restart Now**.

## Open the plugin
{: #cloud-setup-wca-eclipse-open}

To open {{site.data.keyword.wca_short}}:

1. After Eclipse restarts, click **Window**, select **Show View**, then click **Other**.

1. In the Show View dialog, open the **{{site.data.keyword.wca_short}}** folder, select **Chat**, then click **Open**.

1. Click **Log in**, then enter your {{site.data.keyword.wca_full_notm}} API key.

## Setting up your enterprise Java environment
{: #cloud-setup-wca-eclipse-java-environment}

[Standard plan]{: tag-purple} If you're using the Standard plan and want to work with enterprise Java applications, you need to set up your environment. For more information, see [Setting up your enterprise Java environment](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-cloud-setup-wca-java-env).

## Securing your setup
{: #cloud-setup-wca-eclipse-securing}

{{site.data.keyword.wca_full_notm}} doesn't provide any additional security controls. Use these steps to properly secure your setup.

### Your Eclipse environment
{: #cloud-setup-wca-eclipse-securing-environment}

Apply all Eclipse IDE updates to help ensure you have the latest security and bug fixes.

The {{site.data.keyword.wca_short}} extension logs are stored in *.log files under `<your home directory>/.wca`. These files are not encrypted, other than the encryption that your file system provides. Safeguard the logs against improper access.

### Chat conversation storage
{: #cloud-setup-wca-eclipse-securing-storage}

{{site.data.keyword.wca_full_notm}} stores all your chat conversations locally in your file system in `<your home directory>/.wca/chat.db`, in a database format defined by [SQLite](https://www.sqlite.org/index.html){: external}. {{site.data.keyword.wca_full_notm}} does _not_ share these conversations with anyone. This file is not encrypted, other than the encryption that your file system provides. Safeguard this file against improper access.

### Telemetry data
{: #cloud-setup-wca-vscode-securing-telemtry}

{{site.data.keyword.wca_full_notm}} does _not_ collect any telemetry data. In general, {{site.data.keyword.wca_short}} doesn't send any data that it processes to a third party, IBM included.

## Log out of your API key
{: #cloud-setup-wca-eclipse-logout}

If necessary, you can log out of your API key. Logging out and reentering your API key might help with any authentication issues you might encounter.

To log out:

1. Open the chat.

1. Click the **Logout** icon.

## Uninstall the plugin
{: #cloud-setup-wca-eclipse-uninstall}

If you need to uninstall {{site.data.keyword.wca_short}}, follow these steps:

1. In your Eclipse editor, click **Help**, then click **Install New Software**.

1. Click **What is already installed?**.

1. On the **Installed Software** tab, select **{{site.data.keyword.wca_short}}**, then click **Uninstall**.

1. On Uninstall, review the items, then click **Finish**.

1. You need to restart Eclipse. On Software Updates, click **Restart Now**.
