---

copyright:
  years: 2023
lastupdated: "2023-08-"

keywords:

subcollection: watson-code-assistant

content-type: troubleshoot

---

<!-- keywords values above are place holders. Actual values should be pulled from the Troubleshooting questions or error message to which the issue relates. Only use a messageID if the troubleshooting topic is about an issue encountered from an error message that has an ID.  -->

{{site.data.keyword.attribute-definition-list}}

<!-- You must add the troubleshoot content type in your attribute definitions AND on a new line under each troubleshooting topic H1 ID. This will ensure that the troubleshooting entry is pulled into other locations, like chatbots. Use the support attribute definition for reuse in the support center. For more information, see  https://test.cloud.ibm.com/docs/writing?topic=writing-support-center#support-center-troubleshoot-->

<!-- Remember that this is the individual topic template for each troubleshooting entry that belongs in a troubleshooting topic group in the Help left nav group. For more information, see the guidance page: https://test.cloud.ibm.com/docs/writing?topic=writing-troubleshooting-topics-->

# Having trouble?
{: #troubleshoot-xx}
{: troubleshoot}
{: support} <!-- Only add this attribute to entries that you want to display in the support center. -->

<!--The title of your H1 should be a problem statement in question format of the issue that the user is experiencing. Think about the user's language they might use to describe or search for the answer to the issue they are experiencing. Use keywords for other variations of ways to ask the question at the top of the file. -->

You try to create more than one instance in your Lite account, but you can't create more.
{: shortdesc}

<!-- The short description should give a quick summary about the issue the user is experiencing. -->
<!-- Example short description for an error troubleshooting topic: You try to create more than one instance in your Lite account, but you received error `message-id.0001E`.-->

<!-- Tips:
* Organize one troubleshooting issue per topic in a  topic group called "Troubleshooting" in the Help left nav section
* Name your topic group "Troubleshooting". If you have more than one topic group to organize a large set of troubleshooting topics, use "Troubleshoting _xxx_" to provide descriptive topic group titles.
* Use a title that uses a problem statement in the form of a question for each H1 in your topic group
* Use an H1 ID of `troubleshoot-xx` where the `xx` is a descriptive word to match the issue the customer is experiencing for URL readability.
* Set the `troubleshoot` content type attribute definition at the top of your file.
* Set the `troubleshoot` content type attribute on a new line following each H1 ID.
* Use the three attributes for the symptom, cause, and resolution.-->

Description of the troubleshooting entry symptom. For example: You receive the following error message when you try to create a new Lite plan instance:
{: tsSymptoms}

> message-id.0001E: Unable to provision new Lite instance

Description of the troubleshooting entry cause. For example: There's a limit of one instance per Lite plan to ensure that these plans stay free. For more information about Lite account features, see [Lite account](link).
{: tsCauses}

Description of the troubleshooting entry resolution. For example: You can create more instances of the service by selecting one of the billable service plans, which are available in the billable accounts. To upgrade to a billable account from the console, go to **Manage > Account**, and select **Account settings**.
{: tsResolve}

If you don't want to upgrade from a Lite account and are no longer using your existing Lite service instance, you can delete the existing Lite plan instance from the dashboard and then create a new instance.
