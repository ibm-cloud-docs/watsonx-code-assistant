---

copyright:
   years: 2024
lastupdated: "2024-11-21"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Modernizing Java applications
{: #wca-modernize-java}



[{{site.data.keyword.wca_short}}]{: tag-blue} [Standard plan]{: tag-purple}

You can modernize your WebSphere Application Server traditional application to Liberty. To modernize your application, you first upload a migration bundle or build and analyze your application, and then fix your application issues. 
{: shortdesc}

Before you begin, [set up your enterprise Java environment](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-cloud-setup-wca-java-env).
{: #before-mod}

Complete either the steps to upload your application migration bundle or the steps to analyze your application. After you complete one of these sets of steps, you can then fix issues with the migration. The steps to fix the issues are the same for both the migration bundle steps and application analysis. After you fix the issues, you have a modernized application.
{: #about-mod}

When {{site.data.keyword.wca_short}} analyzes your application, it excludes some third-party packages from code analysis by default. For more information, see [Third-party packages that are excluded from application analysis](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-wca-package-reference).
{: important}

## Using a migration bundle to modernize your application
{: #use-migrationb}

The following steps assume that you are using an [{{site.data.keyword.ta}}](https://www.ibm.com/docs/en/cta?topic=about-transformation-advisor){: external} migration bundle to modernize your application. The migration bundle contains a list of modernization issues that need to be addressed. It also contains automatically generated configuration information to enable the application to function properly in Liberty.

If you already uploaded a migration bundle and analyzed it for your project, uploading a new migration bundle overwrites the existing analysis.
{:important: .important}


1. In your IDE, right-click in the directory that you want to modernize, click **{{site.data.keyword.wca_short}}**, then click **Modernize to Liberty**. 


1. On the Modernize <*your application name*> page, upload the migration bundle.
    
   The IDE analyzes your project folder, gathers information about your application, and then uploads the migration bundle that {{site.data.keyword.ta_short}} generates.

    1. Click **Upload migration bundle**.
    1. Select the application bundle `.zip` file from the list and click **Open**.
       
       When the the process to upload the migration bundle completes, the Modernize <*your application name*> page displays the following configuration files that are in the bundle:
       * `server.xml` is the configuration file for Liberty and is required to start your application. 
       * `Containerfile` is required only to build a container image for your Liberty application.

    1. Select the files to add to your project and then click `Proceed`.
       * (Required) Select the `server.xml` file.
       * (Optional) Select the `Containerfile` file only if you are building a container image for your Liberty application.

       

    When the upload of the migration bundle completes, the issues to fix or review are displayed. 

1. [Fix issues with the application.](#wca-modernize-java-step-fix)
   
   Depending on the issues to fix, the ability to fix them can be automated, assisted, or self-directed. The issues on the **Additional information** tab don't require a code change, but you might need to verify or test them and make a code change if you want.

## Analyzing your application to modernize it 
{: #step-analyze}
 
 The following steps assume that you are analyzing your application instead of a using a {{site.data.keyword.ta_short}} migration bundle to modernize your application. The analysis provides you with a list of issues to address and a limited server configuration in the `server.xml` file. The `server.xml` file contains a list of features that your application uses, but it doesn't include other configuration information like database connections or JMS configurations.

1. In your IDE, right-click in the directory that you want to modernize, click **{{site.data.keyword.wca_short}}**, then click **Modernize to Liberty**. 
1. On your Modernize <*your application name*> page, expand **Analyze application**, and click **Start analysis**.
1. Select the analysis parameters, which define the rules that the application server is analyzed against.
   1. Select the application server source and the application server target.
   1. Optionally change the Java SE source, which is displayed automatically with a recommended value.
      
      The recommended value is based on the Java SE version that {{site.data.keyword.wca_short}} recommends for the application server source. Your application server might be using a different Java SE version than what is recommended. If it is, then change the Java SE source to the version that your application server uses.

      For example, {{site.data.keyword.wca_short}} recommends [Java SE 8 for WebSphere Application Server V8.5.5](https://www.ibm.com/docs/en/was/8.5.5?topic=waso-java-se-8-in-websphere-application-server-v85){: external} even though your application server might be using an earlier version of Java SE.
   1. Select the Java SE target.
   1. Click either **Analyze** or **Build and analyze**.

      Application analysis is done on the application binary. The application must be built before analysis begins. You can either automatically or manually build the application. 
      * To automatically build and analyze the application, click **Build and analyze**.
      * If you manually build the application, first build it and then click **Analyze**.

      After your application is built and analyzed, the issues to fix or review are displayed. 

1. [Fix issues with the application.](#wca-modernize-java-step-fix)

   Depending on the issues to fix, the ability to fix them can be automated, assisted, or self-directed. The issues on the **Additional information** tab don't require a code change, but you might need to verify or test them and make a code change if you want.

## Fixing issues and reviewing additional information for your application
{: #wca-modernize-java-step-fix}

The Modernize <*your application name*> page lists the following information:
* The application server source and the application server target
* The Java SE version source and the Java SE version target
* Links to a technology report, an inventory report, and an analysis report
* Tabs for issues to fix, which can be automated, assisted, or self-directed fixes, and additional information.

*  If you have an **Automated fixes** tab with one or more fixes, select the tab.

  Because {{site.data.keyword.wca_short}} completes the fixes for you, you do not need to make any code changes. The LLM is not used for automated fixes.
    1. Expand the Instructions and read them.
    1. Optionally open each issue to review the description of the issue.

       Depending on the issues that you have, you might see two sets of issues, one called **Modernize to Liberty** and the other called **Java Upgrade**.
    1. Click **Run automated fixes**.
    1. When **Run automated fixes** completes, click **Rebuild and refresh** to update the list of issues.
    1. If you have more automated fixes, repeat clicking **Run automated fixes** and **Rebuild and refresh** until all automated fixes are fixed.
*  If you have an **Assisted fixes** tab with one or more fixes, select the tab.

   You change the code, but {{site.data.keyword.wca_short}} provides instructions on how to change the code to fix the issues. The LLM is used to come up with the instructions that {{site.data.keyword.wca_short}} provides.
    1. Expand the Instructions and follow the instructions.
    1. For each issue, expand it.
    1. Click **Read more** to find out more about the issue.
    1. Click the file that is listed in the issue.

       The file opens in the editor.
    1. Click the **+** icon to view the issue details.
    1. Highlight the code snippet.
    1. Click **Help me** for assistance in fixing the issue.
      
       The issue displays one of the following types of assistance that you complete.
       * Instructions to resolve the issue
       * Code to repair the issue
       * Steps to complete before you then call the large language model (LLM) to resolve the issue.
    1. Follow the instructions in the chat to modify the code and fix the issue.
    1. As you fix issues, click **Rebuild and refresh** until all the assisted fixes are fixed.
*  If you have a **Self-directed fixes** tab with one or more fixes, select the tab.

   You change the code and determine how to fix the code, but you can get help from the chat.
    1. Expand the Instructions and follow the instructions.
    1. Expand each issue. 
    1. Click **Read more** to find out more about the issue.
    1. Click the file that is listed in the issue.

      The file opens in the editor.
    1. Click **Start chat**, which is displayed for each occurrence of the issue.

      The chat window opens so that you can get help for the occurrence.
    1. As you fix issues, click and **Rebuild and refresh** until all the self-directed fixes are fixed.
*  If you have an **Additional information** tab with a number of one or more on it, select the tab.

   These issues don't require a code change to migrate your code, but review the issues. They might need to be verified or tested.
    1. Expand the instructions and follow them.
    1. Click each issue.
    1. Click **Read more** to find out more about the issue.
    1. Click the file that is listed in the issue.

      The file opens in the editor.