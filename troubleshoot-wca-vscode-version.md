---

copyright:
  years: 2025
lastupdated: "2025-10-13"

keywords: 

subcollection: watsonx-code-assistant

content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}

# Why is the chat window not loading, and other features aren't working?
{: #troubleshoot-wca-vscode-version}
{: troubleshoot}
{: support} 

[{{site.data.keyword.wca_short}}]{: tag-blue}

In Visual Studio Code, the chat conversion window doesn't load, and other features aren't working.
{: shortdesc}

When you try to use the Visual Studio Code extension, these problems occur:
- The chat window doesn't load
- Features aren't working
- The WCA Language Server logs include the message `bad option: --use-system-ca`
{: tsSymptoms}

You're using an older version of Visual Studio Code.
{: tsCauses}

The {{site.data.keyword.wca_short}} extension is compatible with Visual Studio Code 1.101.1 and later, using Node.js version 22.15 or later.

To verify your Node.js version in Visual Studio Code, click the **Code** menu, then choose **About Visual Studio Code**. Make sure Node.js is version 22.15 or later.

For more information, see [Installing the extension for Visual Studio Code](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-cloud-setup-wca-vscode).
