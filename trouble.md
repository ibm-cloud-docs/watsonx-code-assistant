---

copyright:
  years: 2023, 2024
lastupdated: "2024-03-26"

keywords:

subcollection: watsonx-code-assistant

content-type: troubleshoot

---


{{site.data.keyword.attribute-definition-list}}

# Why can't I connect {{site.data.keyword.wcaz_short}} to my Db2 database?
{: #troubleshoot-db2}
{: troubleshoot}
{: support}

During the initial cloud setup of your {{site.data.keyword.wcaz_short}} instance, the automated population of your Db2 account fails.
{: shortdesc}

If your database is associated with a different account than your {{site.data.keyword.cloud_notm}} instance, or if the automated population in the [onboarding checklist](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-cloud-setup-z) fails, use these steps to connect your database:

1. On the **Code Assistant Models** page, select the **Assets** tab.

2. Click **Import Assets**.

3. On the **Import Assets** > **Data access** page, click **Connection**.

4. Click **Create connection** and select *{{site.data.keyword.Db2_on_Cloud_long_notm}}*. You now need to collect the information to complete this step:

   1. Open a separate browser tab and log in to [cloud.ibm.com](https://cloud.ibm.com/){: external}.
   2. Go to the {{site.data.keyword.cloud_notm}} account that contains your Db2 instance.
   3. Click the *Resource list* icon, then click **Databases** > your Db2 instance. The **Manage** tab of your Db2 instance opens.
   4. Click **Service Credentials** tab then expand the service credentials for your key:

      1. Locate the `hosts` section and make note of the:

         - Hostname
         - Port number

      2. Locate the `authentication` section and make note of the:

         - Username
         - Password

5. Return to you **Create connection** tab and use the following values to create your connection:

    - **Name**: A meaningful name for your connection
    - **Database**: `bludb`
    - **Hostname**: The hostname that you identified in the previous step
    - **Port**: The port number that you identified in the previous step
    - **Username**: The username that you identified in the previous step
    - **Password**: The password that you identified in the previous step

11. Click **Test Connection**. If the test completes successfully, click **Create**.
