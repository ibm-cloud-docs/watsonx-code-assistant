
---

copyright:
   years: 2024
lastupdated: "2024-11-19"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Installing the extension for Visual Studio Code
{: #cloud-setup-wca-vscode}



[{{site.data.keyword.wca_short}}]{: tag-blue}

Create an API key and add the {{site.data.keyword.wca_short}} extension to your Microsoft Visual Studio Code editor.
{: shortdesc}

## Create an API key on {{site.data.keyword.cloud_notm}}
{: #cloud-setup-wca-vscode-create-api-key}

Instead of a username and password, each developer uses a personal API key to sign in to the extension for Microsoft Visual Studio Code. 

To create an API key:

1. Log in to [{{site.data.keyword.cloud_notm}} Keys](https://cloud.ibm.com/iam/apikeys){: external}

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




| Plan | Description |
| --- | --- |
| [Trial plan]{: tag-magenta} | Limited free trial with integrated generative AI chat for code |
| [Essentials plan]{: tag-green}| Integrated generative AI for code suggestions, code explanations, code documentation, and unit tests |
{: caption="Plan descriptions" caption-side="bottom"}


### From the Visual Studio Marketplace
{: #cloud-setup-wca-vscode-install-marketplace}

To install from the Visual Studio Marketplace:

1. Choose the installation for the plan that you are using:

   - [Trial plan]{: tag-magenta} [Essentials plan]{: tag-green} To install the extension for Trial and Essentials plans, open the [{{site.data.keyword.wca_short}}](https://marketplace.visualstudio.com/items?itemName=IBM.wca-core){: external} page in the Visual Studio Marketplace
   


1. Click **Install** on the Marketplace page.

1. In Visual Studio Code, click **Install** on the extension.

### From the Visual Studio Code editor
{: #cloud-setup-wca-vscode-install-editor}

To install from your Visual Studio Code editor:

1. In your Visual Studio Code editor, click the **Extensions** icon.

1. Choose the installation for the plan that you are using:

   - [Trial plan]{: tag-magenta} [Essentials plan]{: tag-green} To install for Trial and Essentials plans, search for `{{site.data.keyword.wca_short}}`.
   

1. Select the extension that you need, then click **Install**.

## Open the extension
{: #cloud-setup-wca-vscode-open}

To open {{site.data.keyword.wca_short}}:

1. Click the **{{site.data.keyword.wca_short}}** icon ![images](/images/wca-portfolio.svg).

1. Click **Log in**, then use your {{site.data.keyword.wca_full_notm}} API key to sign in.





## Securing your setup
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

## Log out of your API key
{: #cloud-setup-wca-vscode-logout}

If necessary, you can log out of your API key.

To log out:

1. In Visual Studio Code, click the **Accounts** icon.

1. Click the **Your Name (WCA API Key)** setting, then click **Sign out**.

## Disable or uninstall the extension
{: #cloud-setup-wca-vscode-uninstall}

If necessary, you can disable the extension and keep it installed, or you can uninstall it completely.

To disable or uninstall the extension:

1. In Visual Studio Code, click the **Extensions** icon to open the panel.

1. Click the **{{site.data.keyword.wca_short}}** extension.

1. Click **Disable** or **Uninstall**.
