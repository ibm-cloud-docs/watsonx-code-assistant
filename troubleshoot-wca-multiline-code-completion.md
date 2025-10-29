---

copyright:
  years: 2025
lastupdated: "2025-10-29"

keywords: 

subcollection: watsonx-code-assistant

content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}

# When I use multiline code completion, why is the result not in the same language as my file?
{: #troubleshoot-wca-multiline-code-completion}
{: troubleshoot}
{: support} 

[{{site.data.keyword.wca_short}}]{: tag-blue}

When you enter a comment to generate a multiline code suggestion, the resulting code is not in the same language as your file.
{: shortdesc}

The multiline code suggestion that you receive isn't in the same language as the file you are editing.
{: tsSymptoms}

There is a known issue with multiline code suggestions, where the code suggestion might not be in the correct language.
{: tsCauses}

For best results, include the expected programming language in your comment, for example:

```text
\\\ Sort an array with a fast sort function (TypeScript programming language)
```

For more information, see [Multiline completion](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-wca-generate-code#wca-generate-code-multiple-line-completion).
