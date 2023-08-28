---

copyright:
   years: 2023
lastupdated: "2023-8-24"

keywords:

subcollection: watson-code-assistant

content-type: tutorial
account-plan: lite
completion-time: 10m

---

{{site.data.keyword.attribute-definition-list}}

# Installing Watson Code Assistant in Visual Studio Code
{: #tutorial-install}
{: toc-content-type="tutorial"}
{: toc-completion-time="10m"}

In this tutorial, you learn how to install the IBM watsonx Code Assistant extension in Microsoft Visual Studio Code (VSC).
{: shortdesc}

## Installing the extension
{: #install-ext}
{: step}

Before you install the watsonx Code Assistant extension, you must have already installed VSC on your system. There is no standalone version of the extension. 

To install the watsonx Code Assistnat extension in VSC, complete the folllowing steps: 

1. Open VSC.
2. Click the Extensions icon ![VSC Extensions icon](../images/vsc_ext_icon.PNG) on the Primary sidebar.
3. Search for *watsonx Code Assistant* in the search box.
4. Click **Install**.

You have installed the extension and can start generating code.

## Verifying installation:
{: #verif-ext}
{: step}

To verify your installation, complete the following steps:

1. Create a new YAML file using the “.yml” or “.yaml” file extension.
2. Associate the Ansible language type with the new YAML file by clicking on the language indicator - which is located on the right hand of the Status Bar, and selecting *Ansible* from the dropdown.
3. Start writing a test playbook. You should see contextual aids as you create your content.
