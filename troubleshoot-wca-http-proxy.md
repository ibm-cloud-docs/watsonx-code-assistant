---

copyright:
  years: 2025
lastupdated: "2025-03-28"

keywords: 

subcollection: watsonx-code-assistant

content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}

# I receive console errors when I try to connect to {{site.data.keyword.wca_short}}
{: #troubleshoot-wca-http-proxy}
{: troubleshoot}
{: support} 

[{{site.data.keyword.wca_short}}]{: tag-blue}

You are unsuccessful when you try to connect to {{site.data.keyword.wca_short}} and receive console errors. 
{: shortdesc}

When you try to use the Visual Studio Code extension or Eclipse IDE plug-in, you can't connect and receive console errors that include `Request failed. AggregateError`.
{: tsSymptoms}

If your organization uses an HTTP proxy server, you need to update your Visual Studio Code or Eclipse IDE settings so that it can connect correctly. You might receive console errors when you try to connect and this setting is missing.
{: tsCauses}

For Visual Studio Code:
1. Open the [http.proxy setting](vscode://settings/http.proxy) in Visual Studio Code settings.
1. Enter the URL of your HTTP proxy server in the format `https://proxy_server:port`. You might need to include authentication information, such as `http://user:pass@proxy_server:port`.

For Eclipse IDE:
1. Open the Eclipse IDE settings.
1. In the General section, click **Network Connections**.
1. Set **Active Provider** to `Manual`.
1. Select the schema, such as `HTTPS`, then click **Edit**.
1. Enter the host URL and port of your HTTP proxy server.
1. If you need to include authentication information, click **Requires Authentication**, then enter your username and password.
1. Click **OK** to apply the changes.
