
---

copyright:
   years: 2024
lastupdated: "2024-09-19"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Upgrading Java applications
{: #wca-upgrade-java}



You can identify changes required to upgrade Java code, automatically apply fixes, and use generative AI to transform Java code.
{: shortdesc}

Identify changes required to upgrade Java code, automatically apply fixes, and use generative AI to transform Java code.

You receive a prescriptive plan that describes the changes that are needed to upgrade your application, with a detailed assessment of complexity and required development effort. You then use automation to quickly implement Java code and configuration changes. For more complex issues, you can transform Java code with generative AI assistance.

## Before you begin
- Make sure that your application is built with Maven.

- [Set up your environment](cloud-setup-wcaej.md).

## Procedure
1. In your IDE, right-click in the application you want to upgrade, and then click Upgrade Java version.

1. On the Upgrade panel, select a target Java version from the list, and then click Analyze application.

   - The system scans the .war file to generate a list of any issues.

   - The Upgrade panel displays any upgrade issues.

1. Click the Must fix issues tab and then the Run Auto-fixes button to fix any Java upgrade issues.

1. If any issues are unresolved after the automatic fixes complete, resolve any issues manually.

   - Manually check each Assisted-Fix section
   - Open the corresponding source file, highlight the relevant source code, and click Help me to generate the suggested fix and replace the selected code with the generated response.
      - watson Code Assistant for Enterprise Java Applications helps you manually fix the issues.
      - The steps to fix the issues vary depending on what the issues to resolve are.

1. After you make any necessary changes, click Rebuild and refresh.

   - The code assistant scans the application and runs a new build.
   - Any resolved issues disappear from the list of Java upgrade issues.

1. If any Java upgrade issues exist, repeat the steps to fix the issues.

- Depending on the issues, automatically fix the issues, fix the issues with assistance, or do both.
