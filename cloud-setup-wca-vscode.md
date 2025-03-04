---

copyright:
   years: 2024, 2025
lastupdated: "2025-03-04"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Installing the extension for Visual Studio Code
{: #cloud-setup-wca-vscode}

[{{site.data.keyword.wca_short}}]{: tag-blue}

Create an API key and add the {{site.data.keyword.wca_short}} extension to your Microsoft Visual Studio Code editor.
{: shortdesc}

## Compatibility
{: #cloud-setup-wca-vscode-compatibility}

The extension is compatible with Visual Studio Code 1.86.x and later.
{: note}

## Create an API key on {{site.data.keyword.cloud_notm}}
{: #cloud-setup-wca-vscode-create-api-key}

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

## Install the extension
{: #cloud-setup-wca-vscode-install}

Choose the installation for the plan that you are using.

The following table lists the plan, a description of the plan, and a link to the extension.

| Plan | Description | Extension name |
| --- | --- | --- |
| [Trial plan]{: tag-magenta} | Limited free trial with integrated generative AI chat for code | [{{site.data.keyword.wca_short}}](https://marketplace.visualstudio.com/items?itemName=IBM.wca-core){: external} |
| [Essentials plan]{: tag-green}| Integrated generative AI for code suggestions, code explanations, code documentation, and unit tests | [{{site.data.keyword.wca_short}}](https://marketplace.visualstudio.com/items?itemName=IBM.wca-core){: external} |
| [Standard plan]{: tag-purple} | All the features of the Essentials plan, plus enterprise Java modernization capabilities, enhanced code explanation, and enhanced unit test generation | [{{site.data.keyword.wcaej_short}}](https://marketplace.visualstudio.com/items?itemName=IBM.wca-eja){: external} |
{: caption="Plan descriptions" caption-side="bottom"}

For complete plan details, see:
- [Pricing plans](https://www.ibm.com/products/watsonx-code-assistant/pricing){: external}
- [IBM Cloud catalog](https://cloud.ibm.com/catalog/services/ibm-watsonx-code-assistant){: external}.

[Standard plan]{: tag-purple} For the Standard plan installation, two entries appear in your Visual Studio Code Extensions panel, one for {{site.data.keyword.wca_short}} and one for {{site.data.keyword.wcaej_short}}. The two extensions are dependencies for this installation.
{: note}

### From the Visual Studio Marketplace
{: #cloud-setup-wca-vscode-install-marketplace}

To install from the Visual Studio Marketplace:

1. Choose the installation for the plan that you are using.

   The following table lists the plan, a description of the plan, and a link to install the extension.

   - [Trial plan]{: tag-magenta} [Essentials plan]{: tag-green} To install for Trial and Essentials plans, open the [{{site.data.keyword.wca_short}}](https://marketplace.visualstudio.com/items?itemName=IBM.wca-core){: external} page in the Visual Studio Marketplace.
   - [Standard plan]{: tag-purple} To install for the Standard plan, open the [{{site.data.keyword.wcaej_short}}](https://marketplace.visualstudio.com/items?itemName=IBM.wca-eja){: external} page in the Visual Studio Marketplace.

1. Click **Install** on the Marketplace page.

1. In Visual Studio Code, click **Install** on the extension.

### From the Visual Studio Code editor
{: #cloud-setup-wca-vscode-install-editor}

To install from your Visual Studio Code editor:

1. In your Visual Studio Code editor, click the **Extensions** icon.

1. Choose the installation for the plan that you are using:

   - [Trial plan]{: tag-magenta} [Essentials plan]{: tag-green} To install for Trial and Essentials plans, search for `{{site.data.keyword.wca_short}}`.
   - [Standard plan]{: tag-purple} To install for the Standard plan, search for `{{site.data.keyword.wcaej_short}}`

1. Select the extension that you need, then click **Install**.

## Open the extension
{: #cloud-setup-wca-vscode-open}

To open {{site.data.keyword.wca_short}}:

1. Click the **{{site.data.keyword.wca_short}}** icon ![**{{site.data.keyword.wca_short}}** icon](images/wca-portfolio.svg).

1. Click **Log in**, then enter your {{site.data.keyword.wca_full_notm}} API key.

## Set up your enterprise Java environment
{: #cloud-setup-wca-vscode-java-environment}

[Standard plan]{: tag-purple} If you're using the Standard plan and want to work with enterprise Java applications, you need to set up your environment. For more information, see [Setting up your enterprise Java environment](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-cloud-setup-wca-java-env).

## Update HTTP proxy settings
{: #cloud-setup-wca-vscode-http-proxy}

If your organization uses an HTTP proxy server, you need to update your Visual Studio Code settings so that it can connect correctly. You might receive console errors when you try to connect and this setting is missing.

1. Open the [http.proxy setting](vscode://settings/http.proxy) in Visual Studio Code settings.
1. Enter the URL of your HTTP proxy server in a format such as `https://proxy_server:port`. You might need to include authentication information, such as `http://user:pass@proxy_server:port`.

## Secure your setup
{: #cloud-setup-wca-vscode-securing}

{{site.data.keyword.wca_full_notm}} doesn't provide any additional security controls. Use these steps to properly secure your setup.

### Your Visual Studio Code environment
{: #cloud-setup-wca-vscode-securing-environment}

Apply all Visual Studio Code updates to help ensure you have the latest security and bug fixes. For more information, see the [Microsoft Documentation](https://code.visualstudio.com/docs/setup/setup-overview){: external}.

The {{site.data.keyword.wca_short}} extension logs are stored in *.log files under `<your home directory>/.wca`. These files are not encrypted, other than the encryption that your file system provides. Safeguard the logs against improper access.

### Chat conversation storage
{: #cloud-setup-wca-vscode-securing-storage}

{{site.data.keyword.wca_full_notm}} stores all your chat conversations locally in your file system in `<your home directory>/.wca/chat.db`, in a database format defined by [SQLite](https://www.sqlite.org/index.html){: external}. {{site.data.keyword.wca_full_notm}} does _not_ share these conversations with anyone. This file is not encrypted, other than the encryption that your file system provides. Safeguard this file against improper access.

### Telemetry data
{: #cloud-setup-wca-vscode-securing-telemtry}

{{site.data.keyword.wca_full_notm}} does _not_ collect any telemetry data. In general, {{site.data.keyword.wca_short}} doesn't send any data that it processes to a third party, IBM included.

## How to log out of your API key
{: #cloud-setup-wca-vscode-logout}

If necessary, you can log out of your API key. Logging out and reentering your API key might help with any authentication issues you might encounter.

To log out:

1. In Visual Studio Code, click the **Accounts** icon.

1. Click the **Your Name (WCA API Key)** setting, then click **Sign out**.

## Use the Output view to see activity details
{: #cloud-setup-wca-output}

You can use the Output view of Visual Studio Code to see details about what the extension is doing and logging, and check for any errors. 

To open the Output view:

1. In Visual Studio Code, click **View**, then click **Output**.

1. In the Output view, use the dropdown menu to select **WCA** or **WCA Language Server**. Both provide more details about what the extension is doing.

To adjust the Output view and logging for the Visual Studio Code extension:

1. In Visual Studio Code, open the extension settings for {{site.data.keyword.wca_short}}.

1. In **Wca: Log level**, switch from the default of `INFO` to another setting such as `WARN`.

## How to disable or uninstall the extension
{: #cloud-setup-wca-vscode-uninstall}

If necessary, you can disable the extension and keep it installed, or you can uninstall it completely.

To disable or uninstall the extension:

1. In Visual Studio Code, click the **Extensions** icon to open the panel.

1. Click the **{{site.data.keyword.wca_short}}** extension.

1. Click **Disable** or **Uninstall**.
