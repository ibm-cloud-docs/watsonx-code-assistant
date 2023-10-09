---

copyright:
  years:  2023
lastupdated: "2023-10-09"

keywords:

subcollection: watson-code-assistant

---

{{site.data.keyword.attribute-definition-list}}



# Managing IAM access for {{site.data.keyword.wca_full_notm}}
{: #iam}

Access to {{site.data.keyword.wca_full}} for users in your account is controlled by {{site.data.keyword.cloud}} Identity and Access Management (IAM). Every user that accesses {{site.data.keyword.wca_full_notm}} in your account must be assigned an access policy with an IAM role.
{: shortdesc}

To add a user to your {{site.data.keyword.wca_full_notm}} instance, you must create an {{site.data.keyword.cloud}} access policy for the user at the platform level. You must also assign an access role for the user in the deployment space. The following roles are available for both the platform and the deployment space.

* A **Viewer** can access resources, but not modify them.
* An **Editor** has full access to view, modify, and create resources, but cannot create users or access policies.
* An **Operator** can configure and operate service instances.
* An **Administrator** has full access to view, modify, and create resources, and to create users and access policies.

When you add users to your {{site.data.keyword.wca_full_notm}} instance, the best practice is to grant them Viewer access at the platform level and Editor access within the deployment space.

## Adding a user to {{site.data.keyword.wca_full_notm}}
{: #add-user}

The following steps must be completed by the Administrator for the {{site.data.keyword.wca_full_notm}} instance.

1. In the {{site.data.keyword.cloud}} console, invite the user to the {{site.data.keyword.cloud}} account for the {{site.data.keyword.wca_full_notm}} instance.

    For information about inviting users, see [Inviting users in the console](/docs/account?topic=account-iamuserinv&interface=ui).

    1. When you invite the user, you must create an access policy for the user at the platform level. Specify the following details:

        * **Service**: {{site.data.keyword.wca_full_notm}}
        * **Resources**: All resources
        * **Roles and Actions** > **Platform access**: Viewer

1. Go to the **Manage** tab of the {{site.data.keyword.wca_full_notm}} user interface (UI).

1. Select **Access control**.

1. Click **Add collaborators** and select **Add user IDs** from the menu.

   A list of user IDs that are associated with your account appears.

1. Click the checkbox for the user ID that you want to add and select **Editor** for the role.

1. Click **Add**

When the user responds to the invitation you sent, they are prompted to sign in to or create an {{site.data.keyword.cloud}} account. From there, they can [create an API key](/docs/account?topic=account-userapikey&interface=ui) to use to connect to the {{site.data.keyword.wca_full_notm}} instance in their local Visual Studio Code environment. Although {{site.data.keyword.wca_full_notm}} supports allowing multiple users to use the API key for the Service ID, the best practice is to have an API key for each user.

For more information about IAM in {{site.data.keyword.cloud}}, see [Managing access to resources](/docs/account?topic=account-assign-access-resources&interface=ui).
