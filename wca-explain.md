
---

copyright:
   years: 2024
lastupdated: "2024-11-20"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Explaining code
{: #wca-explain}



[{{site.data.keyword.wca_short}}]{: tag-blue}

Use generative AI to analyze and summarize your code to understand what the code does.
{: shortdesc}

## Multilanguage support 
{: #wca-explain-languages} 

Support is available for the following languages:

- C 
- C++
- Go
- Java 
- JavaScript
- Python
- TypeScript

## Using a chat command to explain code
{: #wca-explain-command}

You can use the `/explain` command in chat to explain code for a referenced class, file, function, or method in the active workspace.

Use this syntax:

`/explain <code reference> [additional instructions]`

For `<code reference>`, type the `@` symbol to see a list of classes, files, functions, and methods from your workspace. Use one class, file, function, or method reference at a time.

The `[additional instructions]` are optional. Add instructions if you want specific details.

Example prompts:
- `/explain @file.java`
- `/explain @method1`

## Using the CodeLens in the editor to explain code
{: #wca-explain-option}

In the IDE editor, the CodeLens shows a line of generative AI options that precedes code blocks and snippets.  

Click the **Explain** option that immediately precedes a code block to generate an explanation. For example:

```code
   Explain | Document | Unit Test
	protected void doPost(HttpServletRequest request, HttpServletResponse response)
			throws ServletException, IOException {

		doGet(request, response);
	}
```

## Using the Explorer context menu to explain code
{: #wca-explain-context-menu}

To generate an explanation from a context menu:

1. In the Explorer view, expand your application to the code that you want to generate an explanation for.

1. Right-click the code, click **{{site.data.keyword.wca_short}}**, then click **Explain**.

1. The {{site.data.keyword.wca_short}} chat displays the `/explain` command for the code that you selected. The following syntax is used in the command:

   `/explain <code syntax>`

1. {{site.data.keyword.wca_short_cap}} processes the request and in the chat displays the explanation for the code that you selected. 
