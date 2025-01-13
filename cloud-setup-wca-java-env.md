---

copyright:
   years: 2024, 2025
lastupdated: "2025-01-13"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Setting up your enterprise Java environment
{: #cloud-setup-wca-java-env}

[{{site.data.keyword.wca_short}}]{: tag-blue} [Standard plan]{: tag-purple} 

If you're using the Standard plan and want to work with enterprise Java applications, you need to set up your environment for your IDE.
{: shortdesc}

## Java requirements
{: #cloud-setup-wca-java-env-requirements}

The requirements to use {{site.data.keyword.wcaej_short}} are:

| Item | Details |
| --- | --- |
| Java | Java SE 11 with Java Developer Kit 11, or a later version |
| Maven | Use Maven to build your application |
{: caption="System requirements" caption-side="bottom"}

## Visual Studio Code setup
{: #cloud-setup-wca-java-env-vscode}

- [Set environment variables](#cloud-setup-wca-java-env-variables)
- [Determining the Java developer kit](#cloud-setup-wca-java-env-extension-pack)
- [Set logging level](#cloud-setup-wca-java-env-log-level-vscode)

### Set environment variables
{: #cloud-setup-wca-java-env-variables}

Set up your environment variables.

#### JAVA_HOME
{: #cloud-setup-wca-java-env-java-home}

Set the `JAVA_HOME` environment variable the same way that you do for Maven. Set it to the JDK directory that contains the `/bin` directory so that your Java executable file is in the `$JAVA_HOME/bin/java` path.

You can set the `JAVA_HOME` environment variable to build your application at a different version, for example, Java 11.

#### PATH
{: #cloud-setup-wca-java-env-path}

Set the `PATH` environment variable to include the `mvn` executable file.
- Windows: `mvn.cmd`
- macOS: `mvn`

If you use the Visual Studio Code terminal to set the environment variables, you need to restart Visual Studio Code to apply the changes.
{: note}

For macOS operating systems, the environment variables might not be set as expected when you run Eclipse. To fix the problem, you can restart Eclipse through the Finder tool by right-clicking your Eclipse application and choosing Show Package Contents. Enter the newly displayed Contents folder, select MacOS, and then run Eclipse by clicking the executable code.
{: note}

### Determining the Java developer kit
{: #cloud-setup-wca-java-env-extension-pack}

For Visual Studio Code, if you are using the [Extension Pack for Java](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-pack), {{site.data.keyword.wca_short}} determines the Java developer kit to use in this order of precedence:



| Order of precedence | Description |
| :---: | --- |
| 1 | Globally-configured Java developer kit for automatic building in the Red Hat extension, which is `java.configuration.runtimes` in the `IDE settings.json` file |
| 2 | `java.jdt.ls.java.home` or `java.home` IDE settings if they are present |
| 3 | `JAVA_HOME` system environment variable, or else `JDK_HOME` |
| 4 | The Java developer kit in the system `PATH` |
{: caption="Java developer kit order" caption-side="bottom"}

When {{site.data.keyword.wcaej_short}} features are used, such as Java modernization or upgrade, you can verify which Java developer kit is being used:

1. In Visual Studio Code, click **View**, then click **Output**.

1. In the Output view, use the dropdown menu to select **WCA**.

1. Check for a message such as `Using the Java developer kit that is defined in <location> to run watsonx Code Assistant components. The path is: <path>`.



### Set logging level
{: #cloud-setup-wca-java-env-log-level-vscode}

To adjust logging for the Visual Studio Code extension:

1. In Visual Studio Code, open the extension settings for {{site.data.keyword.wca_short}}.

1. In **Wca: Log level**, switch from the default of `INFO` to another setting such as `WARN`.

## Eclipse IDE setup
{: #cloud-setup-wca-java-env-eclipse}

### Determining the Java installation
{: #cloud-setup-wca-java-env-eclipse-java-install}

For Eclipse, the Java installation is determined in this order:
- The installation that is configured in the project's build path
- The default Java installation for the IDE

For application modernization and upgrade, the automated fixes use the Java developer kit installation that best matches the target Java version that you chose. You need to:
1. Install the Java developer kit.
1. In the Eclipse IDE settings, open the **Java** section and add the installation to the **Installed JREs**.

### Maven setup
{: #cloud-setup-wca-java-env-eclipse-maven}

Setting Maven on the path is optional. The Maven executable installation is determined in this order:
- Check for a Maven Wrapper in the project
- Check if `mvn` is available on the PATH
- Generate a Maven Wrapper in the project root by using the default Maven version for the Eclipse IDE.
