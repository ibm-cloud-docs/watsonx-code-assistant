---

copyright:
   years: 2024, 2025
lastupdated: "2025-06-26"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Upgrading the Java version for your application
{: #wca-upgrade-java}

[{{site.data.keyword.wca_short}}]{: tag-blue} [Standard plan]{: tag-purple} 

To upgrade your Java code, you first build and analyze your application, and then fix any issues that are identified. Depending on the issues, the ability to fix them can be automated, assisted, or self-directed. 
{: shortdesc}

Before you begin, [set up your enterprise Java environment](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-cloud-setup-wca-java-env).

{{site.data.content.eclipse-multimodule}}

## Time required to analyze your code
{: #wca-upgrade-java-time-to-analyze-your-code}

The amount of time to analyze your application varies. The following times are typical.

| Time | Application details |
| --- | --- |
| Seconds to a few minutes | Fewer than 100 classes |
| 2 to 10 minutes | 20,000 to 50,000 lines of code |
| 10 or more minutes | 300,000 lines of code |
{: caption="Time required to analyze" caption-side="bottom"}

When {{site.data.keyword.wca_short}} analyzes your application, it excludes some third-party packages from code analysis by default. For more information, see [Third-party packages that are excluded from application analysis](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-wca-package-reference).
{: important}

## Analyzing your application to upgrade the Java version 
{: #wca-upgrade-step-analyze}

The analysis provides you with a list of issues to address. After you fix the issues, the Java version for your application is upgraded.

If you revert the changes to your code, you must click **Return to analyze** and do a full analysis if you want to do the Java upgrade again.
 
1. In your IDE, right-click any item in the hierarchy in the directory of the application that you want to upgrade.

1. Use either path to start the upgrade process. Both are the same:

   - Click **{{site.data.keyword.wca_short}}**, then click **Upgrade Java Version**.
   - Click **Modernize Java Applications**, then click **Upgrade Java Version**.

1. On your Upgrade <*your application name*> page, select the analysis parameters, which define the rules that the application is analyzed against.

   1. Optionally change the Java source, which is displayed automatically with a recommended value.
      
      The Java source version is the Java version that you are upgrading from. Based on the Java version detected in the build configuration, {{site.data.keyword.wca_short}} recommends a Java version to use as the source. You can choose a different Java version from the list of supported Java versions if that is appropriate for your application. The build configuration is in the Maven `pom.xml` file.

      The Java version that is recommended is either the Java version that is detected in the build configuration, or is the best available Java version given the Java version that was detected. For example, if Java 9, which is not supported, is specified in the build configuration, Java 8 is the recommended Java version. Java 8 is recommended since it is the closest supported Java version for the analysis, and since it is earlier than the detected Java version.

      The minimum-supported Java version is Java 6.
      {: important}

   1. Select the Java target.

      The Java target version is the Java version that you are upgrading your Java application to. The target versions that you can select from are long-term (LTS) Java releases.

   1. Click either **Analyze** or **Build and analyze**.

      Application analysis is done on the application binary. The application must be built before analysis begins. You can either automatically or manually build the application. 
      - Click **Build and analyze** to automatically build and analyze the application.
      - Click **Analyze** after you manually build the application.

      After your application is built and analyzed, the issues to fix or review are displayed. Depending on the issues to fix, the ability to fix them can be automated, assisted, or self-directed. These issues to review don't require a code change to migrate your code. However, they might need to be verified or tested.

      When you click **Build and analyze**, the application is built at its current Java source version, so it can be analyzed for Java upgrade issues. Make sure to configure the IDE with the Java developer kit of the Java source version, so the IDE can successfully build the application.

      When building and analyzing, if you have issues with a multimodule project that includes a submodule with `liberty-assembly` packaging, run `mvn install` at the root level of the project and try again.
      {: note}

### Why is a .class file included in an analysis report instead of the .java file?
{: #wca-upgrade-java-class-file}

When you run an analysis of a binary (JAR/WAR/EAR), the issues are always discovered in the class files. When the binary scanner is run outside of {{site.data.keyword.wca_short}}, it has no access to the source code, so the .class file is included in the analysis report. When you import a migration plan, or when you run an analysis inside {{site.data.keyword.wca_short}}, the reports show references to class files, but {{site.data.keyword.wca_short}} links the .class file to the .java file, and the .java files are shown in the {{site.data.keyword.wca_short}} UI.

## Fixing issues and reviewing additional information for your application
{: #wca-upgrade-java-step-fix}

The Upgrade <*your application name*> page lists the following information:
- The Java version source and the Java version target
- Links to a technology report, an inventory report, and an analysis report
- Tabs for issues to fix, which can be automated, assisted, or self-directed fixes, and for additional information
   
The target Java developer kit is required when you run automated fixes and when you build the application after the Java version target changes are made. Make sure that the target Java developer kit is configured for your IDE. 
- The Eclipse IDE extension automatically tries to find the correct Java developer kit that matches the Java version target from the set of all configured Java developer kits in the IDE. 
- In the Visual Studio Code IDE, you must manually change the Java developer kit configuration.


### Completing automated fixes
{: #wca-upgrade-autofix}

If you have an **Automated fixes** tab with one or more fixes, select the tab.

Because {{site.data.keyword.wca_short}} completes the fixes for you, you do not need to make any code changes. The large language model (LLM) is not used for automated fixes.
1. Expand the Instructions and read them.
1. Optionally open the issue to review the description of the issue.
1. Click **Run automated fixes**.
   - The Automated fixes are fixed.
   - External issues remain in the list until you update the associated dependency. 
1. When **Run automated fixes** completes, click **Rebuild and refresh** to update the list of issues.

If the automated fixes fail to run and produce compilation errors in the console output, make sure to update the version of the `maven-compiler` plug-in to 3.13.0 or newer.
{: note}

When running automations, if you have issues with a multimodule project that includes a submodule with `liberty-assembly` packaging, run `mvn install` at the root level of the project and try again.
{: note}

### Completing assisted fixes
{: #wca-upgrade-assistedfix}

If you have an **Assisted fixes** tab with one or more fixes, select the tab.

Although you fix your code, {{site.data.keyword.wca_short}} assists you by providing suggestions in the chat on how to change your code.

The level of assistance available varies with the issue. The assisted fixes help you to fix the issue, and sometimes a code suggestion gets you all the way or most the way. Other times, the code suggestion might be as simple as removing an old API to prevent a compilation failure, and no further action is required from you. It is important to follow steps for each assisted fix to understand the value and limitations of each assisted fix. In cases where a complete code suggestion is not provided, you can think of the assisted fix as a conversation starter in the chat. Continue to engage with the chat to build your understanding of the issue and its resolution.

For a list of issues associated with assisted fixes, see the [Assisted fixes reference](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-wca-assisted-fixes-reference).

To use assisted fixes:
1. Expand the Instructions and follow the instructions.
1. For each issue, expand it.
1. Click **Read more** to expand the issue.
1. Click the file that is listed in the issue.
   The file opens in the editor.
1. Expand the issue to view the issue details.
1. If in the details you are directed to select a code snippet, select it.
1. Click **Help me** for assistance in fixing the issue.
     
   If you are using Visual Studio Code, the following restrictions apply:
   - Make sure that you select Java code in only one active editor.
   - Make sure that the active editor in which you selected Java code is in a different editor group than the **Modernize to Liberty** or **Java Upgrade** view.
1. Follow the code suggestions in the chat to modify the code and fix the issue.

   Sometimes, the chat provides an informational response instead of a code suggestion.
      
1. As you fix issues, click **Rebuild and refresh** until all assisted fixes are fixed.

### Completing self-directed fixes
{: #wca-upgrade-selffix}

If you have a **Self-directed fixes** tab with one or more fixes, select the tab.

You change the code and determine how to fix the code, but you can get help from the chat.
1. Expand the Instructions and follow the instructions.
1. Expand each issue. 
1. Click **Read more** to expand the issue.
1. Click the file that is listed in the issue.
   The file opens in the editor.
1. Click **Start chat**, which is displayed for each occurrence of the issue.
   The chat window opens so you can get help for the occurrence. For example, you can ask the code assistant what the current code does. Or, you can ask if an alternative implementation exists for the problematic code.
1. As you fix issues, click **Rebuild and refresh** until all self-directed fixes are fixed.
 
### Addressing additional information
{: #wca-upgrade-additionalinfo}

If you have an **Additional information** tab with a number of one or more on it, select the tab.

The issues listed on the tab are determined the same way that issues on other tabs are determined. Although the additional information issues do not require a change to your code, review the issues so you can ensure that your application is working when your code is migrated.


The additional information might indicate issues, such as minor behavioral changes in an API and what to do about them. 

- Expand the instructions and follow them.

- Click each issue.
   - Click **Read more** to expand the issue.
   - Click the link on the file that is listed in the issue to review the code.

### Working on external issues outside the current application
{: #wca-upgrade-external-issues}

While you work on fixes, some might be categorized as external issue occurrences outside the current application. The source code for these issues are in specified archives that are not part of the current source application.

If the archive is a library that your organization owns:

1. You can open its associated source code as a separate application and use {{site.data.keyword.wca_short}} to remediate the issues there. 

1. Then, you can update your current application to use the new remediated version.

If the archive is a library that your organization doesn’t own:

1. You need to update to a version that does not contain this issue. If no such version exists, you might need to use an alternative technology.

1. You can start a conversation with {{site.data.keyword.wca_short}} for help with determining a replacement. To start, try asking `What is the library X used for?` or `Is it easy to replace?`. Continue the conversation to get more information for your specific usage of the library.
