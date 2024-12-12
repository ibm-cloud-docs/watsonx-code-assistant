---

copyright:
  years: 2023, 2024
lastupdated: "2024-12-12"

keywords: FAQ, Ansible, Red Hat, Z

subcollection: watsonx-code-assistant

content-type: faq

---


{{site.data.keyword.attribute-definition-list}}


# FAQs for {{site.data.keyword.wca_short}}
{: #my-service-faqs}

FAQs for {{site.data.keyword.wca_short}} might include questions about code implementation, quality, or platforms.
{: shortdesc}


## How is the `pom.xml` file of a Maven project located?
{: #faq-mmr-aggregate}
{: faq}

[{{site.data.keyword.wca_short}}]{: tag-blue} [Standard plan]{: tag-purple}

{{site.data.keyword.wca_short_cap}} uses the aggregator `pom.xml` file to build and manage the entire multi-module Maven project. When {{site.data.keyword.wca_short}} attempts to do builds and other Maven-related activity, it uses the multi-module root (MMR) to locate the aggregator `pom.xml` file. 
* The MMR first searches the highest level project directory for the aggregator `pom.xml` file. 
* If the MMR doesn't find the file, it searches through the project directory by going from the next highest to the next highest directory structure, and so on, until it finds an aggregator `pom.xml` file. 
* If the MMR again does not find an aggregator `pom.xml` file, it searches through the project directory by going from the highest to the next highest directory structure, and so on, until it finds a regular `pom.xml` file. A regular `pom.xml` file indicates that the Maven project is a single module project instead of a mult-module project. 

## What data sources are used to train the {{site.data.keyword.wca_short}} models?
{: #faq-data-sources}
{: faq}

The {{site.data.keyword.wca_short}} models gather training data from various sources depending on which platform it's supporting. For more information, see:

- [{{site.data.keyword.wca_full_notm}} model details](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-wca-model-details)
- [{{site.data.keyword.wcaal_full_notm}} model details](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-ansible-model-details)

## Can I train or tune the model?
{: #faq-train-model}
{: faq}

[Red Hat Ansible Lightspeed]{: tag-red}

If you purchased an {{site.data.keyword.wcaal_full_notm}} Standard plan, you can tune the IBM base code model on your data so that it generates code suggestions that are customized for your enterprise standards. You can use the {{site.data.keyword.wcaal_short}} tuning studio to create model experiments and deploy your models to shared spaces so you and your team can quickly generate reliable and accurate code. For more information, see [Tuning the IBM base code model for {{site.data.keyword.wcaal_short}}](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-tutorial-tune-ansible).

## Can I provide feedback about the model?
{: #faq-provide-feedback}
{: faq}

You can provide feedback on your experiences, including suggestions for when your results don't match your expectations. For more information about providing feedback, see the [IBM Data and AI Ideas Portal for Customers](https://ibm-data-and-ai.ideas.ibm.com/){: external}.

## How long does it take before I see my feedback improve the model?
{: #faq-feedback-len}
{: faq}

Training the IBM {{site.data.keyword.wca_short}} model is resource-intensive. IBM Research intends to retrain the model at a cadence that provides noticeable model improvements between model versions.
