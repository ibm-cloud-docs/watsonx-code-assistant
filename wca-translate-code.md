
---

copyright:
   years: 2024
lastupdated: "2024-11-14"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Translating code from one language to another
{: #wca-translate-code}



[{{site.data.keyword.wca_short}}]{: tag-blue}

Use `/translate` command in the chat window to translate code from one language to the other.

## Chat syntax for translating code
{: #wca-translate-code-syntax}

The chat syntax is:
`/translate [from <source_language>] to <target_language> (<code reference> | <code snippet>) [additional instructions]`

- `[from <source_language>]` is optional and is automatically detected if not specified in the command. It is recommended to specify the source language if the quality of the translation response is not good enough.

- `<target_language>` is required. Provide complete language names without spaces, such as `TypeScript` instead of Type Script or `JavaScript` instead of Java Script.

- `(<code reference> | <code snippet>)`. Along with a target language, you can include either a code reference or a code snippet. Use one reference or snippet at a time.

   - `<code reference>`. Refer to a file, method, or class name from active workspace by using an `@` symbol. For example:

      ```text
      /translate to java @get_metric_type
      ```

   - `<code snippet>`. Enclose code snippets in code backticks. For example: 

      ````text
      /translate to java

      ```
      print('Hello World')
      ```
      ````

- `[additional instructions]` is optional. 

   For example: `/translate to java @get_user_list Copy the comments from this function to the translated code`