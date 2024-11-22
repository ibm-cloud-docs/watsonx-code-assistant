
---

copyright:
   years: 2024
lastupdated: "2024-11-22"

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
 
1. Click a file or directory in the project that you want to upgrade, click **{{site.data.keyword.wca_short}}**, then click **Upgrade Java Version**. 
1. On your Upgrade <*your application name*> page, select the analysis parameters, which define the rules that the application is analyzed against.

   1. Optionally change the Java source, which is displayed automatically with a recommended value.
      
      The Java source version is the Java version that you are upgrading from. Based on the version detected in the build configuration, {{site.data.keyword.wca_short}} recommends a version to use as the source. You can choose a different version from the list of supported versions if that is appropriate for your application.

      The version that is recommended is either the version that is detected in the build configuration, or is the best available version given the version that was detected. For example, if Java 9, which is not supported, is specified in the build configuration, Java 8 is the recommended version. Java 8 is recommended since it is the closest supported version for the analysis, and since it is earlier than the detected version.

   1. Select the Java target.
   1. Click either **Analyze** or **Build and analyze**.

      Application analysis is done on the application binary. The application must be built before analysis begins. You can either automatically or manually build the application. 
      * Click **Build and analyze** to automatically build and analyze the application.
      * Click **Analyze** after you manually build the application.

      After your application is built and analyzed, the issues to fix or review are displayed. Depending on the issues to fix, the ability to fix them can be automated, assisted, or self-directed. These issues to review don't require a code change to migrate your code. However, they might need to be verified or tested.

## Fixing issues and reviewing additional information for your application
{: #wca-upgrade-java-step-fix}

The Upgrade <*your application name*> page lists the following information:
* The Java version source and the Java version target
* Links to a technology report, an inventory report, and an analysis report
* Tabs for issues to fix, which can be automated, assisted, or self-directed fixes, and for additional information
  

*  If you have an **Automated fixes** tab with one or more fixes, select the tab.

  Because {{site.data.keyword.wca_short}} completes the fixes for you, you do not need to make any code changes. The large language model (LLM) is not used for automated fixes.
    1. Expand the Instructions and read them.
    1. Optionally open the issue to review the description of the issue.
    1. Click **Run automated fixes**.
       * The Automated fixes are fixed.
       * External issues remain in the list until you update the associated dependency. 
    1. When **Run automated fixes** completes, click **Rebuild and refresh** to update the list of issues.

*  If you have an **Assisted fixes** tab with one or more fixes, select the tab.

  Although you fix your code, {{site.data.keyword.wca_short}} assists you by providing suggestions in the chat on how to change your code.
    1. Expand the Instructions and follow the instructions.
    1. For each issue, expand it.
    1. Click **Read more** to find out more about the issue.
    1. Click the file that is listed in the issue.

       The file opens in the editor.
    1. Expand the issue to view the issue details.
    1. If you are told to do so, select the code snippet in your file as described in the issue.
    1. Click **Help me** for assistance in fixing the issue.
    1. Follow the code suggestions in the chat so that you modify the code to fix the issue.
    
       In some cases, the chat provides an informational response instead of a code suggestion.
      
   1. As you fix issues, click **Rebuild and refresh** until all the assisted fixes are fixed.


*  If you have a **Self-directed fixes** tab with one or more fixes, select the tab.

   You change the code and determine how to fix the code, but you can get help from the chat.
   1. Expand the Instructions and follow the instructions.
   1. Expand each issue. 
   1. Click **Read more** to find out more about the issue.
   1. Click the file that is listed in the issue.

      The file opens in the editor.
   1. Click **Start chat**, which is displayed for each occurrence of the issue.

      The chat window opens so that you can get help for the occurrence. For example, you can ask the code assistant what the current code does. Or, you can ask if an alternative implementation exists for the problematic code.
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
