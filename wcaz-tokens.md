---

copyright:
   years: 2023, 2024
lastupdated: "2024-02-08"

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Understanding IBM Cloud subscriptions and resource units for IBM {{site.data.keyword.wca_full_notm}} for Z
{: #wcaz-tokenz}

IBM {{site.data.keyword.wca_full_notm}} for Z is an add-on that requires the on-premises version of watsonx Code Assistant for Z as a prerequisite for translating your COBOL code to Java. The {{site.data.keyword.wca_full_notm}} cloud service works on a subscription basis. This topic seeks to clarify the relationship between your subscription, resource units, and tokens.
{: shortdesc}

When explaining how this all of this works, it's easiest to start at the most abstract (and particular) unit, tokens. In generative AI, tokens are discrete pieces of data that, for language or code specifically, can be anything from a word, to a character, to even a phrase (or sequence of words or characters). The models that underly generative AI solutions (like this one) predict content based on an understanding of context (previous tokens). When you query a model, it uses up an number of tokens to accurately generate a response to your query, whether that's in answer to a question or, in your case, translating a COBOL "query" to a Java response.

Keeping that in mind, when you sign up for {{site.data.keyword.wca_full_notm}} for Z in the [IBM watsonx Code Assistant catalog page](https://cloud.ibm.com/catalog/services/ibm-watsonx-code-assistant), what you're purchasing is entitlement to an number of resource units in your IBM Cloud subscription. Resource units are like a change purse that you keep your tokens in, and your IBM Cloud subscription is like the pocket where you keep your change purse. Each resource unit contains 10 tokens, so when you're purchasing a resource unit, you're actually purchasing 150,000 tokens to use to generate responses to your queries. For {{site.data.keyword.wca_full_notm}} for Z, COBOL applications require approximately 20-30 tokens per line of code. That value might vary depending on the application. So ultimately, your tokens yield approximately 5000-7000 lines of code. That number can vary because the number of tokens required to generate a good response varies. When you run out of tokens (resource units, in this case), you can renew your contract to refill your credits.

**Important**: Your IBM Cloud subscription credits don't expire and you can use them on any IBM Cloud service instead of, or in addition to, {{site.data.keyword.wca_full_notm}} for Z. Additionally, resource units (your change purse) are tied to usage, not a time frame. When you run out, you can resubscribe by renewing your contract.
