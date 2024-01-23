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

# Getting started with {{site.data.keyword.wca_full_notm}}
{: #getting-started}
{: toc-content-type="tutorial"}
{: toc-completion-time="20m"}

{{site.data.keyword.wca_full}} is a portfolio of purpose-built, generative AI-assisted products that are built to accelerate code and content generation and increase developer productivity, with trust, security, and compliance at its core. It provides pre-trained models based on specific programming languages to ensure trust and efficiency for accurate code and content generation.
{: shortdesc}

Your cloud administrator must set up a {{site.data.keyword.wca_full_notm}} instance in {{site.data.keyword.cloud}} and you must install and configure the Visual Studio Code extension for your use case.

## Before you begin
{: #prereqs}

* Make sure you have an [{{site.data.keyword.cloud_notm}} account](https://cloud.ibm.com/registration/).

* Provision an instance of {{site.data.keyword.wca_full_notm}} through the [{{site.data.keyword.cloud_notm}} catalog](https://cloud.ibm.com/catalog) page or by working with an IBM sales representative. Your cloud administrator can provision an instance for your company.

* Not all features apply to every pricing plan. For more information about which pricing plan you're on, see the [{{site.data.keyword.wca_full_notm}} catalog page]( https://cloud.ibm.com/catalog/services/ibm-watsonx-code-assistant).

## Set up {{site.data.keyword.wca_full_notm}} in {{site.data.keyword.cloud_notm}}
{: #setup}
{: step}

Your cloud administrator completes the onboarding checklist for your use case to set up an instance of the {{site.data.keyword.wca_full_notm}} service in {{site.data.keyword.cloud_notm}}. The onboarding checklist simplifies the following setup tasks.

* Creating a service ID and API key to access {{site.data.keyword.wca_full_notm}}.

* Setting up a Db2 database to store code input and output. ({{site.data.keyword.wca_full_notm}} for Z only)

* Creating the serving environment for {{site.data.keyword.wca_full_notm}}.

* Adding authorized users to the {{site.data.keyword.wca_full_notm}} instance. ({{site.data.keyword.wca_full_notm}} for Z only)

For more information, see the cloud setup documentation for your use case:

* [Set up {{site.data.keyword.wcaal_full_notm}} in {{site.data.keyword.cloud_notm}}](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-cloud-setup-a)

* [Set up {{site.data.keyword.wca_full_notm}} for Z in {{site.data.keyword.cloud_notm}}](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-cloud-setup-z)


## Install the Visual Studio Code extension for your use case
{: #vsc}
{: step}

Depending on your use case, {{site.data.keyword.wca_full_notm}} provides code suggestions through a third-party Visual Studio Code extension.

* {{site.data.keyword.wcaal_full_notm}} works with the [Ansible extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=redhat.ansible).
* {{site.data.keyword.wca_full_notm}} for Z works with the [IBM Z Open Editor](https://ibm.github.io/zopeneditor-about/).

## Provide the {{site.data.keyword.wca_full_notm}} resources for your use case
{: #connect}
{: step}

[{{site.data.keyword.wca_full_notm}} for Z]{: tag-purple}

If you are using {{site.data.keyword.wca_full_notm}} for Z, you must create an API key and provide it in the settings for your IBM Z Open Editor Visual Studio Code extension.

1. When your cloud administrator adds you to the {{site.data.keyword.wca_full_notm}} instance, you receive an invitation to create or log in to an {{site.data.keyword.cloud_notm}} account.
1. After you log in to your {{site.data.keyword.cloud_notm}} account, [create an API key](/docs/account?topic=account-userapikey&interface=ui) and store it in a safe location.
1. Provide this API key in the settings for your IBM Z Open Editor Visual Studio Code extension to enable {{site.data.keyword.wca_full_notm}} to provide code recommendations.

For more information, see [Set up watsonx Code Assistant for Z in IBM Cloud](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-cloud-setup-z).

[{{site.data.keyword.wcaal_full_notm}}]{: tag-red}

If you are using {{site.data.keyword.wcaal_full_notm}}, your cloud administrator must provide a Model ID and API Key in the Red Hat Ansible Lightspeed Admin Portal. For more information, see [Set up watsonx Code Assistant for Red Hat Ansible Lightspeed in IBM Cloud](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-cloud-setup-a).

## Next steps
{: #wca_next_steps}

To start coding with {{site.data.keyword.wca_full_notm}}, see the documentation for your use case:

[{{site.data.keyword.wca_full_notm}} for Z]{: tag-purple} [Refactoring and transforming COBOL code](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-wca4z)

[{{site.data.keyword.wcaal_full_notm}}]{: tag-red} [Writing Ansible playbooks with AI-generated recommendations](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-wcaal)
