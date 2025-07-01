---

copyright:
   years: 2024, 2025
lastupdated: "2025-07-01"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Generating unit tests
{: #wca-generate-test}

[{{site.data.keyword.wca_short}}]{: tag-blue}

Generate unit tests for various programming languages from the chat, the CodeLens in the editor, or the explorer.
{: shortdesc}

The following table lists the type of unit test for each plan.

| Plan | Unit test | Description |
| --- | --- | --- |
| [Trial plan]{: tag-magenta} [Essentials plan]{: tag-green} | Basic | Uses generative AI to provide a basic unit test. No extra code analysis is required. |
| [Standard plan]{: tag-purple} | Enhanced | Requires a built application, and uses a code analysis and generative AI to provide an enhanced unit test for Java methods and classes. |
{: caption="Unit test types" caption-side="bottom"}

{{site.data.content.eclipse-multimodule}}

## Language support 
{: #wca-generate-test-languages} 

Test generation is available for the following languages:

{{site.data.content.language-support}}

{{site.data.content.language-support-methods}}

## Dependencies
{: #wca-generate-test-dependencies}

[Standard plan]{: tag-purple} For Java, make sure that the `pom.xml` file includes the following dependencies:
- JUnit - A minimum of JUnit 5 is required
- Mockito - A minimum of Java 9 is required

The following sample `pom.xml` file shows the dependencies with example versions. In your file, include the dependencies and versions that you are using.
 
```code  
   <dependencies>
      <dependency>
         <groupId>org.junit.jupiter</groupId>
         <artifactId>junit-jupiter-api</artifactId>
         <version>5.10.0</version>
         <scope>test</scope>
      </dependency>
      <dependency>
         <groupId>org.mockito</groupId>
         <artifactId>mockito-core</artifactId>
         <version>5.12.0</version>
         <scope>test</scope>
      </dependency>
      <dependency>
         <groupId>org.mockito</groupId>
         <artifactId>mockito-junit-jupiter</artifactId>
         <version>5.12.0</version>
         <scope>test</scope>
      </dependency>
   </dependencies>
```

## Using a chat command to generate a unit test
{: #wca-gen-chat}

You can use the `/unit-test` command in chat to generate a test for a referenced class, file, function, or method in the active workspace.

Use this syntax:

`/unit-test [using <test_framework>] <code reference> [similar to (<unit test reference>)] [additional instructions]`

- Make sure to start the prompt with `/unit-test`, followed by the rest of the syntax.

- `[using <test_framework>]` is optional. If you don't specify the framework, {{site.data.keyword.wca_short}} uses the test framework from your settings.

- For `<code reference>`, type the `@` symbol to see a list of classes, files, functions, and methods from your workspace. Use one class, file, function, or method reference at a time.

   {{site.data.content.reference-file-size-limit}}

- `[similar to (<unit test reference>)]` is optional. Use to provide an example of how the generated unit test is expected to look. You can use a method reference in the `similar to` option if required.

- The `[additional instructions]` are optional. Add instructions if you want specific details.

Next, {{site.data.keyword.wca_short}} processes the request and in the chat displays the generated unit test for the code that you selected. 

- [Essentials plan]{: tag-green} Copy the unit test to a file where you have unit tests for your application.

- [Standard plan]{: tag-purple} Copy the unit test to a file in the high-level directory structure `src/test/java`. For example, copy the unit test file to `.../src/test/java/com/acme/modres/OrdersAlertFilter.java`.

## Using the CodeLens in the editor to generate unit tests
{: #wca-gen-option}

In the IDE editor, the CodeLens shows a line of generative AI options that precedes code blocks and snippets.  

{{site.data.content.codelens-delay}}

1. Click the **Unit Test** option that immediately precedes a code block to generate a unit test. 

   In the following code example, the `Explain | Document | Unit Test` options immediately precede the `protected void` keywords.

   ![CodeLens example](images/codelens.png){: caption="CodeLens example"}

   The {{site.data.keyword.wca_short}} chat window opens, displays the `/unit-test @<*item name*>` command, runs the command, and displays the unit test.

1. [Essentials plan]{: tag-green} Copy the unit test to a file where you have unit tests for your application.

1. [Standard plan]{: tag-purple} Copy the unit test to a file in the high-level directory structure `src/test/java`. For example, copy the unit test file to `.../src/test/java/com/acme/modres/OrdersAlertFilter.java`.

### Disabling CodeLens
{: #wca-generate-test-disable-codelens}

If you want to disable the CodeLens options, you can change the setting for the extension or plug-in.

In Visual Studio Code:

1. Open the settings for the extension.

1. Clear the `Enable CodeLens` setting.

In Eclipse:

1. Open the settings for the Eclipse IDE.

1. In the **watsonx Code Assistant Settings** entry, clear the `Enable CodeLens` setting.

1. Click **Apply and close**. 

## Using the explorer to generate unit tests
{: #wca-gen-context}

To generate a unit test from the Explorer (Visual Studio Code) or Project Explorer (Eclipse):

1. Expand your application to the code for which you want to generate a unit test.

1. Right-click the code, click **{{site.data.keyword.wca_short}}**, then click **Unit Test**.

1. The {{site.data.keyword.wca_short}} chat displays the `/unit-test` command for the code that you selected for unit testing. The following syntax is used in the command:

   `/unit-test @<*item syntax*>`

   The following syntax examples are for a file, a class, and a method.

   * File: `/unit-test @OrdersAlertFilter.java`
   * Class: `/unit-test @OrdersAlertFilter`
   * Method: `/unit-test @DoFilter()`


   {{site.data.keyword.wca_short_cap}} processes the request and in the chat displays the generated unit test for the code that you selected. 

1. [Essentials plan]{: tag-green} Copy the unit test to a file where you have unit tests for your application.

1. [Standard plan]{: tag-purple} Copy the unit test to a file in the high-level directory structure `src/test/java`. For example, copy the unit test file to `.../src/test/java/com/acme/modres/OrdersAlertFilter.java`.

## Fixing unit tests
{: #wca-generate-test-fix}

[Standard plan]{: tag-purple} Fixing unit tests is only available with the {{site.data.keyword.wcaej_short}} Visual Studio Code extension or Eclipse plug-in, version 1.1.0 and later.

If you are using {{site.data.keyword.wca_short}} on-premises as a service of IBM Software Hub, version 5.2 or later is required.
{: note} 

You can start a unit test fix for any Java file that is in an application test folder of a Java project.

The **Fix unit test** menu item is only for Java files in the `src/test/java` folder of a Java project or application. This menu item is for fixing a unit test for compile or runtime errors. Usually you generate the test by selecting **Unit Test** and copying the results from the chat into a file in the `src/test/java` folder.

To fix a unit test:

1. Open the Explorer view.

1. In the test folder, right-click an existing test file, click **{{site.data.keyword.wca_short}}**, and then click **Fix unit test**.
   
   The process runs in two phases:
   - **Compile fix phase**: Updates the file in the editor with clean compiled code 
   - **Runtime fix phase**: Checks the unit test for runtime errors 

   If failures occur during the process, the code is commented out. For example, if compilation errors are fixed but the resulting code then has runtime errors.
   {: note}
   
1. When the two phases are complete, the unit test file is updated and can be run.

Keep the following points in mind:
- If a reference with a fully qualified class name or a full qualified method is missing from the generated test case, the unit test fix is canceled.
- Your application must be at Java version 9 or later to fix a unit test. 
- Your application must be analyzed before the unit test can be fixed.
- Test generation sometimes generates unnecessary imported classes, interfaces, or packages. If the imports cause compile or runtime errors, you can comment them out.
