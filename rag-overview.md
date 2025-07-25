---

copyright:
   years: 2025
lastupdated: "2025-07-25"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Setting up retrieval augmented generation (RAG) for {{site.data.keyword.wca_full_notm}}
{: #rag-overview}

[{{site.data.keyword.wca_short}}]{: tag-warm-gray} [Standard plan]{: tag-purple} 

RAG is the process of optimizing the large language model (LLM) output through the prompt augmentation with the additional context. If you submit a query, {{site.data.keyword.wca_short}} uses the RAG tools to retrieve the information from your codebases or documentation. This relevant context is appended to the query before it is sent to the LLM model. RAG system determines the sources that need to be included or excluded to generate a response with the most useful information.

RAG is supported for {{site.data.keyword.wca_short}} with the Standard plan.
{: important}

{{site.data.keyword.wca_full_notm}} supports RAG that enhances response quality of user queries in relevant, up-to-date context from codebases and documentation. RAG reduces model hallucinations and improves the accuracy of generated responses.

You can configure {{site.data.keyword.wca_short}} with specific code repositories and project documentation that are not stored in the Git repository using RAG to extract relevant information for the chat message. You can configure documentation such as API document, readme files, technical and design documents, Markdown, PDFs, Word, and PowerPoint documents.

The following figure illustrates the procedure to configure RAG for {{site.data.keyword.wca_short}}:

![Procedure for setting up RAG in {{site.data.keyword.wca_short}}](./images/procedure_rag.png){: caption="Procedure for setting up RAG in {{site.data.keyword.wca_short}}"}

## Enabling RAG for {{site.data.keyword.wca_full_notm}}
{: #rag-enable}

To enable RAG for {{site.data.keyword.wca_full_notm}}, complete the following steps:

1. Provision a vector store on IBM Cloud.
   
   1. Provision a Milvus or Elasticsearch vector store instance on the IBM Cloud. If the vector store is already available on your IBM Cloud account, you can skip this step.
      
      - To provision an Elasticsearch vector store instance on the IBM cloud, see [Provisioning Databases for Elasticsearch](/docs/databases-for-elasticsearch?topic=databases-for-elasticsearch-provisioning&interface=ui){: external}.

      - To provision a Milvus vector store instance on the IBM cloud, see [Provisioning watsonx.data](/docs/watsonxdata?topic=watsonxdata-getting-started){: external}.
        
        Milvus is a part of IBM watsonx.data. You can provision a Milvus instance on the IBM Cloud with [watsonx.data enterprise plan](/docs/watsonxdata?topic=watsonxdata-getting-started_1){: external}.
        {: note}

   1. Optional: Provision an instance of IBM watsonx.ai Studio to index the code repository.

1. Index or refresh your code repositories in Milvus or Elasticsearch on IBM Cloud. For more information, see [Indexing code repositories with IBM watsonx.ai Studio](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-rag-index-studio){: external}.

   Set up the connection assets:
   
   1. Use the existing deployment space in your {{site.data.keyword.wca_short}} service instance.

   1. Create a connection asset for each index that is created in the vector store. For more information, see [Creating a connection asset](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-rag-wca-onboard#rag-connection){: external}.

1. Set up the Git personal access token in the Visual Studio Code and use the RAG enabled prompts.
   
   1. Click your profile icon in the GitHub and go to **Settings** > **Developer Settings** > **Personal Access Tokens** > **Tokens (Classic)**.
      To create a new personal access token with the required permissions, see [Generate a new token](https://github.ibm.com/settings/tokens).
   1. Copy your personal access token. 
   1. Open the Visual Studio Code.
   1. Select `Enter Github Personal Access Token for WCA` in the command line.
   1. Enter your GitHub personal access token and press `Enter` or `Return`.   
   1. Enter the `@repo < instruction>` or `@docs < instruction>` syntax in the {{site.data.keyword.wca_short}} chat to generate a response that uses the context from the referenced repository or documents in the vector store. Replace `<instruction>` parameter with the prompt message. 
      
   - The following is the sample syntax to use the referenced repository:
  
     ```text
     @repo how is a chat message processed?
     ```
     {: codeblock} 
   
     {{site.data.keyword.wca_short}} uses the indexed repositories based on the following conditions:

     - If one repository is opened in Visual Studio Code, {{site.data.keyword.wca_short}} search for the context in the opened repository as default.

     - If multiple repositories are opened in the Visual Studio Code, {{site.data.keyword.wca_short}} search for the context from the repository that is associated with the recently accessed file.

     - {{site.data.keyword.wca_short}} checks for the `repo.yaml` file in the indexed repository when you enter `@repo < instruction>` syntax in the chat. If one or more YAML configuration files are configured, {{site.data.keyword.wca_short}} uses all the configured repositories to generate a response. If YAML configuration is not configured, {{site.data.keyword.wca_short}} uses the selected repository. 
      
   - The following is the sample syntax to use the referenced document collection:

     ```text
     @docs What are the steps to setup a connection to the user data store?
     ```
     {: codeblock} 

     {{site.data.keyword.wca_short}} uses the indexed document collections based on the following conditions:

     - If the document is opened in Visual Studio Code, {{site.data.keyword.wca_short}} search for the context in the opened repository as default.

     - If multiple document collections are opened in the Visual Studio Code, {{site.data.keyword.wca_short}} search for the context from the recently accessed document.

     - {{site.data.keyword.wca_short}} checks for the `docs.yaml` file in the indexed repository when you enter `@docs < instruction>` syntax in the chat. If one or more YAML configuration files are configured, {{site.data.keyword.wca_short}} uses all the configured document collections to generate a response. If YAML configuration is not configured, {{site.data.keyword.wca_short}} uses all the document with the `docs_<filename>` name in your deployment space. 

   Optional: If you need to set up YAML configuration for indexed repositories or document collections, see [Setting up YAML configuration for RAG](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-rag-overview#yaml-rag).

## Setting up YAML configuration for RAG
{: #yaml-rag}

You can set up YAML configuration optionally to allow {{site.data.keyword.wca_short}} to search for multiple repositories at a same time or use the specific indexed code repository or document in the vector store. If you do not set up YAML configuration, {{site.data.keyword.wca_short}} uses the repository that is opened in the Visual Studio Code as default. 

{{site.data.keyword.wca_short}} uses the API key authorization method to ensure that you can access only the authorized repositories or document collections.
{: note}

   - To set up YAML configuration for specific indexed repository, completed the following steps:

     1. Create a `.wca/repo` folder at the root level of the repository.
     1. Create a YAML file with the following fields:
        
        ```shell
        repo:
           - url: git@github.ibm.com:code-assistant/<my-code>.git
        ```
        {: codeblock}

        If you need to configure {{site.data.keyword.wca_short}} with multiple repositories, create `repo.yaml` file for each repository that needs to be used to generate a response. 
      
   - To set up YAML configuration for specific document collections, completed the following steps:

     1. Create a `.wca/docs` folder at the root level of the repository.
     1. Create a YAML file with the following fields:
        
        ```shell
        docs: 
           - url: my_collection
        ```
        {: codeblock} 
   
## Use case scenarios
{: #rag_usecase}

The use case scenarios explain how the RAG function works and data are retrieved from indexed repositories or documents.

### Using a single code repository in {{site.data.keyword.wca_short}}
{: #rag_usecase1}

If you are working on a repository A and want to use the code from this repository as context for the chat conversations with {{site.data.keyword.wca_short}}, complete the following steps:

1. Ensure that you have access to repository A in GitHub.

1. Index the repository A in the vector store. For more information, see [Indexing code repository with IBM watsonx.ai Studio](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-rag-index-studio){: external}.

1. Create a connection asset for repository A. For more information, see [Creating a connection asset](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-rag-wca-onboard#rag-connection){: external}.

1. Generate a Git personal access token from your GitHub account and complete the set up in the Visual Studio Code.

1. Open the repository A in the Visual Studio Code.

1. Use `@repo` syntax in the {{site.data.keyword.wca_short}} chat to generate a response that uses the context from the repository A.

### Using multiple code repositories in {{site.data.keyword.wca_short}} 
{: #rag_usecase2}

If you are working on a repository A that has dependencies on repository B, you can use the code from both the repositories as context for the chat conversations with {{site.data.keyword.wca_short}}. To use both the repositories, complete the following steps:

1. Ensure that you have access to repositories A and B in GitHub.

1. Index each repository A and B in the vector store separately. For more information, see [Indexing code repository with IBM watsonx.ai Studio](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-rag-index-studio){: external}.

1. Create two connection assets for each vector store. For more information, see [Creating a connection asset](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-rag-wca-onboard#rag-connection){: external}.

1. Generate a Git personal access token from your GitHub account and complete the set up in the Visual Studio Code.

1. Set up YAML configuration for each repository A and B in the repository A.

1. Use `@repo` syntax in the {{site.data.keyword.wca_short}} chat to generate a response that uses the context from the repositories A and B.

If you use same index for repositories A and B, the GitHub access check is not performed for repository B. If you do not have access for one of the repositories, {{site.data.keyword.wca_short}} generates the context from the authorized repository.
{: note} 

### Enabling all the users in a team to access project documentation repositories
{: #rag_usecase3}

You can allow all the users in a team to access the project documentation repositories and use the documents as context for the chat conversation with {{site.data.keyword.wca_short}}. To enable the access for all users, complete the following steps:

1. Index the project documentation repositories in the vector store. For more information, see [Indexing code repository with IBM watsonx.ai Studio](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-rag-index-studio){: external}. 

   You can use the same index for all documentation repositories if all the users have access for the indexed project documentation repositories. If the users have an access restriction for the indexed repository, see [Enabling the users in a different sub-team to access project documentation repositories](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-rag-overview#rag_usecase4).

1. Create a connection asset for the documentation index in the deployment space that includes all the users of the team. For more information, see [Creating a connection asset](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-rag-wca-onboard#rag-connection){: external}.

1. Use `@docs` syntax in the {{site.data.keyword.wca_short}} chat to generate a response that uses the context from the documentation index.

The GitHub personal access tokens are not used to verify access to documentation content when you use `@docs` syntax in the {{site.data.keyword.wca_short}}. You can combine several documentation repositories in the same index in the vector store. The documentation content is less restrictive than code repositories and a single index for all the documentation repositories simplifies the index management process. The authorization to access the documentation repositories is only allowed to the onboarded users in the deployment space.
{: note}

### Enabling the users in a different sub-team to access project documentation repositories
{: #rag_usecase4}

The different subteams in a large team maintain the project documentation repositories and the access to the documentation repositories is restricted to the specific subteams. The other subteams do not have access for these documentation repositories. 

To enable each sub-team to access the related project documentation repositories and use the documents as context for the chat conversation with {{site.data.keyword.wca_short}}, complete the following steps:

1. Index the documentation repositories of each subteams separately in the vector store. The two documentation indexes are created in the vector store for each sub-team. For more information, see [Indexing code repository with IBM watsonx.ai Studio](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-rag-index-studio){: external}.

1. Ensure that the deployment space is created for each sub-team with its users.

1. For each documentation repository index, create a connection asset in the related deployment space. For more information, see [Creating a connection asset](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-rag-wca-onboard#rag-connection){: external}.

1. Use `@docs` syntax in the {{site.data.keyword.wca_short}} chat to generate a response that uses the context from the documentation index.

{{site.data.keyword.wca_short}} uses the respective documentation repository index based on the deployment space that is assigned to the user. The client-side configuration is not required.

### Enabling the users based on a role to access project documentation repositories
{: #rag_usecase5}

The users in a team require access to different sets of documentation based on their roles. The scope of documentation that is used as context in {{site.data.keyword.wca_short}} varies across the users and no access restrictions. For example, developers need technical and API documentation only, while business analysts focus on business process documents.

To customize the documentation repositories that are used as context in {{site.data.keyword.wca_short}}, complete the following steps:

1. Index each documentation repository in the vector store separately. For more information, see [Indexing code repository with IBM watsonx.ai Studio](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-rag-index-studio){: external}.

1. Create a connection asset for each index in the deployment space of the team. For more information, see [Creating a connection asset](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-rag-wca-onboard#rag-connection){: external}.

1. Set up YAML configuration for the required documentation index that is used as context in {{site.data.keyword.wca_short}}. If you need to use multiple documentation indexes as a context in {{site.data.keyword.wca_short}}, set up YAML configuration for each documentation index.

1. Use `@docs` syntax in the {{site.data.keyword.wca_short}} chat to generate a response based on the documentation index that is configured in the YAML configuration.
