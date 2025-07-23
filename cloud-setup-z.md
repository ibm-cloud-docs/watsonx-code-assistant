---

copyright:
   years: 2023, 2025
lastupdated: "2025-07-23"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Setting up your {{site.data.keyword.wcaz_short}} service in {{site.data.keyword.cloud_notm}}
{: #cloud-setup-z}

[{{site.data.keyword.wcaz_short}}]{: tag-dark-teal}

Set up your {{site.data.keyword.cloud_notm}} service instance of {{site.data.keyword.wcaz_short}} so you can use it with your full installation of the product.
{: shortdesc}

## Before you begin
{: #prereqs-z}

- Make sure that you have an [{{site.data.keyword.cloud_notm}} account](https://cloud.ibm.com/registration/){: external}.

- Provision an instance of {{site.data.keyword.wcaz_short}} through the [{{site.data.keyword.cloud_notm}} catalog](https://cloud.ibm.com/catalog/services/ibm-watsonx-code-assistant){: external} page or by working with an IBM sales representative. 

   The service is available in these data centers:
   - Dallas (`us-south`)
   - Frankfurt (`eu-de`)
   
   For more information about data centers, see the {{site.data.keyword.BluSoftlayer_notm}} documentation for [Service and infrastructure availability by location](https://cloud.ibm.com/docs/overview?topic=overview-services_region){: external}.

- Download the most recent `IBM watsonx Code Assistant for Z Multiplatform Multilingual eAssembly` from [IBM Passport Advantage](https://www.ibm.com/software/passportadvantage/){: external}.

When you finish provisioning your instance, click **Setup** to open an onboarding checklist page to help you configure the instance. Or, you can select **Administration** and then **Setup** to access this onboarding checklist.

Items in that checklist correspond to each of the following steps. Click the action arrows on the checklist page that are associated with each item to complete the steps.

## Create a service ID and API key
{: #apikey}

You can use this API key later to enable Visual Studio Code to communicate with {{site.data.keyword.wca_short}}.

1. On the [Service IDs](https://cloud.ibm.com/iam/serviceids){: external} page, click **Create**.

1. Enter `{{site.data.keyword.wca_full_notm}} user` as the name for your service ID. Optionally, enter a description.

1. Click **Create**.

   You are redirected to the dashboard for your service ID, which includes tabs for **Access** and **API keys**.

1. Click the **API Keys** tab.

1. Click **Create**.

1. Enter `{{site.data.keyword.wca_full_notm}} API key` as the name for your API key. Optionally, enter a description.

1. Click **Create**.

1. Click **Download** or **Copy** and store the API key in a safe location.

   The key is only available for 296 seconds. Make sure to store it somewhere you can find it later.
   {: important}

   Although {{site.data.keyword.wca_short}} supports allowing multiple users to share the API key for the Service ID, the best practice is for each user to have their own API key. For more information about adding users to your instance, see [Managing IAM access for {{site.data.keyword.wcaz_short}}](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-wca-iam).

## Create a deployment space
{: #deploy_space-z}

The deployment space is the serving environment for {{site.data.keyword.wca_short}}.

1. In your {{site.data.keyword.wca_short}} instance, click the **Navigation Menu** ![Navigation Menu](images/menu.svg) icon, then select **Deployments**.

1. Click **New deployment space**.

1. Enter `Code Assistant` as the name for your deployment space. Optionally, enter a description.

1. In **Code assistant service**, select your instance.

1. Click **Create**.

1. A status window appears. After the space is created, click **Close**.

## Add the service ID as a space collaborator
{: #space_collab_z}

Enable the API to connect to your deployment space.

1. On the **Manage** tab of your deployment space, click **Access control**.

1. Click **Add collaborators** and select **Add service IDs** from the menu.

   A list of service IDs that are associated with your account appears.

1. Click the checkbox for the **{{site.data.keyword.wca_full_notm}} user** service ID that you created, and select **Editor** for the role.

1. Click **Add**.

   The service ID is added to the list of collaborators.

## Sign up for Db2
{: #db2}

{{site.data.keyword.wcaz_short_cap}} uses Db2 to store code input and output. If you don't already have an instance of Db2, {{site.data.keyword.cloud_notm}} can help you create one that is optimized for {{site.data.keyword.wcaz_short}}.

1. Select a region from the list of available regions.

1. Review the preselected Db2 pricing plan.

1. Click **Create**.

## Add the Db2 connection to your space
{: #your_space}

Enable the deployment space to send and retrieve code from Db2 storage.

1. On the **Assets** tab of your deployment space, click **New asset**.

1. In **New asset**, choose **Connect to a data source**.

1. In **Add connection**, select the IBM DB2 on Cloud connector, then click **Next**.

1. Click the **Select instance** button.

1. In **Select service**, select your Db2 service instance, and then click **Select**. Information from your service instance is added to the connection overview, details, credentials, and certificates.

   If your instance isn't listed, you can enter the name, details, credentials, and certificates manually.
   {: note}

1. Click **Create**.

   If you did not set a location and sovereignty, a window appears where you can confirm that you want to create the connection without setting these values. To accept, click **Create**. If you need to set the values, click **Cancel** and select **Location and sovereignty**.

   If your database is on another {{site.data.keyword.cloud_notm}} account, or if the automated population fails, see [Why can't I connect {{site.data.keyword.wcaz_short}} to my Db2 database?](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-troubleshoot-wcaz-connect-db2).

## Set up the Db2 database
{: #db2-configure}

After {{site.data.keyword.wcaz_short}} is set up in {{site.data.keyword.cloud_notm}}, the Db2 administrator needs to configure the database by loading the provided script.

To locate the script files:

1. Use [IBM Passport Advantage](https://www.ibm.com/software/passportadvantage/){: external} to download either:

   - The most recent `IBM watsonx Code Assistant for Z Multiplatform Multilingual eAssembly` 
   - Or the most recent individual image of `IBM watsonx Code Assistant Developer Tools Multilingual`

1. Open the `IBM watsonx Code Assistant Developer Tools Multilingual` image. 

   (The compressed file name is similar to this example: `IwCAfZ2e0_2.0_ML.zip`.)

1. In the `IBM watsonx Code Assistant Developer Tools Multilingual` folder, open the compressed file with the name similar to this example: `watsonx_Code_Assistant-for_Z-2.0.0.zip`.

1. Locate these files in the resulting folder:

   - `adscan_DB2oC_CreateObjects.sql`
   - `adscan_DB2oC_DeleteObjects.sql`

To configure Db2:

1. In the {{site.data.keyword.Db2_on_Cloud_short}} console, click the **Run SQL** ![Run SQL](images/SQL.svg) icon.

1. Click the plus (+) tab to add a script.

1. If you already have an initialized database from a previous version of {{site.data.keyword.wcaz_short}}, you need first clean up the old database. Click **From file** and browse to select `adscan_DB2oC_DeleteObjects.sql`, then click **Run all** to delete the schema and tables.

   The `adscan_DB2oC_DeleteObjects.sql` script is a sample. Depending on the state of the database, more or fewer steps might be required to completely reset the database. Contact your Db2 Administrator for assistance when you run the script.
   {: note}

1. To initialize a new database, click **From file** and browse to select `adscan_DB2oC_CreateObjects.sql`.

1. Click **Run all** to create the schema and tables.

## Set up your network
{: #cloud-setup-z-network-setup}

To ensure that your developers can connect the IDE extension or plug-in, you need to allow access to {{site.data.keyword.cloud_notm}} URLs. Make sure your organization's network allows access to:

- `https://iam.cloud.ibm.com/`
- `https://api.dataplatform.cloud.ibm.com/`

## Next steps
{: #next_steps_z}

You deployed and connected your {{site.data.keyword.cloud_notm}} components to your provisioned {{site.data.keyword.wca_short}} instance. You're ready to take your next steps and integrate with your IBM Z Open Editor in Visual Studio Code. For information, see [Set up a development environment](https://www.ibm.com/docs/en/watsonx/watsonx-code-assistant-4z/latest?topic=transform-set-up-development-environment){: external}.
