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

# Getting started with {{site.data.keyword.wca_full_notm}}
{: #getting-started}
{: toc-content-type="tutorial"}
{: toc-completion-time="20m"}

{{site.data.keyword.wca_full}} facilitates writing code smartly and securely.
{: shortdesc}

Whether you're converting IBM Z COBOL into Java, or generating Red Hat Ansible code from your own prompts, {{site.data.keyword.wca_full_notm}} helps you to generate reliable and accurate code. {{site.data.keyword.wca_full_notm}} provides pre-trained models based on specific programming languages to ensure trust and efficiency for accurate code generation.

No matter which use case you choose, you must enable {{site.data.keyword.wca_full_notm}} to communicate with your local Visual Studio Code environment and to interoperate with any other language-specific third-party tools or extensions.

## Before you begin
{: #prereqs}

* Make sure you have an [{{site.data.keyword.cloud_notm}} account](https://cloud.ibm.com/registration/).

* Provision an instance of {{site.data.keyword.wca_full_notm}} through the [{{site.data.keyword.cloud_notm}} catalog](https://cloud.ibm.com/catalog) page or by working with an IBM sales representative. Your cloud administrator can provision an instance for your company.

## Set up {{site.data.keyword.wca_full_notm}} in {{site.data.keyword.cloud_notm}}
{: #setup}
{: step}

Your cloud administrator can complete the onboarding checklist to set up an instance of the {{site.data.keyword.wca_full_notm}} service in {{site.data.keyword.cloud_notm}}. The onboarding checklist simplifies the following setup tasks.

* Creating a service ID and API key to enable Visual Studio Code to communicate with the {{site.data.keyword.wca_full_notm}}.

* Setting up a Db2 database to store code input and output. ({{site.data.keyword.cloud_notm}} for Z only)

* Creating the serving environment for {{site.data.keyword.wca_full_notm}}.

* Adding authorized users to the {{site.data.keyword.wca_full_notm}} instance.

## Install the Visual Studio Code extension for your use case
{: #vsc}
{: step}

Depending on your use case, {{site.data.keyword.wca_full_notm}} provides code suggestions through a third-party Visual Studio Code extension. For example, {{site.data.keyword.wcaal_full_notm}}works with the [Ansible extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=redhat.ansible). **{{site.data.keyword.wca_full_notm}} for Z** works with the [IBM Z Open Editor](https://ibm.github.io/zopeneditor-about/).

For more information, see the documentation for your {{site.data.keyword.wca_full_notm}} use case.


## Enable {{site.data.keyword.wca_full_notm}} to connect with your local Visual Studio Code environment
{: #connect}
{: step}

1. When your cloud administrator adds you to the {{site.data.keyword.wca_full_notm}} instance, you receive an invitation to create or log in to an {{site.data.keyword.cloud_notm}} account and create an API key.
1. Provide this API key in the settings for your Visual Studio Code extension for your use case to enable {{site.data.keyword.wca_full_notm}} to provide code recommendations. If you are using {{site.data.keyword.wcaal_full_notm}}, you must also provide a Model ID, which your cloud administrator receives during the {{site.data.keyword.wca_full_notm}} setup process.

For more information, see the documentation for your {{site.data.keyword.wca_full_notm}} use case.

## Next steps
{: #anchor_value}

How you start coding with {{site.data.keyword.wca_full_notm}} depends on your use case:

[{{site.data.keyword.wca_full_notm}} for Z]{: tag-purple} For {{site.data.keyword.wca_full_notm}} for Z users, see [Refactoring and transforming COBOL code with IBM {{site.data.keyword.wca_full_notm}} for Z](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-wca4z).

[{{site.data.keyword.wcaal_full_notm}}]{: tag-red} For {{site.data.keyword.wcaal_full_notm}} users, see [Writing Ansible playbooks with AI-generated recommendations with {{site.data.keyword.wcaal_full_notm}}](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-wcaal).
