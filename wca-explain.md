---

copyright:
   years: 2024, 2025
lastupdated: "2025-03-19"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Explaining code
{: #wca-explain}

[{{site.data.keyword.wca_short}}]{: tag-blue}

Use generative AI to analyze and summarize your code to understand what the code does.
{: shortdesc}

The following table lists the type of explanation for each plan.

| Plan | Explanation | Description |
| --- | --- | --- |
| [Trial plan]{: tag-magenta} [Essentials plan]{: tag-green} | Basic | Uses generative AI to provide a basic explanation. No extra code analysis is required. |
| [Standard plan]{: tag-purple} | Enhanced | Requires a built application, and uses a code analysis and generative AI to provide an enhanced code explanation for Java methods/classes and enterprise Java applications. |
{: caption="Explanation types" caption-side="bottom"}

{{site.data.content.eclipse-multimodule}}

## Language support 
{: #wca-explain-languages} 

Code explanation is available for the following languages:

{{site.data.content.language-support}}

## Using a chat command to explain code
{: #wca-explain-command}

You can use the `/explain` command in chat to explain code for a referenced class, file, function, or method in the active workspace.

Use this syntax:

`/explain <code reference> [additional instructions]`

- For `<code reference>`, type the `@` symbol to see a list of classes, files, functions, and methods from your workspace. Use one class, file, function, or method reference at a time.

- The `[additional instructions]` are optional. Add instructions if you want specific details.

## Using the CodeLens in the editor to explain code
{: #wca-explain-option}

In the IDE editor, the CodeLens shows a line of generative AI options that precedes code blocks and snippets.  

{{site.data.content.codelens-delay}}

1. Click the **Explain** option that immediately precedes a code block to generate an explanation.

   In the following code example, the `Explain | Document | Unit Test` options immediately precede the `protected void` keywords.

   ![CodeLens example](images/codelens.png){: caption="CodeLens example"}

1. The {{site.data.keyword.wca_short}} chat window opens, displays the `/explain @<*item name*>` command, runs the command, and displays the explanation. 

If you want to disable the CodeLens options, you can deselect the `Enable CodeLens` setting for the Visual Studio Code extension.
{: note}

## Using the Explorer context menu to explain code
{: #wca-explain-context-menu}

To generate an explanation from a context menu:

1. In the Explorer view, expand your application to the code that you want to generate an explanation for.

1. Right-click the code, click **{{site.data.keyword.wca_short}}**, then click **Explain**.

1. The {{site.data.keyword.wca_short}} chat displays the `/explain` command for the code that you selected. The following syntax is used in the command:

   `/explain <code syntax>`

1. {{site.data.keyword.wca_short_cap}} processes the request and in the chat displays the explanation for the code that you selected. 



## Explaining Java applications
{: #wca-explain-apps}

[Standard plan]{: tag-purple} Application explanation is only available with the {{site.data.keyword.wcaej_short}} extension. 

Application explanation is only supported for Java applications that contain one or more classes that extend `javax.servlet.http.HttpServlet`. These classes need to implement any one of the following methods: `doGet`, `doPost`, or `doPut`.
{: note}

To request and view an explanation for an application:

1. In your IDE, right-click on any item in the hierarchy in the directory of the application that you want to explain, and then click **Explain Application**.

   In the Eclipse IDE, if you have a multimodule application with a peer multimodule root, the application explanation applies only to the selected module.
   {: note}

1. {{site.data.keyword.wca_short_cap}} scans the application to generate an overview and a list of main services with a description of functions for each method.
1. Click **Save** to retain a copy, or the explanation is discarded.
1. Click **Open explanation** and review, and then you can click **Save application explanation** to store in a local file.
