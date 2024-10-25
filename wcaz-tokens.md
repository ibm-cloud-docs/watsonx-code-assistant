---

copyright:
   years: 2023, 2024
lastupdated: "2024-10-25"

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Understanding {{site.data.keyword.cloud_notm}} subscriptions and resource units for {{site.data.keyword.wcaz_short}}
{: #wcaz-tokenz}

[{{site.data.keyword.wcaz_short}}]{: tag-teal}

The {{site.data.keyword.wca_short}} cloud service works on a subscription basis. Learn about the relationship among your subscription, resource units, and tokens.
{: shortdesc}

In generative AI, tokens are discrete pieces of data that, for language or code, can be a word, a character, or even a phrase (or sequence of words or characters). The models that underlie generative AI solutions predict content based on an understanding of context (which are previous tokens). When you query a model, it uses a number of tokens to accurately generate a response to your query.

When you use the [{{site.data.keyword.wcaz_full_notm}} catalog page](https://cloud.ibm.com/catalog/services/ibm-watsonx-code-assistant){: external}, what you're purchasing is entitlement to a number of resource units in your {{site.data.keyword.cloud_notm}} subscription. Each resource unit is equal to 150,000 tokens. For {{site.data.keyword.wcaz_short}}, COBOL applications require approximately 20-30 tokens per line of code. That value might vary depending on the application. Your tokens yield approximately 5000-7000 lines of code. That number can vary because the number of tokens that are required to generate a good response varies. When you run out of tokens, you can renew your contract to refill your credits.

Your {{site.data.keyword.cloud_notm}} subscription credits don't expire and you can use them on any service instead of, or in addition to, {{site.data.keyword.wcaz_short}}. Resource units are tied to usage, not a time frame. When you run out, you can resubscribe by renewing your contract.
{: important}
