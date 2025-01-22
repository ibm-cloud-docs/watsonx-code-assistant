---

copyright:
   years: 2024, 2025
lastupdated: "2025-01-22"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Getting code suggestions
{: #wca-generate-code}

[{{site.data.keyword.wca_short}}]{: tag-blue}

Generate code suggestions by using chat conversations or completing code in the editor.
{: shortdesc}

## Using chat conversations
{: #wca-generate-code-chat}

Enter a prompt that explains the code you need, and {{site.data.keyword.wca_short}} generates something you can choose to use.

1. To start a new chat conversation, click the **New chat** icon ![New chat](images/new-chat.svg).
1. Ask a question or give an instruction.
1. Click the **Send** icon ![Send](images/send.svg). {{site.data.keyword.wca_short_cap}} sends your input to the code model, and shows the response in the chat.

### Using natural language
{: #wca-generate-code-natural-language}

Each chat message is part of a chat conversation. Keep conversations focused around a specific subject or task. When you switch your context to another programming language, another project in your workspace, or a different programming task, create a new chat conversation. You get more relevant results for your questions.

Examples:
- `Create a Python class Customer. Include attributes for firstName, lastName and age.`
- `Create a JavaScript function that fetches data from a REST API endpoint, dynamically populates an HTML table with the results, and updates the UI asynchronously`

#### Using the prompt library
{: #wca-generate-code-prompt-library}

{{site.data.keyword.wca_short_cap}} includes a prompt library that contains a set of common, natural-language coding requests. You can use them as-is in your chat, or modify them for your use case.

To access the prompt library:
1. Click the **Open menu** icon ![Open menu](images/menu.svg).
1. Click **Prompt library** to open it.
1. Click the **Copy to clipboard** icon ![Copy to clipboard](images/copy.svg).
1. Click **Prompt library** again to close it.
1. Paste the prompt into the chat.

### Writing effective chat messages
{: #wca-generate-code-effective-messages}

For the best results in your conversation:

- Write your chat messages in English.
- Start with a simple and clear instruction.
- Use subsequent chat messages to refine the code output of the model.
- Be as specific and detailed as you can for each step. You can gradually enhance the created code through subsequent chat messages.
- Use file and method references in your message to provide relevant context. For example, if you want the model to create a method that is similar to another method, add `similar to @<method>` to your message.
- If you find the answers become less relevant, or if you start a new task, create a new chat conversation, and work from there. It is better to have many short chat conversations, each with a specific context, rather than one large conversation that might confuse the model with different and unrelated chat messages.

## Referencing code in your workspace
{: #wca-generate-code-reference-code}

To ask questions or refine a specific file, class, function, or method in your workspace, you can use a *code reference*. These references provide important context and can help to increase the accuracy of the answer.

1. Type the `@` symbol as part of your chat message to see a list of files, classes, and methods from your workspace.
1. Filter the list by typing characters of the file, class, or method name you want to reference.
1. Click to select the reference. {{site.data.keyword.wca_short_cap}} sends the contents of the reference as part of your message.

When you open a workspace folder, {{site.data.keyword.wca_short}} creates an index of these items in memory so  you can reference these files and functions in the chat. Your editor also indexes files that you add or change during your session. The index contains up to 1,000 of the most recent files in these programming languages:
{{site.data.content.language-support}}

Use cases with examples that reference code:

| Use case | Example message |
| --- | --- |
| Generate a function based on an existing function | Create a method `send_translate_message` that is similar to @send_code_explanation_message |
| Generate a unit test that follows existing unit tests | Create a unit test for @getName that is similar to the unit tests in @testLoadTablesChildConnectionReceiverJob.h |
| Enhance existing functions | Add error handling and log statements to @format_documents |
| Enhance existing functions | Update @setEmail with error handling for null strings |
| Explain code | What does @main.py do |
| Explain code | Explain the logic of @send_invoice |
| Generate documentation for functions and classes | Add Javadoc to @Customer |
{: caption="Chat messages that reference code" caption-side="bottom"}

## Using commands
{: #wca-generate-code-commands}

Chat commands that you can use to perform certain tasks:

| Command | Description | For more information |
| --- | --- | --- |
| `/document` | Generate documentation for a referenced file or a method or a class in the active workspace | [Generating documentation](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-wca-generate-doc#wca-generate-doc-chat-command) |
| `/docs` | Ask questions that reference IBM and Red Hat product documentation | [Getting answers from IBM documentation](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-wca-ibm-docs) |
| `/explain` | Use generative AI to analyze and summarize your code to understand what the code does | [Explaining code](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-wca-explain#wca-explain-command) |
| `/help` | Get quick assistance about tasks | Type `/help` in the chat |
| `/unit-test` | Generate unit tests for various programming languages | [Generating unit tests](https://test.cloud.ibm.com/docs/watsonx-code-assistant?topic=watsonx-code-assistant-wca-generate-test#wca-gen-chat) |
| `/translate` | Translate code from one language to the other | [Translating code](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-wca-translate-code) |
{: caption="Chat commands" caption-side="bottom"}

## Managing chat conversations
{: #wca-generate-code-manage-chat}

You can use the **Chat sessions** menu to manage your existing chat conversations.

To open the menu:
1. Click the **Open menu** icon ![Open menu](images/menu.svg).
1. Click **Chat sessions**.



## Completing code in the editor
{: #wca-generate-code-completion}

Get code suggestions by entering code or comments in your editor.

### Using the editor in Eclipse
{: #wca-generate-code-editor-eclipse}

For C, C++, Go, JavaScript, Python, and TypeScript:

1. Right-click on the file.
1. Click **Open with**, then click **Text Editor**. 

For Java, inline code generation with the Java Editor in the Eclipse IDE is supported in {{site.data.keyword.wca_short}} but first needs to be set up. 

1. Go to Content Assist in the Eclipse settings.

   | OS | Path |
   | --- | --- |
   | Mac |  Eclipse > Settings > Java > Editor > Content Assist|
   | Windows |  Window > Preference > Java > Editor > Content Assist |
   {: caption="Navigation to Content Assist" caption-side="bottom"}

1. In the **Insertion** section, disable **Insert single proposals automatically** by unchecking this option.

1. In the **Auto Activation** section, add `._abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ` to **Auto activation triggers for Java**, and confirm that **Enable auto activation** is checked.

1. Click **Apply and Close**.

### Single-line completion
{: #wca-generate-code-single-line-completion}

As you write a line of code in your editor, {{site.data.keyword.wca_short}} can suggest code to complete it.

1. Start typing a line of code, then pause.
1. {{site.data.keyword.wca_short_cap}} adds a code suggestion to complete the line that you typed.
1. In Visual Studio Code, press **Tab** to accept the suggestion. In Eclipse, press **Return** or **Enter** to accept the suggestion. Or press **Esc** to reject.

### Multiline completion
{: #wca-generate-code-multiple-line-completion}

You can get a multiline code suggestion based on a line of code or a comment that you enter.

1. Start typing a line of code, or enter a comment that describes the code you want.
1. Use a keyboard shortcut.
   
   | Mac | Windows |
   | --- | --- |
   | Option+. | Alt+. |
   {: caption="Default keyboard shortcuts" caption-side="bottom"}

1. {{site.data.keyword.wca_short_cap}} adds a multiline code suggestion.
1. In Visual Studio Code, press **Tab** to accept the suggestion. In Eclipse, press **Return** or **Enter** to accept the suggestion. Or press **Esc** to reject.

#### Changing keyboard shortcuts
{: #wca-generate-code-keyboard-shortcuts}

You can change the keyboard shortcuts that you use to get a code suggestion, if the default combinations are already assigned to other tasks.

To change keyboard shortcuts in Visual Studio Code:

1. Click the **Code** menu.
1. Select **Settings**.
1. Select **Keyboard Shortcuts**.
1. Search for `wca.inlineSuggest.trigger`.
1. Click the **Change Keybinding** edit pencil icon and assign a different key combination.

To change keyboard shortcuts in Eclipse:

1. Click the **Eclipse** menu. 
1. Select **Settings**.
1. Type `Keys` to filter the settings, then click **Keys**.
1. Type `WCA` to filter the list.
1. Select the keyboard shortcut that you want to change.
1. In the **Binding** field, enter a new key combination.

### Disabling code completion
{: #wca-generate-code-disable-completion}

If necessary, you can disable the completion of code in the editor window.

To disable code completion in Visual Studio Code:
1. In the lower right corner of the editor, click the **Disable watsonx Code Assistant Completions** icon ![images](images/wca-portfolio.svg).
1. You can re-enable completions by clicking the **Enable watsonx Code Assistant Completions** icon again.

To disable code completion in the Eclipse IDE:
1. In the editor toolbar, click the **Disable watsonx Code Assistant Completions** icon.
1. You can re-enable completions by clicking the **Enable watsonx Code Assistant Completions** icon again.

## Best practices for generating code suggestions
{: #wca-generate-code-best-practices}

Use these tips to get the best results.

### Use chat for larger code blocks. Use in-editor code generation for refinement and boilerplate code.
{: #wca-generate-code-best-practice-1}

Use chat to:
- Generate an outline of a class
- Specify a method in detail
- Refine the suggested code with more instructions (for example, rename or replace)

Use in-editor code generation to:
- Complete the line of code that you started to type
- Automatically create boilerplate code, such as getters and setters
- Create methods and code that can be described with a single comment line

### Comment-to-code: use descriptive comments, not instructions
{: #wca-generate-code-best-practice-2}

When you use comment-to-code in the editor, write a comment that describes the intended behavior, similar to how you write comments for code you wrote. For example, use `//return even numbers from an arraylist` or `//method that returns even numbers from an arraylist`. 

Don't write your comment as an instruction, such as `//write a method that returns even numbers from an arraylist`. {{site.data.keyword.wca_short_cap}} uses models that are trained to complete code on data that contains many typical, descriptive comments, so these types of comments yield better results.

### Context used for in-editor code generation
{: #wca-generate-code-best-practice-3}

The key ingredient for code generation is context, that is, the surrounding code that you pass to the model. For in-editor code generation, {{site.data.keyword.wca_short}} uses:

1. The 20 lines of code before the line where the generation is triggered.
2. The 20 lines of code after the line where the generation is triggered.
3. Up to 200 lines from the beginning of the current file where generation is triggered.
4. Up to 5 code snippets that are similar to the code that surrounds the line where generation was triggered. These snippets are taken from the last 10 files that you opened in the same programming language as the current file.

To improve the results of in-editor code generation:

- Open files in your workspace that have code you want {{site.data.keyword.wca_short}} to know about. {{site.data.keyword.wca_short_cap}} tries to find code in these files that is similar to where you trigger completion, for example, methods that use similar classes and variables, and then sends this code to the model as context.
- Help {{site.data.keyword.wca_short}} by starting with a class definition or adding import statements, or use the {{site.data.keyword.wca_short}} chat to create the initial outline, copy the result into a file in your workspace, and then continue with in-editor code generation. Don’t use in-editor code generation when you start from zero or almost empty files, as these conditions do not provide enough context. 
