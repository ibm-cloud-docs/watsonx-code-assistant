---

copyright:
  years: 2025
lastupdated: "2025-02-28"

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

When you try to use the Visual Studio Code extension, you can't connect and receive console errors that include `Request failed. AggregateError`.
{: tsSymptoms}

If your organization uses an HTTP proxy server, you need to update your Visual Studio Code settings so that it can connect correctly. You might receive console errors when you try to connect and this setting is missing.
{: tsCauses}

1. Open the [http.proxy setting](vscode://settings/http.proxy) in Visual Studio Code settings.
1. Enter the URL of your HTTP proxy server in a format such as `https://proxy_server:port`. You might need to include authentication information, such as `http://user:pass@proxy_server:port`.
{: tsResolve}
