
---

copyright:
   years: 2024
lastupdated: "2024-11-14"

keywords: 

subcollection: watsonx-code-assistant

content-type:

---

{{site.data.keyword.attribute-definition-list}}

# Configuring how code suggestions are displayed
{: #cloud-setup-configurations}



[{{site.data.keyword.wca_short}}]{: tag-blue}

{{site.data.keyword.wca_short_cap}} checks whether a generated code suggestion is similar to other code sources. The generated code must be:
- 10 or more lines
- Python, Java, JavaScript, Typescript, C++, C, or Go
{: shortdesc}

By default, {{site.data.keyword.wca_short}} blocks code suggestions that are similar to other code sources. You can set whether code suggestions that are similar to code from specific licenses are  displayed in the IDE with a reference to the similar code source and its license.

The code suggestion display is set per license. The choices are:

| Setting | Description |
| --- | --- |
| Block code suggestion (default) | No code suggestion |
| Show code suggestion with reference | Show the code suggestion with a license reference |
{: caption="Code similarity settings" caption-side="bottom"}

IBM recommends that you block the display of code suggestions that are similar to other code sources. If you choose to show code suggestions that are similar to other code sources with a reference, your eligibility for contractual IP protection (if available) under your customer agreement might be affected.
{: important}

To change settings:

1. Open your {{site.data.keyword.wca_short}} instance.

1. On the home page, click the **Settings for code generation licences** tile.

1. Select the licenses that you want to change.

1. Click the setting in the action bar. The action bar choices are **Block** or **Show with reference**. 

For a list of licenses that can be configured, see the [Code suggestion license reference](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-wca-license-reference).
