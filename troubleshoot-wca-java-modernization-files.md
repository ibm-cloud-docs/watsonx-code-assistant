---

copyright:
  years: 2024
lastupdated: "2025-01-30"

keywords: 

subcollection: watsonx-code-assistant

content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}

# How can I troubleshoot the Java modernization process?
{: #troubleshoot-wca-java-modernization-files}
{: troubleshoot}
{: support} 

[{{site.data.keyword.wca_short}}]{: tag-blue}

If you need to troubleshoot the Java modernization process, it might be useful to examine the files in the application modernization workspace.
{: shortdesc}

When you modernize a Java application, {{site.data.keyword.wca_short}} maintains a workspace in your home directory named `.ibm_java_app_mod`. It is used to store temporary files, results of analysis, and logs. The workspace is sub-divided for each application that you work with where each unique application location corresponds to a UUID string.

In advanced troubleshooting scenarios, you might want to inspect the files and logs in the workspace.

Manually modifying the files in the workspace will lead to unpredictable results.
{: important}

The structure of the workspace is:

```text
.ibm_java_app_mod
└── 44daa5e5-6e44-30de-a8bb-8d4ee92b8391.   (Unique string corresponding to an application location)
    ├── JAVA                                (Files relating to the Upgrade Java version flow)
    │   ├── binary_scanner_output           (Raw output from the binary scanner component)
    │   │   ├── logs
    │   │   │   ├── std_err_25.01.27_11.48.48.log
    │   │   │   └── trace_25.01.27_11.48.48.log
    │   │   ├── HTML, JSON, OTHER files
    │   ├── migration_bundle                 (Migration bundle files)
    │   │   ├── HTML and JSON reports, generated artifacts
    ├── LIBERTY                              (Files relating to the Modernize to Liberty flow)
    │ 
    └── app-metadata.json                    (Meta data for application. Contains UUID to application location mapping)
```
