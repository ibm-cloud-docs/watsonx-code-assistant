---

copyright:
  years:  2023, 2024
lastupdated: "2024-03-28"

keywords: security, privacy, foundation models, prompts

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}


# Data privacy and {{site.data.keyword.wcaz_full_notm}}
{: #wca-privacy-z}

[{{site.data.keyword.wcaz_short}}]{: tag-blue}

When you request code recommendations from {{site.data.keyword.wcaz_short}}, the prompt data that you submit is transient and IBM does not retain or use it for any other purpose.

## What data does {{site.data.keyword.wcaz_short}} collect?
{: #wca-z-data}

When you request a code recommendation, a prompt is sent to the service with the following information:

- The COBOL paragraph that you are requesting a recommendation for
- Metadata that provides content about your COBOL program

The following information clarifies how {{site.data.keyword.wcaz_short}} handles the data that it collects in each of these cases.

### The COBOL paragraph
{: #wca-z-prompt}

Although the prompt includes the code snippet that you are requesting a recommendation for, IBM does not store the input prompt in any way. It is transient information that is available in the memory of the {{site.data.keyword.wca_short}} microservices only during the request.

IBM does not:
- Use the input prompt to gather feedback about the model performance.
- Use the input prompt to improve models.
- Log the input prompt in any observability tools, whether as part of an explicit log message or as part of exception messages.

### The context data
{: #wca-z-context}

Your prompt also includes metadata on the overall COBOL program, which helps {{site.data.keyword.wcaz_short}} make more accurate recommendations in the context of your code. This metadata does not include the actual source code.

This metadata is stored in a Db2 instance on {{site.data.keyword.cloud_notm}}, which is both managed and provided by you.

Only the specific {{site.data.keyword.cloud_notm}} user and service IDs that you explicitly authorize have access to the Db2 instance that stores your metadata.

{{site.data.keyword.wca_short_cap}} does not cache the connection information for this Db2 instance in any way. The connection is retrieved specifically for each request, and kept in memory only during that particular request.
