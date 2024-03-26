---

copyright:
  years:  2023, 2024
lastupdated: "2024-03-26"

keywords: security, identity management, privileges, access, IAM

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Managing IAM access for {{site.data.keyword.wcaz_short}}
{: #wca-iam}

Access to {{site.data.keyword.wcaz_short}} for users in your account is controlled by {{site.data.keyword.iamlong}} (IAM). Every user that accesses {{site.data.keyword.wca_full_notm}} in your account must be assigned an access policy with an IAM role.
{: shortdesc}

To add a user to your instance, you must assign the **Editor** access role for the user in the deployment space. With this role, the user has full access to view, modify, and create resources, but cannot create users or access policies.

## Adding users
{: #add-user}

The following steps must be completed by the administrator for the instance.

1. In the {{site.data.keyword.cloud_notm}} console, invite the user to the account for the instance.

    You must provide an email address for the user that you want to invite. For more information, see [Inviting users in the console](/docs/account?topic=account-iamuserinv&interface=ui){: external}.
    
    Specify the following details:
    - **Service**: {{site.data.keyword.wca_full_notm}}
    - **Resources**: All resources

    When the user responds to this invitation, they are prompted to sign in to or create an {{site.data.keyword.cloud_notm}} account. From there, they can [create an API key](/docs/account?topic=account-userapikey&interface=ui){: external} to connect to the instance from their local Visual Studio Code environment.

1. Go to the [watsonx user interface](https://dataplatform.cloud.ibm.com/){: external}.

1. Open the Navigation menu and click **Deployments**.

1. Go to the **Spaces** tab and click the **Code Assistant Models** space that you created during setup.

1. Select the **Manage** tab and click **Access Control**.

1. Click **Add collaborators** and select **Add user IDs** from the menu.

   A list of user IDs that are associated with your account appears.

1. Click the checkbox for the user ID that you want to add and select **Editor** for the role.

1. Click **Add**.

1. After the user accepts the invitation that you sent in the first step of this procedure, they can sign in to {{site.data.keyword.cloud_notm}} and [create an API key](/docs/account?topic=account-userapikey&interface=ui){: external}. The user must then provide this API key in the settings for the Open Z Editor Visual Studio Code extension in their local environment.

For more information, see [Refactoring and transforming COBOL code with {{site.data.keyword.wcaz_full_notm}}](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-wca4z).

For more information about IAM in {{site.data.keyword.cloud_notm}}, see [Managing access to resources](/docs/account?topic=account-assign-access-resources&interface=ui){: external}.
