
---

copyright:
   years: 2024
lastupdated: "2024-11-18"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Documenting code
{: #wca-generate-doc}



[{{site.data.keyword.wca_short}}]{: tag-blue}

Generate comment lines that document what your code does.
{: shortdesc}

Documentation uses these standards, depending on the code language:

| Code | Documentation standard |
| --- | --- |
| C | doxygen |
| C++ | doxygen |
| Go | GoDoc |
| Java | Javadoc |
| JavaScript | JSDoc |
| TypeScript | JSDoc |
| All others | Markdown |
{: caption="Documentation standards" caption-side="bottom"}

## Using a chat command to generate documentation
{: #wca-generate-doc-chat-command}

You can use the `/document` command in chat to generate documentation for a referenced file or a method or a class in the active workspace.

Use this syntax:

`/document <code reference> [additional instructions]`

For `<code reference>`, type the `@` symbol to see a list of files, classes, and methods from your workspace. Use one file, method, class reference at a time.

The `[additional instructions]` are optional. Add instructions if you want specific details.

Examples prompts:
- `/document @file.java`
- `/document @method1`

## Using the CodeLens in the editor to generate documentation
{: #wca-generate-doc-document-option}

In the IDE editor, the CodeLens shows a line of generative AI options that precedes code blocks and snippets.  

Click the **Document** option that immediately precedes a code block or snippet to generate its documentation. For example:

```code
   Explain | Document | Unit Test
	protected void doPost(HttpServletRequest request, HttpServletResponse response)
			throws ServletException, IOException {

		doGet(request, response);
	}
```
