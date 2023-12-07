---

copyright:
  years:  2023
lastupdated: "2023-10-09"

keywords: security, identity management, privileges, access, IAM

subcollection: watson-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Managing IAM access for {{site.data.keyword.wca_full_notm}} for Z
{: #wca-iam}

Access to {{site.data.keyword.wca_full}} for Z for users in your account is controlled by {{site.data.keyword.cloud}} Identity and Access Management (IAM). Every user that accesses {{site.data.keyword.wca_full_notm}} in your account must be assigned an access policy with an IAM role.
{: shortdesc}

To add a user to your {{site.data.keyword.wca_full_notm}} for Z instance, you must assign the **Editor** access role for the user in the deployment space. With this role, the user has full access to view, modify, and create resources, but cannot create users or access policies.

The following information applies only to {{site.data.keyword.wca_full}} for Z users. Because {{site.data.keyword.wcaal_full}} users do not need to generate their own API keys or directly access the {{site.data.keyword.wca_full_notm}} user interface in {{site.data.keyword.wca_full_notm}}, these users do not need to set up IAM in {{site.data.keyword.wca_full_notm}}.


## Adding a user to {{site.data.keyword.wca_full_notm}} for Z
{: #add-user}

The following steps must be completed by the Administrator for the {{site.data.keyword.wca_full_notm}} instance.

1. In the {{site.data.keyword.cloud_notm}} console, invite the user to the {{site.data.keyword.cloud_notm}} account for the {{site.data.keyword.wca_full_notm}} instance.

    You must provide an email address for the user that you want to invite. For more information, see [Inviting users in the console](/docs/account?topic=account-iamuserinv&interface=ui).

    1. Specify the following details:

        * **Service**: {{site.data.keyword.wca_full_notm}}
        * **Resources**: All resources

    When the user responds to this invitation, they are prompted to sign in to or create an {{site.data.keyword.cloud_notm}} account. From there, they can [create an API key](/docs/account?topic=account-userapikey&interface=ui) to connect to the {{site.data.keyword.wca_full_notm}} for Z instance from their local Visual Studio Code environment.

1. Go to the [watsonx user interface](https://dataplatform.cloud.ibm.com/).

1. Open the Navigation menu and click **Deployments**.

1. Go to the **Spaces** tab and click the **Code Assistant Models** space that you created during [{{site.data.keyword.wca_full_notm}} for Z setup in {{site.data.keyword.wca_full_notm}}](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-cloud-setup-z).

1. Select the **Manage** tab and click **Access Control**.

1. Click **Add collaborators** and select **Add user IDs** from the menu.

   A list of user IDs that are associated with your account appears.

1. Click the checkbox for the user ID that you want to add and select **Editor** for the role.

1. Click **Add**.

1. After the user accepts the invitation that you sent in the first step of this procedure, they can sign in to {{site.data.keyword.cloud_notm}} and [create an API key](/docs/account?topic=account-userapikey&interface=ui). The user must then provide this API key in the settings for the Open Z Editor Visual Studio Code extension in their local environment.

For more information, see [Refactoring and transforming COBOL code with IBM watsonx Code Assistant for Z](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-wca4z).


For more information about IAM in {{site.data.keyword.cloud_notm}}, see [Managing access to resources](/docs/account?topic=account-assign-access-resources&interface=ui).
