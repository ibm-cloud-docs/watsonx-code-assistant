---

copyright:
   years: 2025
lastupdated: "2025-07-25"

keywords: 

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Indexing code repositories with IBM watsonx.ai Studio
{: #rag-index-studio}

[{{site.data.keyword.wca_short}}]{: tag-blue}
 
You can use watsonx.ai Studio to index your code repositories to enable the retrieval augmented generation (RAG) support for {{site.data.keyword.wca_short}}.

## Before you begin
{: #watson_prereqs}

- Ensure that you have an instance of the Milvus or Elasticsearch DB on IBM Cloud before you run the notebook.

- Ensure that you have an instance of the watsonx.ai Studio to run the notebook. To create a watsonx.ai Studio instance, see [watsonx.ai Studio catalog](https://cloud.ibm.com/catalog/services/watsonxai-studio).

- Ensure that you have an API key to access {{site.data.keyword.wca_short}} to generate explanations for the functions in your code. The explanations are indexed with the code for better search results. To get the API key, see [API key access to {{site.data.keyword.wca_short}}](https://github.ibm.com/code-assistant/wca-api/issues/new/choose){: external}.

## Planning your index
{: #planning_index}

Effective indexing is essential for optimizing the performance of {{site.data.keyword.wca_short}} when you use the RAG feature. Ensure that you consider the following factors when you index the repository or documents:

- Ensure that the storage space in the disk is double the size of the content that is being indexed.

- Index code repositories when you reuse existing code to generate new code, locating implementations of specific functions, answering how how-to questions related to the codebase. You can include main code projects and their dependencies such as API implementation.

- Index documentation repositories such as product or project documentation, technical guides, and design documents if you need {{site.data.keyword.wca_short}} to respond to queries based on these documents.

- Do not index rarely used code repositories or documents to reduce storage usage and minimize the time that is required for index creation and maintenance.

- Use one index per repository, especially for source code to limit the context search to specific repositories.

- Combine multiple documentation repositories in a single index if you commonly search across all documents. You can create separate indexes if a significant keyword overlap between repositories and different team or users need to search the context in the specific documentation repositories.
   
- Do not merge code from different repositories in the same index. This reduces the accuracy of the response generation for the prompt and leads to unauthorized access of the code if the access restriction for the users is not implemented properly.

- Ensure that you manage security and authorization correctly during the indexing process. For different usage scenarios, see [Use case scenarios](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-rag-overview#rag_usecase).

- Ensure that all necessary organizational approvals are obtained before you index the confidential or sensitive content. The source code and documents that are used for RAG are saved as plain text and vectorized format in a vector store outside your GitHub repository.

## Indexing code repositories
{: #studio-procwatsonx}

1. Login to your [{{site.data.keyword.wca_short}} service instance](https://dataplatform.cloud.ibm.com/exchange/public/entry/view/6b610fcb-7308-456f-884c-9e5ec456218a?context=wx).

1. Click **Create project**.

1. Select a cloud object storage instance in the **Storage** field. If the cloud object storage instance is not available in the drop-down list, create it.

1. Click **Create**.

1. Go to **Asset** tab in your project and click **Populate vector store** notebook.

1. Follow the instructions in the `Populate vector store` notebook to index the code or document in the Github repository.


