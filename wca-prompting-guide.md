---

copyright:
   years: 2025
lastupdated: "2025-05-19"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Prompting guide for {{site.data.keyword.wca_full_notm}}
{: #wca-prompting-guide}

Learn about prompting techniques that maximize your use of {{site.data.keyword.wca_short}}.
{: shortdesc}

{{site.data.keyword.wca_full_notm}}:

- Captures and transmits prompt and context information for inference and captures feedback from the user to improve model and service quality
- Combines and processes natural language and code to get code suggestions from large language models (LLMs)
- Finds training examples that are similar to the code suggestions
- Collects and processes feedback data to improve model quality and user experience

One of the key advantages of {{site.data.keyword.wca_short}} is its ability to use context and industry best practices to generate intelligent suggestions. As you use {{site.data.keyword.wca_short}}, it incorporates context from the overall source file and the specific paragraph to provide more accurate recommendations. It analyzes the code that you wrote and suggests improvements or additions based on established best practices.

## Prompt engineering primer
{: #wca-prompting-guide-primer}

*Parameterization*, in the context of prompt engineering, covers the adjusted settings that go into the behavior of your model for your use case. Here are some key prompt engineering parameters and how they work:

- **Temperature**: Controls the randomness of responses. Lowering it to approximately 0.1 yields consistent, predictable outputs, while raising it (approximately 0.9) produces creative responses with varying degrees of variability.

- **Stop sequences**: Tells the model when to end its response and acknowledge when a question has been fully answered.

- **Top-k**: Sets a hard limit on how many word choices the model considers at each step of its thought process. For example, if the top-k is set to 50, the model picks from only the 50 most likely next words, ignoring less probable ones.

- **Top-p sampling**: Also known as nucleus sampling, it works by considering words based on their cumulative probability. With a lower value, the model sticks to high-confidence words, giving you more focused and reliable answers.

- **Frequency versus presence penalties**: Prevents repetition. Frequency penalizes reusing words, while presence encourages exploring new topics.

- **Logit bias**: You can select specific words to be more or less likely to show up in ones responses. This is helpful when you want to steer the model toward or away from certain terminologies.

For the purposes of code generation, {{site.data.keyword.wca_short}} has optimized backend parameters like *temperature*, where the value threshold is set low enough to provide consistent and predictable outputs while allowing creative responses when appropriate. Additionally, {{site.data.keyword.wca_short}} couples this with *stop sequences* that are clear and produce structured functional code that adheres to proper syntax rules.

Because {{site.data.keyword.wca_short}} doesn't expose these parameters, you are effectively practicing *hard prompting* and *soft prompting* by using inputs in *prompt chat* and *inline in the code directly*.

### Hard prompting
{: #wca-prompting-guide-hard-prompting}

Code generation is inherently an exercise in hard prompting, requiring you to provide specific instructions as prompts to the AI domain expert to receive an accurate response. As a warmup, ask {{site.data.keyword.wca_short}} to do something generic. For example:

```text
Write Python code to sort an array using the bubble sort algorithm.
```
{: codeblock}

{{site.data.keyword.wca_short_cap}} might respond with:

```text
Here's a Python implementation of the bubble sort algorithm:

# Assisted by watsonx Code Assistant

def bubble_sort(arr):
    n = len(arr)

    for i in range(n):
        for j in range(0, n - i - 1):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]

# Example usage:

arr = [64, 34, 25, 12, 22, 11, 90]
bubble_sort(arr)
print("Sorted array is:", arr)

This code defines a function bubble_sort that takes an array as input and sorts it using the bubble sort algorithm. The outer loop iterates through the array, and the inner loop compares adjacent elements and swaps them if they are in the wrong order. The process repeats until the array is sorted. The example usage demonstrates how to use the bubble_sort function to sort an array.
```

The nature of the question was so generic yet specialized in its domain that the LLM provided an example usage without being prompted for it.
{: note}

The challenge with hard prompting is that it's possible to make the prompt too hard. If you use hardcoded information in your prompt, there's an excellent chance that the response is anonymized or otherwise different from what you prompted. For example, if you prompt with:

```bash
You are a Cisco NXOS engineer. Write a script that sets the secondary interface IPv4 address for Ethernet1/2 to 194.99.2.254/24.
```

You might get a response that uses a different number in the fourth octet of the IPv4 address, or a different IPv4 address entirely.

This is where the other definition of parameterization applies, which is the use of parameters within the syntax of the language you are using. Consider this improvement:

```text
You are a Cisco NXOS engineer. Write a script that sets the secondary interface IPv4 address for a parameterized layer 1 interface name to a parameterized IPv4 address formatted as CIDR.
```

You might even give an example:

```text
You are a Cisco NXOS engineer. Write a script that sets the secondary interface IPv4 address for a parameterized layer 1 interface name like "Ethernet1/2" to a parameterized IPv4 address formatted as CIDR like "192.168.1.200/24."
```

Experiment with different approaches, but the use of hardcoded data is an anti-pattern.

### Soft prompting
{: #wca-prompting-guide-soft-prompting}

Conversely, when code generation occurs without explicit instructions and the AI is provided with subtle guidance, the AI generates prompts as prefix vector embeddings that are incomprehensible to humans. This phenomenon is commonly referred to as *soft prompting*.

{{site.data.keyword.wca_short_cap}} benefits from this technique in the form of single and multiline code completion, which makes the solution so powerful. For example, prompt {{site.data.keyword.wca_short}} to do something traditional in the context of object-oriented programming:

```text
Create a python class Customer. Include attributes for firstName, lastName, and age.
```

{{site.data.keyword.wca_short_cap}} would respond with:

```text
Here's a Python class named Customer with attributes for firstName, lastName, and age:

 # Assisted by watsonx Code Assistant 
 

class Customer:

    def __init__(self, first_name, last_name, age):
        self.first_name = first_name
        self.last_name = last_name
        self.age = age

    def full_name(self):
        return f"{self.first_name} {self.last_name}"

    def is_adult(self):
        return self.age >= 18

This class has three attributes: first_name, last_name, and age. The __init__ method initializes these attributes when a new Customer object is created. The full_name method returns the customer's full name, and the is_adult method checks if the customer is an adult (18 years or older).
```

The example method is deliberately omitted in the response to articulate the following point.
{: note}

Now for the fun part. You've your hard prompting efforts from the prompt chat into your code file. Your results, which in effect act as a parameterization for soft prompting, take over when asked to provide an example usage of your code inline, for example:

![Soft prompting example](images/soft-prompt-example.png){: caption="Soft prompting example" caption-side="bottom"}

As expected, it instantiates customer object examples and provides what those example results would be.

### Summary
{: #wca-prompting-guide-prompting-summary}

With hard prompting, parameterization is driven by you. {{site.data.keyword.wca_short_cap}} facilitates this in the chat. Conversely, with soft prompting your entire contextualized code is one significant parameter that is driven by the IBM Granite model, which is used by {{site.data.keyword.wca_short}} and facilitated within the inline code directly.

## Simple ways to enhance your experience
{: #wca-prompting-guide-simple-ways}

Use these approaches to enhance your experience when you write prompts.

### Use personas or role names to provide context
{: #wca-prompting-guide-simple-ways-personas}

The LLM supporting {{site.data.keyword.wca_short}} is tuned to support 116 different programming languages. When you prompt for content, explanations, or opportunities for improvement, it's important to provide context that includes the role or persona that would otherwise be expected to produce the content without AI.

Start with a basic query for language recommendations. Suppose you work for an operational technology company that produces embedded systems, sensors, and other instruments. You want to implement the UNIX `cat` command, and ask the following question:

**Good:** `Between C, C++, and Ada, which language is best for implementing the UNIX "cat" command?`

This is a good start, and one improvement would be to start with a sentence that provides more context. Consider the following:

**Better:** `You are an embedded systems programmer. Between C, C++, and Ada, which language is best for implementing the UNIX "cat" command?`

This is better because the needed skill set is now much clearer. 

Finally, it would help to include any specific requirements. For example:

**Best:** `You are an embedded systems programmer building secure fielded instruments. Between C, C++, and Ada, which language is best for implementing the UNIX "cat" command?`

This is an improvement because the prompt includes the security requirement, preventing the need for a follow-up prompt such as `What if I need robust security capabilities?`

You can use these examples to build a strong persona line:

| Element | Example |
|---------|---------|
| **Role** | Backend developer, site‑reliability engineer |
| **Seniority** | Junior, senior, principal |
| **Domain** | Fintech, healthcare, edge devices |
| **Key constraints** | FIPS, low latency, 256 MB RAM cap |
| **Audience or voice** | Mentoring a junior, writing a blog post |
{: caption="Persona examples" caption-side="bottom"}

#### Terraform module examples
{: #wca-prompting-guide-simple-ways-terraform}

| Level | Prompt |
|-------|--------|
| Good | `Write Terraform to deploy an S3 bucket.` |
| Better | `You are a cloud engineer. Write Terraform to deploy an encrypted S3 bucket.` |
| Best | `You are a senior cloud engineer in a healthcare firm. Write Terraform that deploys an S3 bucket with SSE‑KMS, public access blocked, and versioning on.` |
{: caption="Terraform module examples" caption-side="bottom"}

#### Python ETL script examples
{: #wca-prompting-guide-simple-ways-python-etl}

| Level | Prompt |
|-------|--------|
| Good | `Write a Python script that loads a CSV into PostgreSQL.` |
| Better | `You are a data engineer. Write a Python script that loads a CSV into PostgreSQL using psycopg2.` |
| Best | `You are a data engineer at a pharma company. Write a Python script that loads a large CSV into PostgreSQL using COPY, tracks row count, and logs failures to CloudWatch.` |
{: caption="Python ETL script examples" caption-side="bottom"}

#### Security review examples
{: #wca-prompting-guide-simple-ways-security-review}

| Level | Prompt |
|-------|--------|
| Good | `Review this Node.js code for bugs.` |
| Better | `You are an application security auditor. Review this Node.js code for common OWASP issues.` |
| Best | `You are an application security auditor preparing a PCI report. Review this Node.js Express handler for OWASP Top 10 issues and suggest fixes inline.` |
{: caption="Security review examples" caption-side="bottom"}

#### Postgres tuning examples
{: #wca-prompting-guide-simple-ways-postgres-tuning}

| Level | Prompt |
|-------|--------|
| Good | `Suggest Postgres settings for high load.` |
| Better | `You are a database administrator. Suggest Postgres settings for steady 5 k writes per second.` |
| Best | `You are a senior DBA at an ad‑tech firm. Suggest Postgres 15 settings to sustain 5 k writes per second on an m6i.2xlarge, 64 GB RAM, 2 TB gp3.` |
{: caption="Postgres tuning examples" caption-side="bottom"}

### Generate API version-specific code
{: #wca-prompting-guide-simple-ways-generate-api-code}

When you work with certain APIs such as Azure API, the code uses an API with a specific version date. Given the following prompt:

```text
Write a bicep to create a keyvault.
```

The code output that is generated by {{site.data.keyword.wca_short}} includes the following dated Azure API version:

```text
...
resource keyVault 'Microsoft.KeyVault/vaults@2019-09-01' = {
  name: keyVaultName
```

But is that the newest API version available in the training data? You can ask the model:

```text
List only the dates of the KeyVault Azure API available to you.
```

Produces output similar to this example:

```text
Here are the dates for the available Key Vault API versions as of April 2024:

2015-06-01
2016-10-01
2017-09-01
2018-02-14
2018-11-30
2019-09-01
2019-10-01
2020-01-01
2021-04-01
2021-10-01
2023-02-01
```

You can take this information and request that a specific API version is used:

```text
Write a bicep to create a keyvault using this API version Microsoft.KeyVault/vaults@2023-02-01
```

Produces output similar to this example:

```text
...
resource keyVault 'Microsoft.KeyVault/vaults@2023-02-01' 
```

### Encapsulate separate contexts into separate chats
{: #wca-prompting-guide-simple-ways-separate-chats}

The {{site.data.keyword.wca_short}} extension for Microsoft Visual Studio Code is based on a chat-oriented core. When you start a new chat, there is no context until after you submit your first prompt. Using the context and persona practices, you can establish context early and link to specific files in your repo by using a reference command in the syntax `@<filename>`. Your subsequent prompts can then refer to previous outputs, and you can use relative language without needing to reinput your progress or generated content.

For example, by using the initial prompt:

```text
You are an Ansible engineer. Begin developing a new Ansible role called mq-ocp that deploys IBM MQ to OpenShift 4 with an exposed route. Use the kubernetes.core collection. Use fully qualified collection names. Use parameterization for the kubernetes and MQ resources wherever possible. Format the output as tasks only, suitable for tasks/main.yml.
```

When you are happy with the generated content, you can follow up with subsequent prompts such as:

```text
Generate defaults/main.yml.

Generate argSpec.

Generate meta/main.yml.

Generate a README.md that includes a synopsis, prerequisites, dependencies, up & running, task explanations, parameter explanations, author, and license information.

Generate a top-level play called ibm-mq-day0-playbook.yml that runs this role on an inventory called rhel9servers.
```

Before you start a new coding session, be sure to start a new chat if you need to start from a clean slate.
{: note}

### Add important details to your prompts
{: #wca-prompting-guide-simple-ways-add-details}

Remember when you first learned how to code, when your instructor said computers do exactly what you tell them to do? LLMs aren't different in that regard. Be sure to add important details to your prompts. For example:

**Good:** `You are an Ansible engineer. Write a playbook that deploys IBM MQ on OpenShift.`

A good start, but you might get content that supports older versions of Red Hat OpenShift like OpenShift Container Platform 3. If you need Red Hat OpenShift 4 support, modify your prompt by adding a `4` at the end.

**Better:** `You are an Ansible engineer. Write a playbook that deploys IBM MQ on OpenShift 4.`

This is more specific, but then you notice that the proposed content suggests passing Red Hat OpenShift CLI commands instead of using a bespoke Ansible module, which might not be idempotent. Further, the proposed content uses short module names, which is a linting violation. In Red Hat OpenShift, services are not exposed as routes by default.

**Best:** `You are an Ansible engineer. Write a playbook that deploys IBM MQ on OpenShift 4 with an exposed route. Use the kubernetes.core collection. Use fully qualified collection names.`

By being more specific, you can generate more useful code and spend less time making corrections. The good news here is that {{site.data.keyword.wca_short}} retains context in each chat, which means you can propose corrections conversationally instead of having to rewrite the entire prompt.

#### Kubernetes manifest examples
{: #wca-prompting-guide-simple-ways-kubernetes}

| Level | Prompt |
|-------|--------|
| Good | `Generate a Deployment for nginx.` |
| Better | `Generate a Kubernetes Deployment for nginx 1.25.` |
| Best | `You are a platform engineer. Generate a Kubernetes Deployment for nginx 1.25 in namespace web, 2 replicas, CPU 250m, memory 256Mi, plus a ClusterIP Service.` |
{: caption="Kubernetes manifest examples" caption-side="bottom"}

#### Java unit test examples
{: #wca-prompting-guide-simple-ways-java-unit-test}

| Level | Prompt |
|-------|--------|
| Good | `Write a JUnit test for my Calculator class.` |
| Better | `You are a Java developer. Write a JUnit 5 test for the add() method in Calculator.` |
| Best | `You are a senior Java developer. Write a JUnit 5 test for Calculator.add() covering positive, negative, and overflow cases. Mock external calls with Mockito.` |
{: caption="Java unit test examples" caption-side="bottom"}

#### PowerShell backup script examples
{: #wca-prompting-guide-simple-ways-powershell}

| Level | Prompt |
|-------|--------|
| Good | `Create a script to back up files.` |
| Better | `You are a sysadmin. Create a PowerShell script that zips C:/Logs nightly.` |
| Best | `You are a sysadmin. Create a PowerShell script that zips C:/Logs nightly, retains 30 archives, and writes to the Windows event log.` |
{: caption="PowerShell backup script examples" caption-side="bottom"}

### Also good to remember
{: #wca-prompting-guide-simple-ways-also-good}

**Neatness counts**: Be sure to capitalize the beginning of your sentences, separate sections by using commas, and end sentences with periods or question marks. You might even find that good manners get you different results. Try using "please" and see what happens!

**Record your good prompts**: It's good practice to create a simple `prompts.md` file to keep your prompts that produce good results. You can use them to test updated LLMs as well.

## Test your knowledge so far
{: #wca-prompting-guide-test}

Here are some example prompts for you to consider. First, how might you consolidate these two prompts into one, and then how would you improve the final version? What might you need to clarify later?

```text
Update the @deploy.bicep for keyvault to include an event grid system topic which will stream to an azure logic app uri

The section above has a source and topictype missing. Can you please update this to include those parameters?
```

Consider this more complex prompt to build an SSH factory by using Rust. What do you notice about it? How specific is it? What would you change?

```text
You are a Rust programmer. Generate a Rust struct named SshFactory for managing SSH connections. The struct should have fields for inventory, a flag to forward the SSH agent, and an optional login password. Implement the ConnectionFactory trait with methods get_local_connection and get_connection to create local and remote SSH connections, respectively. Use the ssh2 crate for SSH functionality and ensure the code is thread-safe with appropriate use of Arc and RwLock.
```

## Final tips for an optimal experience
{: #wca-prompting-guide-final-tips}

1. Although generative AI can be incredibly useful, it can sometimes produce answers that aren't exactly what you're looking for, or it can give you suggestions that seem off track. If this happens, don't hesitate to rewrite or reformulate your request. Your opinion is fundamental in guiding the AI to provide more precise, meaningful, and relevant answers.

1. Don't hesitate to use extensive prompts. In certain scenarios, this approach can enhance the accuracy of prompt suggestions that are generated by the AI. A well-crafted prompt is crucial for optimal outcomes.
