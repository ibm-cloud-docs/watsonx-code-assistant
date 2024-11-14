
---

copyright:
   years: 2024
lastupdated: "2024-11-14"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Generating unit tests
{: #wca-generate-test}



[{{site.data.keyword.wca_short}}]{: tag-blue}

Generate unit tests for various programming languages.
{: shortdesc}



## Multilanguage support 
{: #wca-generate-test-languages} 

Support is available for the following languages:

- C 
- C++
- Go
- Java 
- JavaScript
- Python
- Typescript

## Using a chat command to generate a unit test
{: #wca-gen-chat}

You can use the `/unit-test` command in chat to generate a test for a referenced class, file, function, or method in the active workspace.

Use this syntax:

`/unit-test <code reference> [additional instructions]`

For `<code reference>`, type the `@` symbol to see a list of classes, files, functions, and methods from your workspace. Use one class, file, function, or method reference at a time.

The `[additional instructions]` are optional. Add instructions if you want specific details.

Example prompts:
- File: `/unit-test @OrdersAlertFilter.java`
- Class: `/unit-test @OrdersAlertFilter`
- Method: `/unit-test @DoFilter()`  

Next, {{site.data.keyword.wca_short}} processes the request and in the chat displays the generated unit test for the code that you selected. 

  

## Using the CodeLens in the editor to generate unit tests
{: #wca-gen-option}

In the IDE editor, the CodeLens shows a line of generative AI options that precedes code blocks and snippets.  

1. Click the **Unit Test** option that immediately precedes a code block to generate an explanation. For example:

   ```code
      Explain | Document | Unit Test
	   protected void doPost(HttpServletRequest request, HttpServletResponse response)
		   	throws ServletException, IOException {

		   doGet(request, response);
	   }
   ```

1. The {{site.data.keyword.wca_short}} chat window opens, displays the `/unit-test @<*item name*>` command, runs the command, and displays the unit test. 



## Generating unit tests from the context menu
{: #wca-gen-context}

To generate a unit test from a context menu:

1. In the Explorer view, expand your application to the code that you want to generate a unit test for.

1. Right-click the code, click **{{site.data.keyword.wca_short}}**, then click **Unit Test**.

1. The {{site.data.keyword.wca_short}} chat displays the `/unit-test` command for the code that you selected for unit testing. The following syntax is used in the command:

   `/unit-test @<*item syntax*>`

   The following syntax examples are for a file, a class, and a method.

   * File: `/unit-test @OrdersAlertFilter.java`
   * Class: `/unit-test @OrdersAlertFilter`
   * Method: `/unit-test @DoFilter()`


1. {{site.data.keyword.wca_short_cap}} processes the request and in the chat displays the generated unit test for the code that you selected. 



 
