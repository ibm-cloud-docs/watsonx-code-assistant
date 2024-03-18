---

copyright:
   years: 2023, 2024
lastupdated: "2024-03-18"

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Understanding {{site.data.keyword.Bluemix_notm}} subscriptions and resource units for {{site.data.keyword.wcaz_short}}
{: #wcaz-tokenz}

{{site.data.keyword.wcaz_full_notm}} is an add-on that requires the on-premises version of {{site.data.keyword.wcaz_short}} as a prerequisite for converting your COBOL code to Java. The {{site.data.keyword.wca_short}} cloud service works on a subscription basis. Learn about the relationship among your subscription, resource units, and tokens.
{: shortdesc}

To explain how this works, it's easiest to start at the most abstract (and particular) unit, tokens. In generative AI, tokens are discrete pieces of data that, for language or code specifically, can be a word, a character, or even a phrase (or sequence of words or characters). The models that underly generative AI solutions (like this one) predict content based on an understanding of context (previous tokens). When you query a model, it uses a number of tokens to accurately generate a response to your query, whether that's in answer to a question or, in your case, converting a COBOL "query" to a Java response.

Keeping that in mind, when you use the [{{site.data.keyword.wcaz_full_notm}} catalog page](https://cloud.ibm.com/catalog/services/ibm-watsonx-code-assistant){: external}, what you're purchasing is entitlement to a number of resource units in your {{site.data.keyword.Bluemix_notm}} subscription. Resource units are like a change purse that you keep your tokens in, and your {{site.data.keyword.Bluemix_notm}} subscription is like the pocket where you keep your change purse. Each resource unit is equal to 150,000 tokens. For {{site.data.keyword.wcaz_short}}, COBOL applications require approximately 20-30 tokens per line of code. That value might vary depending on the application. So ultimately, your tokens yield approximately 5000-7000 lines of code. That number can vary because the number of tokens that are required to generate a good response varies. When you run out of tokens (resource units, in this case), you can renew your contract to refill your credits.

**Important**: Your {{site.data.keyword.Bluemix_notm}} subscription credits don't expire and you can use them on any {{site.data.keyword.Bluemix_notm}} service instead of, or in addition to, {{site.data.keyword.wcaz_short}}. Additionally, resource units (your change purse) are tied to usage, not a time frame. When you run out, you can resubscribe by renewing your contract.
