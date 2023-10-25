---

copyright:
  years: 2023
lastupdated: "2023-08-23"

keywords:

subcollection: watson-code-assistant

content-type: troubleshoot

---


{{site.data.keyword.attribute-definition-list}}

# Why can't I connect {{site.data.keyword.cloud_notm}} for Z to my Db2 database?
{: #troubleshoot-xx}
{: troubleshoot}
{: support}

During the initial cloud setup of your {{site.data.keyword.cloud_notm}} for Z instance, the automated population of your Db2 account fails.
{: shortdesc}

If your database is associated with a different IBM Cloud account than your {{site.data.keyword.cloud_notm}} instance, or if the automated population fails, complete the following steps to connect your database to your deployment space.

1. On the **Code Assistant Models** page, select the **Assets** tab.

2. Click **Import Assets**.

3. On the **Import Assets** > **Data access** page, click **Connection**.

4. Click **Create connection** and select *IBM Db2 on Cloud*. You now need to collect the information to complete this step:

   1. Open a separate browser tab and log in to [cloud.ibm.com](cloud.ibm.com)
   2. Go to the IBM Cloud account that contains your Db2 instance.
   3. Click the *Resource list* icon, then click **Databases** > your Db2 instance. The **Manage** tab of your Db2 instance opens.
   4. Click **Service Credentials** tab then expand the service credentials for your key:

      1. Locate the `hosts` section:

         * Make note the hostname
         * Make note of the port number

      2. Locate the `authentication` section:

         * Make note of the username
         * Make note of the password

5. Return to you **Create connection** tab and use the following values to create your connection:

    * **Name**: A meaningful name for your connection
    * **Database**: `bludb`
    * **Hostname**: The hostname that you identified in the previous step
    * **Port**: The port number that you identified in the previous step
    * **Username**: The username that you identified in the previous step
    * **Password**: The password that you identified in the previous step

11. Click **Test Connection**. If the test completes successfully, click **Create**.
