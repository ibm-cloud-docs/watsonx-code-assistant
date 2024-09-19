---

copyright:
   years: 2024
lastupdated: "2024-09-19"

keywords: watsonx, ansible, llm, model

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# {{site.data.keyword.wcaal_full_notm}} model details
{: #ansible-model-details}

[Red Hat Ansible Lightspeed]{: tag-red}

{{site.data.keyword.wcaal_short_cap}} base models are derived from the [IBM Granite models](https://www.ibm.com/products/watsonx-ai/foundation-models){: external} and were trained on Ansible YAML data to improve their performance in Ansible tasks.

The following sources were used for training the base model on Ansible code:
- Ansible Galaxy (Ansible Collections)
- Ansible YAMLs from public repositories in GitLab and GitHub

The following sources were used for training the base model on the English language:
- Ansible documentation
- StackExchange
- Wikipedia
- CommonCrawl
