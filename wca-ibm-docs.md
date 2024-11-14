
---

copyright:
   years: 2024
lastupdated: "2024-11-14"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Getting answers from IBM documentation
{: #wca-ibm-docs}



[{{site.data.keyword.wca_short}}]{: tag-blue}

Use chat to ask questions that reference IBM and Red Hat product documentation.
{: shortdesc}

This feature requires an {{site.data.keyword.cloud_notm}} Trial, Essentials, or Standard plan. It isn't available if you are using Ollama to access a local IBM Granite model.
{: note}

## Chat syntax for documentation questions
{: #wca-ibm-docs-syntax}

The chat syntax is:
`/docs [collection:<collection_name>] <your question>`

The `collection_name` is optional. If no collection is specified, `ibm_docs` is used.

Available documentation collections are:

| Collection | Source | URL reference |
| --- | --- | --- |
| `ibm_docs` | IBM Documentation | https://www.ibm.com/docs/en |
| `redhat` | Red Hat Documentation | https://docs.redhat.com/products |
| `ibm_redbooks` | IBM Redbooks | https://www.redbooks.ibm.com/ |
| `cloud_docs` | IBM Cloud Docs | https://cloud.ibm.com/docs/ |
| `support_docs` | IBM Support content | https://www.ibm.com/support/ |
| `general_technical_docs` | IBM Research and SecurityIntelligence | https://research.ibm.com/ and https://securityintelligence.com/articles |
{: caption="Documentation collections" caption-side="bottom"}

## Examples
{: #wca-ibm-docs-examples}

| Type | Example question |
| --- | --- |
| General product information | `/docs what are the different IBM Cognos Analytics offerings for which IBM provides commands to?`|
| Perform a task | `/docs What is the command to back up a database in Db2? Enclose the command in code blocks.` |
| Troubleshoot an error code | `/docs I am getting this error: Internal error occurred: SCAPI error: The value on row 1,029 is not a valid string while previewing a data asset using import node. Can you provide a workaround for this?` |
| Query a specific collection | `/docs collection:redhat What are Machine pools in Cluster administration nodes in Red Hat OpenShift dedicated?` |
{: caption="Examples" caption-side="bottom"}

## Tips
{: #wca-ibm-docs-tips}

These tips can help improve your `/docs` questions.

### Use the product name
{: #wca-ibm-docs-tips-product}

Be sure to specify the product name. `How to back up a database` might retrieve results from Db2, but `How to back up a Db2 database` works better.

### Version numbers
{: #wca-ibm-docs-tips-version}

The source that {{site.data.keyword.wca_short}} uses contains documentation about the latest versions of IBM products. Questions about older versions might work if you specify the version number in your query.

### Context
{: #wca-ibm-docs-tips-context}

When {{site.data.keyword.wca_short}} answers a `/docs` question, it doesn't use any other context from your chat window or open files. The context is retrieved from IBM product documentation.

The response from a `/docs` question becomes part of your chat context. Your next chat question can use the documentation response as context to help guide {{site.data.keyword.wca_short}}. 

For example, you can ask: `/docs what is the command to back up a Db2 database. Format the command in Markdown.`

When you get the response with the command, you can ask: `Create a script to back up the Db2 database REVENUE` and you should receive a response that uses the command syntax from the documentation.
