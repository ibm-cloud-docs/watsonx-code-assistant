---

copyright:
  years: 2023, 2024
lastupdated: "2024-11-21"

keywords:

subcollection: watsonx-code-assistant

content-type: troubleshoot

---


{{site.data.keyword.attribute-definition-list}}

# Why can't I connect {{site.data.keyword.wcaz_short}} to my Db2 database?
{: #troubleshoot-wcaz-connect-db2}
{: troubleshoot}
{: support}

[{{site.data.keyword.wcaz_short}}]{: tag-dark-teal}

During the initial cloud setup of your {{site.data.keyword.wcaz_short}} instance, the automated population of your Db2 account fails.
{: shortdesc}

If your database is associated with a different account than your {{site.data.keyword.cloud_notm}} instance, or if the automated population in the onboarding checklist fails, use these steps to manually connect your database.

First, you need to collect authentication and hostname information from your Db2 service instance:

1. Log in to [cloud.ibm.com](https://cloud.ibm.com/){: external}.

1. Open the {{site.data.keyword.cloud_notm}} account that contains your Db2 instance.

1. Click the **Resource list** icon ![Resource list](images/list.svg).

1. Open the **Databases** section, then click your Db2 instance.

1. Click **Service Credentials**. 

   If don't have service credentials, click **New credential**, then click **Add**.
   {: note}

1. Click the expand icon ![Chevron down](images/chevron--down.svg) for the credentials.

1. Locate the `authentication` section and make note of the:

   - username
   - password

1. Locate the `hosts` section and make note of the:

   - hostname
   - port

Second, create a connection in your deployment space:

1. In your {{site.data.keyword.wcaz_short}} instance, open your deployment space.

1. Click the **Assets** tab.

1. Click **Import Assets**.

1. Click **Data access**, then click the **Connection** tile.

1. On the **New** tab, select **IBM Db2 on Cloud**, then click **Select**.

1. Enter the following values to create your connection:

    - **Name**: A meaningful name for your connection
    - **Database**: `bludb`
    - **Hostname or IP address**: The hostname from the service credentials
    - **Port**: The port number from the service credentials
    - **Username**: The username from the service credentials
    - **Password**: The password from the service credentials

1. Click **Test Connection**. If the test completes successfully, click **Create**.
