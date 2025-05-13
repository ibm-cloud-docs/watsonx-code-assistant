---

copyright:
   years: 2024, 2025
lastupdated: "2025-05-13"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Translating code from one language to another
{: #wca-translate-code}

[{{site.data.keyword.wca_short}}]{: tag-blue}

Use the `/translate` command in the chat window to translate code from one language to the other.

## Chat syntax for translating code
{: #wca-translate-code-syntax}

The chat syntax is:
`/translate [from <source_language>] to <target_language> (<code reference> | <code snippet>) [additional instructions]`

- `[from <source_language>]` is optional and is automatically detected if not specified in the command. It is recommended to specify the source language if the quality of the translation response is not good enough.

- `<target_language>` is required. Provide complete language names without spaces, such as `TypeScript` instead of Type Script or `JavaScript` instead of Java Script.

- `(<code reference> | <code snippet>)`: Along with a target language, you can include either a code reference or a code snippet. Use one reference or snippet at a time.

   - `<code reference>`: Refer to a file, method, or class name from active workspace by using an `@` symbol. For example:

      ```text
      /translate to java @get_metric_type
      ```

      When you reference a method, {{site.data.keyword.wca_short}} supports certain code languages. Referencing a full file works for all languages. For more information, see [Language support when you work with methods](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-wca-reference-methods-language).

      {{site.data.content.reference-file-size-limit}}

   - `<code snippet>`: Use a code snippet from your editor or paste a code snippet.
      
      To use code snippet from your editor:
      1. Highlight the code in the editor.
      1. Right click to show the pop-up menu.
      1. Choose **{{site.data.keyword.wca_short}}**.
      1. Choose **Add selected code to chat**. 

      To paste a code snippet, find the code you want and insert it into the chat.

- `[additional instructions]` are optional. 

   For example: `/translate to java @get_user_list Copy the comments from this function to the translated code`
