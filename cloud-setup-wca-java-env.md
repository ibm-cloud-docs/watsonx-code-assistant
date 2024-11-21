
---

copyright:
   years: 2024
lastupdated: "2024-11-21"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Setting up your enterprise Java environment
{: #cloud-setup-wca-java-env}



[{{site.data.keyword.wca_short}}]{: tag-blue}

[Standard plan]{: tag-purple} If you're using the Standard plan and want to work with enterprise Java applications, you need to set up your environment.
{: shortdesc}

## Set environment variables
{: #cloud-setup-wca-java-env-variables}

Set up your environment variables.

### JAVA_HOME
{: #cloud-setup-wca-java-env-java-home}

Set the `JAVA_HOME` environment variable the same way that you do for Maven. Set it to the JDK directory that contains the `/bin` directory so that your Java executable is in the `$JAVA_HOME/bin/java` path.

You can set the `JAVA_HOME` environment variable to build your application at a different version, for example, Java 11.

### PATH
{: #cloud-setup-wca-java-env-path}

Set the `PATH` environment variable to include the `mvn` executable.
- Windows: `mvn.cmd`
- macOS: `mvn`

If you use the Visual Studio Code terminal to set the environment variables, you need to restart Visual Studio Code to apply the changes.
{: note}




## Determining the Java developer kit
{: #cloud-setup-wca-java-env-extension-pack}

For Visual Studio Code, if you are using the [Extension Pack for Java](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-pack), {{site.data.keyword.wca_short}} determines the Java developer kit to use in this order of precedence:

| Order of precedence | Description |
| :---: | --- |
| 1 | Project-specific Java developer kit if set in the Microsoft Visual Studio extension |
| 2 | Globally-configured Java developer kit for autobuild in the Red Hat extension, which is `java.configuration.runtimes` in the `IDE settings.json` file |
| 3 | `java.jdt.ls.java.home` or `java.home` IDE settings if they are present |
| 4 | `JAVA_HOME` system environment variable, or else `JDK_HOME` |
| 5 | The Java developer kit in the system `PATH` |
{: caption="Java developer kit order" caption-side="bottom"}

To verify which Java developer kit is being used:

1. In Visual Studio Code, click **View**, then click **Output**.

1. In the Output panel, use the dropdown menu to select **WCA**.

1. Check for a message such as `Using the Java developer kit that is defined in <location> to run watsonx Code Assistant components. The path is: <path>`.

## Log settings
{: #cloud-setup-wca-java-env-maven-logs}

If necessary, you can adjust the logging activity.

### Maven logging
{: #cloud-setup-wca-java-env-maven-logs-jvm-config}

If you need to adjust the verbosity of Maven logging, you can adjust these settings.

In your `.mvn` folder, add these lines to `jvm.config`:

```text
-Dorg.slf4j.simpleLogger.defaultLogLevel=error 
-Dorg.slf4j.simpleLogger.log.net.sourceforge.pmd=error
```
{: codeblock}

### Log level setting for the extension
{: #cloud-setup-wca-java-env-maven-logs-level}

To adjust logging for the extension:

1. In Visual Studio Code, open the extension settings for {{site.data.keyword.wca_short}}.

1. In **Wca: Log level**, switch from the default of `INFO` to another setting such as `WARN`.