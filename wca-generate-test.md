
---

copyright:
   years: 2024
lastupdated: "2024-09-19"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Generating unit tests
{: #wca-generate-test}



Depending on the extension that you are using, you can generate tests with the Visual Studio Code extension or JUnit tests with the Eclipse extension.
{: shortdesc}

## Generating tests with the Visual Studio Code extension
{: #wca-generate-test_visual-studio}

You can generate tests with the Visual Studio Code extension in two ways. You can click either the project root folder or the Java file from the project view. You can open the code lens inside the editor so that the unit test menu display.

### Before you begin tests
{: #wca-before-tests}

Set up your environment.

### Automatically generate tests in your Visual Studio Code extension for the entire application
{: #wca-auto-generate-test-visual-studio}

Right click the project root folder in the Visual Studio Code Explorer view, select **{{site.data.keyword.wca_short}}**, then select **Generate Tests**.

- Clickable links to the generated test files are displayed on the Unit test View panel of your IDE.
- The test files are in the `src/test/java` subfolder of the application. This subfolder is created when the test generation initially runs.
- Tip: Generating all tests for an entire application can be a long running process. Consider generating testcases on a class by class basis if running the testcases all at once is an issue.

### Automatically generate tests in your Visual Studio Code extension for a specific class in the application
{: #wca-generate-test-specific-class}

Right click on the class within your Java application in the Visual Studio Code extension and select **{{site.data.keyword.wca_short}}**, then select **Generate Tests**.

- A clickable link to the generated test file is displayed on the Unit test View panel of your IDE.
- This file will exists in the `src/test/java` subfolder of the application. This subfolder is created when the test generation initially runs.

Review a test file that displays in the Unit test files panel by clicking the file.

- The file opens in the editor.

If you want to generate tests again for the same application or application class, but don't want the existing test files overwritten, change the name of the test files by removing the WCA\_ prefix from the file name.

---

## Generating JUnit tests for your Java application with the Eclipse IDE
{: #wca-generate-junit-test}

You can automatically generate JUnit tests for your Java application and then display them in the Eclipse IDE.

### Before you begin JUnit tests
{: #wca-before-junit}

Set up your environment.

### Automatically generate JUnit tests in your Eclipse IDE for the entire application
{: #wca-auto -generate-application}

Right click the folder for your Java application in the Eclipse Project Explorer view and select **{{site.data.keyword.wca_short}}**, then select **Generate Tests**.

- Clickable links to the generated JUnit test files are displayed on the Unit test View panel of your IDE.
- The JUnit test files are in the `src/test/java` subfolder of the application. This subfolder is created when test generation initially runs.
- Tip: Generating all tests for an entire application can be a long running process. Consider generating testcases on a class by class basis if running the testcases all at once is an issue.

### Automatically generate JUnit tests in your Eclipse IDE for a specific class in the application
{: #wca-auto -generate-class}

Right click on the class within your Java application in the Eclipse Project Explorer view and select **{{site.data.keyword.wca_short}}**, then select **Generate Tests**.

- A clickable link to the generated JUnit test file is displayed on the Unit test View panel of your IDE.
- The JUnit test files are in the `src/test/java` subfolder of the application. This subfolder is created when test generation initially runs.

### Automatically generate a JUnit test for specific method in a specific class within your application
{: #wca-auto -generate-method}

Open a class in the Java Project Explorer view and right click on the method you want to generate a JUnit test for and select **{{site.data.keyword.wca_short}}**, then select **Generate Tests**.

- A clickable link to the generated JUnit test file containing your generate test is displayed on the Unit test View panel of your IDE.
- The JUnit test files are in the `src/test/java` subfolder of the application. This subfolder is created when test generation initially runs.

Review a JUnit test file that displays in the Unit test files panel by clicking the file.

- The file opens in the editor.

If you want to generate JUnit tests again for the same application or application class, but don't want the existing JUnit test files overwritten, change the name of the JUnit test files.
