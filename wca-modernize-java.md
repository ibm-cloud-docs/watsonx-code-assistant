
---

copyright:
   years: 2024
lastupdated: "2024-09-19"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Modernizing Java applications
{: #wca-modernize-java}



You can modernize your WebSphere Application Server traditional application to Liberty. To modernize your application, you can use a migration bundle or scan your application directly if a migration bundle is not available.
{: shortdesc}


To scan your application directly, see the **View other options** section of your IDE panel.

## Before you begin

Before you begin, [set up your environment](cloud-setup-wcaej.md).

## Procedure

The following example assumes that you are using a migration bundle to modernize your application.

1. In your IDE, right-click in the directory that you want to modernize, and click **Watson Assistant for Enterprise Java Applications**, then click **Modernize to Liberty**. 

1. Start the modernization process by selecting a migration bundle to get the appropriate configuration files and a list of modernization issues.

  * You can review the migration bundle by clicking a file name and loading it into the editor.

    * The `server.xml` file is the server configuration file for WebSphere Liberty. When you scan your application that is deployed in the traditional WebSphere Application Server environment, the server.xml file that is generated in the migration bundle contains the full configuration for your application.

1. Add the files in the migration bundle to your application project by clicking **Add files to project**.

  * The modernization panel displays any modernization issues.

    * **Important**: Any critical issues must be fixed so that the modernized application can be built successfully.

1. Click **Run auto fixes** to automatically fix the modernization issues.

1. If any issues are unresolved after the automatic fixes complete, resolve any issues manually by clicking the **Assisted fixes** tab.

  1. Open the source file, select a code block, and click **Help me** next to the issue.

     * Details on how to fix the issue are provided in a chat window. The suggested fix might or might not be confined to the selected file.

  1. Make the suggested manual fix.

  1. Repeat these steps to fix the issues in the source files.

1. After you make any necessary changes, click **Build and Refresh**.

  * The code assistant runs a new build and scans the application.

    * Any resolved issues disappear from the list of modernization issues.

1. If any modernization issues exist, repeat the steps to fix the issues.

  * Depending on the issues, automatically fix the issues, fix the issues with assistance, or do both. 

## IBM Cloud Transformation Advisor

You can use IBM Cloud Transformation Advisor to analyze your traditional WebSphere environment and generate a migration bundle, which is a set of resources that {{site.data.keyword.wca_short}} can use to accelerate your modernization effort.

- [Learn about IBM Cloud Transformation Advisor](https://www.ibm.com/products/cloud-pak-for-applications/transformation-advisor){: external}
- [Access the IBM Cloud Transformation Advisor downloads](https://www.ibm.com/support/pages/node/6958773){: external}
