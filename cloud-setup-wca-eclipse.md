
---

copyright:
   years: 2024
lastupdated: "2024-09-19"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Adding the plugin for the Eclipse IDE
{: #cloud-setup-wca-eclipse}



Add {{site.data.keyword.wca_short}} to your Eclipse IDE.
{: shortdesc}

The plugin you need depends upon the plan you are using.

| Plan | Plugin |
| --- | --- |
| Trial | [plugin link](link){: external} |
| Essentials | [plugin link](link){: external} |
| Standard | [plugin link](link){: external} |
{: caption="Plugins by plan" caption-side="bottom"}

## Install the plugin
{: #cloud-setup-wca-eclipse-install}

To install the plugin:



1. In your Eclipse editor, click **Help**, then click **Install New Software**.

1. In the Install dialog, click **Add**.

1. In the Add Repository dialog, click **Archive**, then choose the ZIP file.

1. Enter a name in the **Name** field, then click **Add**.

1. Click the check box for the plugin, then click **Next**. 

1. On Install Details, review the items, then click **Next**.

1. On Review Licenses, read the license, click to agree, then click **Finish**.

1. On Trust Artifacts, click the **Type** check box, then click **Trust Selected**.

1. You need to restart Eclipse. On Software Updates, click **Restart Now**.

To open {{site.data.keyword.wca_short}}:

1. After Eclipse restarts, click **Window**, select **Show View**, then click **Other**.

1. In the Show View dialog, open the **{{site.data.keyword.wca_short}}** folder, select **Chat**, then click **Open**.

1. Use your IBM w3id to sign in.

## Setting up your enterprise Java environment
{: #cloud-setup-wca-eclipse-environment}

If you're using the Standard plan and want to work with enterprise Java applications, you need to set up your environment.

**JAVA_HOME**
Set the JAVA_HOME environment variable the same way that you do for Maven. Set it to the JDK directory that contains the /bin directory  so that your Java executable is in the $JAVA_HOME/bin/java path.

You can set the JAVA_HOME environment variable to build your application at a different level, for example, Java 11. The Java version that runs in the IDE uses Java 17 for the private preview.

**PATH**
Set the PATH environment variable to include the mvn executable.
- Windows: `mvn.cmd`
- macOS: `mvn`

For macOS operating systems, the environment variables might not be set as expected when you run Eclipse. To fix the problem, you can restart Eclipse through the Finder tool by right-clicking your Eclipse application and choosing Show Package Contents. Enter the newly displayed Contents folder, select MacOS, and then run Eclipse by clicking the executable code.

## Uninstall the plugin
{: #cloud-setup-wca-eclipse-uninstall}

If you need to uninstall {{site.data.keyword.wca_short}}, follow these steps:

1. In your Eclipse editor, click **Help**, then click **Install New Software**.

1. Click **What is already installed?**.

1. On the **Installed Software** tab, select **{{site.data.keyword.wca_short}}**, then click **Uninstall**.

1. On Uninstall, review the items, then click **Finish**.

1. You need to restart Eclipse. On Software Updates, click **Restart Now**.

