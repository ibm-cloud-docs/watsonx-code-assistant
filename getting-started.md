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

# Getting started
{: #getting-started}
{: toc-content-type="tutorial"}
{: toc-completion-time="20m"}

{{site.data.keyword.wca_full}} is a portfolio of purpose-built, generative AI-assisted products that are built to accelerate code and content generation and increase developer productivity, with trust, security, and compliance at its core. It provides pretrained models based on specific programming languages to provide trust and efficiency for accurate code and content generation.
{: shortdesc}

Your cloud administrator must set up a {{site.data.keyword.wca_short}} instance in {{site.data.keyword.cloud}} and you must install and configure the Visual Studio Code extension for your use case.

## Before you begin
{: #prereqs}

- Make sure you have an [{{site.data.keyword.cloud_notm}} account](https://cloud.ibm.com/registration/){: external}.

- Provision an instance of {{site.data.keyword.wca_short}} from the [{{site.data.keyword.cloud_notm}} catalog](https://cloud.ibm.com/catalog){: external} or by working with an IBM sales representative. Your cloud administrator can provision an instance for your company.

- Not all features apply to every pricing plan. For more information about your pricing plan, see the [{{site.data.keyword.wca_full_notm}} catalog page](https://cloud.ibm.com/catalog/services/ibm-watsonx-code-assistant){: external}.

## Set up {{site.data.keyword.wca_short}} in {{site.data.keyword.cloud_notm}}
{: #setup}
{: step}

Your cloud administrator completes the onboarding checklist for your use case to set up an instance of the {{site.data.keyword.wca_short}} service in {{site.data.keyword.cloud_notm}}. The onboarding checklist simplifies the following setup tasks:

- Create a service ID and API key.

- Set up a Db2 database to store code input and output. ({{site.data.keyword.wcaz_short}} only)

- Create the serving environment.

- Add authorized users to the {{site.data.keyword.wca_full_notm}} instance. ({{site.data.keyword.wcaz_short}} only)

For more information, see the cloud setup documentation for your use case:

- [Setting up {{site.data.keyword.wcaal_short}} in {{site.data.keyword.cloud_notm}}](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-cloud-setup-a)

- [Setting up {{site.data.keyword.wcaz_short}} in {{site.data.keyword.cloud_notm}}](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-cloud-setup-z)


## Install the Visual Studio Code extension for your use case
{: #vsc}
{: step}

Depending on your use case, {{site.data.keyword.wca_short}} provides code suggestions in a Visual Studio Code extension.

- {{site.data.keyword.wcaal_short_cap}} works with the [Ansible extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=redhat.ansible){: external}. Your cloud administrator must provide a Model ID and API Key in the Red Hat Ansible Lightspeed Admin Portal. For more information, see [Setting up {{site.data.keyword.wcaal_short}} in {{site.data.keyword.cloud_notm}}](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-cloud-setup-a).

- {{site.data.keyword.wcaz_full_notm}} works with the [IBM Z Open Editor](https://ibm.github.io/zopeneditor-about/){: external} extension.


## Provide the {{site.data.keyword.wca_full_notm}} resources for your use case
{: #connect}
{: step}

[{{site.data.keyword.wcaz_short}}]{: tag-blue}

If you are using {{site.data.keyword.wcaz_short}}, you must create an API key and provide it in the settings for your IBM Z Open Editor extension for Visual Studio Code.

1. When your cloud administrator adds you to the {{site.data.keyword.wca_short}} instance, you receive an invitation to create or log in.

1. After you log in to your account, [create an API key](/docs/account?topic=account-userapikey&interface=ui){: external} and store it in a safe location.

1. Provide this API key in the settings for your IBM Z Open Editor extension for Visual Studio Code to enable code recommendations.

For more information, see [Setting up {{site.data.keyword.wcaz_short}} in {{site.data.keyword.cloud_notm}}](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-cloud-setup-z).

## Next steps
{: #wca_next_steps}

To start coding, see the documentation for your use case:

[{{site.data.keyword.wcaz_short}}]{: tag-blue} [Refactoring and transforming COBOL code](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-wca4z)

[{{site.data.keyword.wcaal_short}}]{: tag-red} [Writing Ansible playbooks with AI-generated recommendations](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-wcaal)
