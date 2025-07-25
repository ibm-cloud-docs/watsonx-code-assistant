---

copyright:
   years: 2025
lastupdated: "2025-07-25"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Setting up connection assets
{: #rag-wca-onboard}

Connection asset contains the connection details of your vector store. {{site.data.keyword.wca_short}} uses the connection asset to connect to your vector store and fetch the context for your instructions in the chat.

## Before you begin
{: #rag-wca-onboard_prerequisite}

- Ensure that you refer to the use case scenarios before you create a connection asset. For more information, see [Use case scenarios](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-rag-overview#rag_usecase).
- Ensure that you have an IBM Cloud account.
- Ensure that you have an instance of the Milvus or Elasticsearch DB on IBM Cloud.
- Ensure that you have the list of indexed code repositories and document in the vector store.

## Creating a connection asset
{: #rag-connection}

{{site.data.keyword.wca_full_notm}} uses connection assets in your deployment space to access code repository content that is indexed in your vector store. Create a connection asset for each index in your vector store.

The name of the connection asset must be the same as the name of the code repository. For example, if the repository url is `git@github.ibm.com:my-org/mycode.git`, the name of the connection asset must be `mycode`. If you create connection asset for the documentation indexes, the name of the connection asset must be in the `docs_<name>` format. You can replace `<name>` with the name of the indexed document with the prefix `docs`.
{: note}

{{site.data.keyword.wca_full_notm}} uses the description section of the connection asset to read more configuration details about your vector store. 

To create a connection asset, complete the following steps:

1. Open your {{site.data.keyword.wca_short}} service instance.

1. Click the **Navigation Menu** icon ![Navigation Menu](images/menu.svg), then select **Deployments**.

1. Select your deployment space.

1. Go to the **Assets** tab of your deployment space.

1. Go to **Import assets** > **Data access** > **Connection**.

1. Select the Elasticsearch or Milvus connection type in **Add connection**.
   
   - For the Elastichsearch connection type, add the following fields:
     
     |Parameter|Description|
     |---|---|
     |Name| Enter the name of the Elasticsearch connection. The Elasticsearch connection name must be the same as the repository name to use `@repo` syntax or start with `docs_` to use `@docs` syntax.|
     |Description|Enter the additional information of the connection asset in the JSON format with the following fields:<pre><code><br>{</br><br>"index_name": "add the name of your index",</br><br>"db_type": "elasticsearch",</br><br>"ssl_assert_fingerprint": "your_fingerprint",</br><br>"embedding_details": {</br><br>"model_id": "msmarco-MiniLM-L-6-v3"</br><br>}</br></br>}</br></code></pre>|
     |URL| Enter the connection URL for your Elasticsearch instance.|
     |Username and Password|Enter the credentials of your Elasticsearch instance.|
     |SSL Certificate|Optional: Enter the SSL certificate to create a secure connection with the Elasticsearch instance. You cannot test your Elastcisearch connection without an SSL Certificate. To save the connection, click **Save connection anyway**.|
     {: caption="Elastichsearch connection type settings" caption-side="bottom"}

   - For the Milvus connection type, add the following fields:
     
     |Parameter|Description|
     |---|---|
     |Name| Enter the name of the Milvus connection. The Milvus connection name must be the same as the repository name to use `@repo` syntax or start with `docs_` to use `@docs` syntax.|
     |Description|Enter the additional information of the connection asset in the JSON format with the following fields:<pre><code><br>{</br><br>"index_name": ""add the name of your index",</br><br>"db_type": "milvus",</br><br>"embedding_details": {</br><br>  "model_id": "msmarco-MiniLM-L-6-v3"</br><br>}</br></br>}</br></code></pre>|
     |Host|Enter the host URL for your Milvus instance.|
     |Port|Enter the port number for your Milvus instance.|
     |Database|Set the Database parameter to default.|
     |Username and Password|Set the username to `ibmlhapikey` and enter an API key that is generated from the IBM Cloud account with the watsonx.data instance in the Password field.|
     |SSL Certificate|Optional: Enter the SSL certificate to create a secure connection with the Milvus instance. You can test your Milvus connection without an SSL Certificate.|
     {: caption="Milvus connection type settings" caption-side="bottom"}
     

1. Click **Create**.
