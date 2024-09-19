
---

copyright:
   years: 2024
lastupdated: "2024-09-19"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Get code suggestions
{: #wca-chat}



Use chat, code, or comments to get code suggestions by using generative AI.
{: shortdesc}

- **Use chat to ask for code suggestions.** Enter a prompt that explains the code you need, and the code assistant generates something you can choose to use.
- **Complete code.** Start typing a line of code. Wait for one second, and the code assistant provides a suggestion you can use or reject.
- **Enter code or comments.** Start writing code or enter a comment, then press a keyboard shortcut to get a code suggestion.









- In Visual Studio Code, press Option+. (Mac) or Alt+. (Windows)
- In Eclipse, press Command+' (Mac) or Ctrl+' (Windows)

## Changing keyboard shortcuts
{: #wca-chat-keyboard-shortcuts}

If necessary, you can change the keyboard shortcuts that you use to get a code suggestion.

To change keyboard shortcuts in Visual Studio Code:

1. Click the Code menu, select Settings, then select Keyboard Shortcuts.
1. Search for `wca.inlineSuggest.trigger`.
1. Click the Change Keybinding edit pencil icon and assign a different key combination.

To change keyboard shortcuts in Eclipse:

1. Click the Eclipse menu then select Settings.
1. Type Keys to filter the settings, then click Keys.
1. Type WCA to filter the list.
1. Select the keyboard shortcut you want to change.
1. In the Binding field, enter a new key combination.



## Using chat to generate code
{: #wca-chat-chat}


### Use natural language

Enter a free-text question or instruction and click the **Enter** icon. {{site.data.keyword.wca_short_cap}} sends your input to the code model, and shows the response in the chat.

Each chat message is part of a chat conversation. We highly recommend keeping conversations focused around a specific subject or task. When you switch your context, for example, to another programming language, another project in your workspace, or a different programming task, create a new chat conversation. You get more relevant results for your questions.

| Use case | Example message |
| --- | --- |
| Generate a function based on an existing function | _Create a method `send_translate_message` that is similar to @send_code_explanation_message_ |
| Generate a unit test that follows existing unit tests | _Create a unit test for @getName that is similar to the unit tests in @testLoadTablesChildConnectionReceiverJob.h_ |
| Enhance existing functions | _Add error handling and log statements to @format_documents_ |
| Enhance existing functions | _Update @setEmail with error handling for null strings_ |
| Explain code | _What does @main.py do_ |
| Explain code | _Explain the logic of @send_invoice_ |
| Generate documentation for functions and classes | _Add javadoc to @Customer_ |
{: caption="Chat message examples" caption-side="bottom"}

### Writing effective chat messages

- Write your chat messages in English.
- Start with a simple and clear instruction.
- Use subsequent chat messages to refine the code output of the model.
- Be as specific and detailed as you can for each step. You can gradually enhance the created code through subsequent chat messages.
- Use file and method references in your message to provide relevant context. For example, if you want the model to create a method that is similar to another method, add _"similar to `@<method>`"_ to your message.
- If you find the answers become less relevant, or if you start a new task, create a new chat conversation, and work from there. It is better to have many short chat conversations, each with a specific context, rather than one large conversation that might confuse the model with different and unrelated chat messages.

{{site.data.keyword.wca_short_cap}} and the Granite code models are created to answer questions that are related to code, general programming, and software engineering. While the IDE doesn’t restrict your questions or prompts, the Granite Code models were not designed for language tasks and are not appropriate for such use. Any such use is at your own risk, and you may not rely on resulting output. Please validate all output independently and consider deploying a Hate Abuse Profanity (HAP) filter.

To create a new chat conversation:

   1. Open the menu at the top of the chat.
   2. Select **New Chat**.

To switch between chat conversations:

   1. Open the menu at the top of the chat.
   2. Select **Chat Sessions**.
   3. Select the conversation.

To delete a chat conversation:

   1. Open the menu at the top of the chat.
   2. Select **Chat Sessions**.
   3. Select the menu on the right of the conversation.
   4. Click **Delete**.

To rename a chat conversation:

   1. Open the menu at the top of the chat.
   2. Select **Chat Sessions**.
   3. Select the menu on the right of the conversation.
   4. Click **Rename**.

### Reference code

To ask questions or refine a specific file, class, function, or method in your workspace, you can use a _code reference_. These references provide important context for the LLM, and can help to increase the accuracy of the answer.

1. As part of your chat message, type the `@` symbol.
2. A screen pops up, showing all files, classes, and methods from your workspace.
3. Start typing the characters of the file, class, or method name you want to reference. The list filters automatically.
4. Select the reference.

{{site.data.keyword.wca_short_cap}} sends the contents of the reference automatically to the model as part of your message.

When you open a workspace folder, {{site.data.keyword.wca_short}} creates an index of these items in memory so that you can reference these files and functions in the chat. The IDE also indexes files that you add or change during your Visual Studio Code session. The index contains up to 1000 of the most recent files in 7 programming languages: C, C++, Java, Go, JavaScript, Typescript, and Python.






## Using in-editor code completion and comment-to-code

### Single-line completion

1. Start typing a line of code.
2. {{site.data.keyword.wca_short_cap}} adds a code suggestion to complete the line that you typed.
3. Press **Tab** to accept the suggestion.

<img src="https://github.com/ibm-granite/granite-code-ide/raw/HEAD/images/Single-line.gif" height=200 alt="Single-line completion in IBM Granite.Code">

### Multi-line completion

1. Start typing a line of code.
2. Press `Option` + `.` (Mac) or `Alt`+ `.` (Windows)
3. {{site.data.keyword.wca_short_cap}} adds a code suggestion to complete the line that you typed, and adds code lines.
4. Press **Tab** to accept the suggestion.

<img src="https://github.com/ibm-granite/granite-code-ide/raw/HEAD/images/Multi-line.gif" height=350 alt="Multi-line completion in IBM Granite.Code">

### Comment-to-code

1. Type a comment.
2. Press `Option` + `.` (Mac) or `Alt`+ `.` (Windows)
3. {{site.data.keyword.wca_short_cap}} adds a code suggestion based on your comment.
4. Press **Tab** to accept the suggestion.

<img src="https://github.com/ibm-granite/granite-code-ide/raw/HEAD/images/comment-to-code.gif" height=200 alt="Comment to code generation in IBM Granite.Code">

### Tips for generating code

#### Chat for larger code blocks. Use in-editor code generation for refinement and boilerplate code

Use chat to:

- Generate the overall outline of a class
- Specify a method in detail
- Refine the suggested code by using more instructions (for example, rename or replace)

Use in-editor code generation to:

- Complete the line of code that you started to type
- Automatically create boilerplate code like getters and setters
- Create methods and code that can be described with a single comment line

#### Comment-to-code: use descriptive comments, not instructions

When you use comment-to-code in the editor, write a comment that describes the intended behavior - just like what you do when you write comments for code you wrote. For example, use `//return even numbers from an arraylist` or `//method that returns even numbers from an arraylist`. Don't write your comment as an instruction, such as `//write a method that returns even numbers from an arraylist`. Granite models are trained to complete code on data that contains many "typical", descriptive comments, so these kinds of comments yield better results.

#### Context used for in-editor code generation

The key ingredient for code generation is the context, that is, the surrounding code that you pass to the model. For in-editor code generation, {{site.data.keyword.wca_short}} uses the following context:

1. The 20 lines of code before the line where the generation is triggered.
2. The 20 lines of code after the line where the generation is triggered.
3. Up to 200 lines from the beginning of the current file where generation is triggered.
4. Up to 5 code snippets that are similar to the code that surrounds the line where generation was triggered. These snippets are taken from the last 10 files that you opened that are in the same programming language as the current file.

To improve the results of in-editor code generation:

- Open files in your workspace that have code you want {{site.data.keyword.wca_short}} to know about. {{site.data.keyword.wca_short_cap}} tries to find code in these files that is similar to the place where you trigger completion, for example, methods that use similar classes and variables, and sends this code to the model as context.
- Don’t use in-editor code generation when you start from scratch. Code generation in almost empty files might not have enough context. You can help {{site.data.keyword.wca_short}} by starting with a class definition or adding import statements. You can also use the {{site.data.keyword.wca_short}} chat to create the initial outline, copy the result into a file in your workspace, and continue with in-editor code generation.

