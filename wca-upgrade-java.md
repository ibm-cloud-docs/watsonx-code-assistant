
---

copyright:
   years: 2024
lastupdated: "2024-11-21"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Upgrading the Java version for your application
{: #wca-upgrade-java}



[{{site.data.keyword.wca_short}}]{: tag-blue}

[Standard plan]{: tag-purple} To upgrade your Java code, you first build and analyze your application, and then fix any issues that are identified. Depending on the issues to fix, the ability to fix them can be automated, assisted, or self-directed. 
{: shortdesc}

Before you begin, [set up your enterprise Java environment](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-cloud-setup-wca-java-env).
{: #before-upgradej}

When {{site.data.keyword.wca_short}} analyzes your application, it [excludes third-party packages from code analysis by default](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-wca-package-reference).
{:important: .important}

## Analyzing your application to upgrade the Java version 
 {: #step-analyze}
 
1. In your IDE, right-click in the directory that you want to upgrade, click **{{site.data.keyword.wca_short}}**, then click **Upgrade Java Version**. 
1. On your Upgrade <*your application name*> page, expand **Analyze application**, and click **Start analysis**.
1. Select the analysis parameters, which define the rules that the application server is analyzed against.

   1. Optionally change the Java runtime source, which is displayed automatically with a recommended value.
      
      The Java runtime source version is the one that {{site.data.keyword.wca_short}} recommends for the application source. Your application might be using a different Java runtime version than what is recommended. If it is, then change the Java runtime source to the version that your application uses.

   1. Select the Java runtime target.
   1. Click either **Analyze** or **Build and analyze**.

      Application analysis is done on the application binary. The application must be built before analysis begins. You can either automatically or manually build the application. 
      * Click **Build and analyze** to automatically build and analyze the application.
      * Click **Analyze** after you manually build the application.

      After your application is built and analyzed, the issues to fix or review are displayed. Depending on the issues to fix, the ability to fix them can be automated, assisted, or self-directed. These issues to review don't require a code change to migrate your code. However, they might need to be verified or tested.

## Fixing issues and reviewing additional information for your application
{: #wca-upgrade-java-step-fix}

The Upgrade <*your application name*> page lists the following information:
* The Java runtime version source and the Java runtime version target
* Links to a technology report, an inventory report, and an analysis report
* Tabs for issues to fix, which can be automated, assisted, or self-directed fixes, and for additional information
  

*  If you have an **Automated fixes** tab with one or more fixes, select the tab.

  Because {{site.data.keyword.wca_short}} completes the fixes for you, you do not need to make any code changes. The LLM is not used for automated fixes.
    1. Expand the Instructions and read them.
    1. Optionally open the issue to review the description of the issue.
    1. Click **Run automated fixes**.
    1. When **Run automated fixes** completes, click **Rebuild and refresh** to update the list of issues.
    1. If you have more automated fixes, repeat clicking **Run automated fixes** and **Rebuild and refresh** until all automated fixes are fixed.
    1. Update the Java runtime version in your build file to match the Java runtime version target.

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
   1. Update the Java runtime version in your build file to match the Java runtime version target.

*  If you have a **Self-directed fixes** tab with one or more fixes, select the tab.

   You change the code and determine how to fix the code, but you can get help from the chat.
   1. Expand the Instructions and follow the instructions.
   1. Expand each issue. 
   1. Click **Read more** to find out more about the issue.
   1. Click the file that is listed in the issue.

      The file opens in the editor.
   1. Click **Start chat**, which is displayed for each occurrence of the issue.

      The chat window opens so that you can get help for the occurrence.
   1. As you fix issues, click **Rebuild and refresh** until all the self-directed fixes are fixed.
 

*  If you have an **Additional information** tab with a number of one or more on it, select the tab.

   These issues don't require a code change to migrate your code, but review the issues. They might need to be verified or tested.
   * Expand the instructions and follow them.

     The instructions explain the severity of the issues, whether they are critical, warning, or informational issues.
   * Click each issue.
     * Click **Read more** to find out more about the issue.
     * Click the link on the file that is listed in the issue to review the code.

       The file opens in the editor.

       How you address the issue depends on the severity of the issue along with information supplied that is specific to the issue.
