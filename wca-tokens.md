---

copyright:
   years: 2025
lastupdated: "2025-04-30"

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Understanding {{site.data.keyword.cloud_notm}} subscriptions and resource units for {{site.data.keyword.wca_short}}
{: #wca-tokens}

[{{site.data.keyword.wca_short}}]{: tag-blue}

The {{site.data.keyword.wca_short}} service works on a subscription basis. Learn about the relationship among your subscription, resource units, and tokens.
{: shortdesc}

In generative AI, tokens are discrete pieces of data that, for language or code, can be a word, a character, or even a phrase (or sequence of words or characters). The models that underlie generative AI solutions predict content based on an understanding of context (which are previous tokens). When you query a model, it uses a number of tokens to accurately generate a response to your query.

When you use the [{{site.data.keyword.wca_full_notm}} catalog page](https://cloud.ibm.com/catalog/services/ibm-watsonx-code-assistant){: external}, what you're purchasing is entitlement to a number of resource units in your {{site.data.keyword.cloud_notm}} subscription. 
- One resource unit covers approximately 20 task prompts that use 500 tokens each
- A single developer requires approximately 15 resource units per month
- Use the [catalog page](https://cloud.ibm.com/catalog/services/ibm-watsonx-code-assistant){: external} to see what each plan offers and to estimate your costs

Your {{site.data.keyword.cloud_notm}} subscription credits don't expire and you can use them on any service instead of, or in addition to, {{site.data.keyword.wca_short}}. Resource units are tied to usage, not time. When you run out, you can resubscribe by renewing your contract.
{: important}
