---

copyright:
   years: 2025, 2025
lastupdated: "2025-03-17"

keywords: watsonx, ansible, privacy, security

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}


# Data privacy and {{site.data.keyword.wcaal_full_notm}}
{: #wca-privacy-ansible}

[Red Hat Ansible Lightspeed]{: tag-red}

When you request code recommendations from {{site.data.keyword.wcaal_short}}, the prompt data that you submit is transient, and IBM does not retain or use it for any other purpose.

## What data does {{site.data.keyword.wcaal_short}} collect?
{: #wca-ansible-data}

When you request a code recommendation, a prompt is sent to the service with the following information:
- The Ansible tasks that you are requesting a recommendation for
- Playbook context, that is, the playbook name and variables mentioned in that playbook 

Once the data is submitted for processing to the model, the prompt data is discarded.

IBM does not:
- Use the input prompt to gather feedback about the model's performance.
- Use the input prompt to improve models.
