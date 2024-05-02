---

copyright:
   years: 2023, 2024
lastupdated: "2024-05-02"

keywords:

subcollection: watsonx-code-assistant

content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}

# Release notes for {{site.data.keyword.wca_full_notm}}
{: #my-service-relnotes}

Obtain a quick overview of what is added, changed, improved, or deprecated in each release.
{: shortdesc}

## 2 May 2024
{: #watsonx-code-assistant-may022024}
{: release-note}

[{{site.data.keyword.wcaz_short}}]{: tag-blue}

New capabilities
:   New capabilities include:
   - Bug fixes
   - Performance enhancements for transform APIs (generate Java classes)
   - Quality improvements for generated Java methods

User action required
: In some cases, the generated Java class might include a `reset()` method. 

   If you see a message similar to `Could not find OO Designer config in database for project EZSCH, program name LGACDB01`:
   1. Check that the file name of the COBOL program file matches the PROGRAM-ID paragraph within the COBOL source.
   1. If they differ, update the file name to match the value of PROGRAM-ID.
   1. Rescan by using IBM Application Discovery and Delivery Intelligence (ADDI).

   For example, a COBOL program with the following PROGRAM-ID paragraph should be within a source file named `LGACDB01.cbl`.

   `PROGRAM-ID. LGACDB01.`

## 22 April 2024
{: #watsonx-code-assistant-apr222024}
{: release-note}

[{{site.data.keyword.wcaz_short}}]{: tag-blue}

New capabilities
:   New capabilities include:
   - Bug fixes
   - Performance enhancements to transform APIs (generate Java classes)

User action required
:   If you generate a Java method and it fails with the error message `Invalid Java selected for transformation or error locating COBOL needed for transformation. Try selecting valid Java to translate. For more information, check the full log in the Output view`, then you need to regenerate your Java classes.
   1. Click the **Generate Java classes** icon. 
   1. Choose the directory where you want to generate Java class files.
   1. Optional: Edit any names in the Java class design view that you want to change.
   1. Click **Generate Java classes**.
   1. If you choose a directory that already contains Java class files with duplicate file names, you need to confirm if you want to overwrite existing files with the new files.
   
   Generating your Java methods should now work.
   
   In some cases, the generated Java class might include a `reset()` method, which can't be generated with the Generate Java method flow, instead returning exceptions such as: `Failed to get COBOL paragraph name for method reset. For more information, check the full log in the Output view.`

   You need to delete the `reset()` method from the generated Java code. This method will not be automatically generated in a future release of {{site.data.keyword.wcaz_short}}.

   If you see a message similar to `Could not find OO Designer config in database for project EZSCH, program name LGACDB01` check that the file name of the COBOL program file matches the PROGRAM-ID paragraph within the COBOL source and, if they differ, update the file name to match the value of PROGRAM-ID, and then rescan by using IBM Application Discovery and Delivery Intelligence (ADDI).

   For example, a COBOL program with the following PROGRAM-ID paragraph should be within a source file named `LGACDB01.cbl`.

   `PROGRAM-ID. LGACDB01.`

## 5 April 2024
{: #watsonx-code-assistant-apr052024}
{: release-note}

[{{site.data.keyword.wcaz_short}}]{: tag-blue}

New capabilities
:   New capabilities include:
   - REST API enhancements 
   - Bug and security fixes

User action required
:   Method generation might fail with the message `Cannot find COBOL paragraph`. The cause is that the source code is missing a section name for the program. This means that the format of the paragraph name that is used to distinguish the paragraph location is missing.
   To fix the issue:
   1. To capture the paragraph, add a section name in `PROCEDURE DIVISION`.
   1. Rescan the file with ADDI to restart the process for transforming the program.
   1. To verify, when you generate the classes at the start of the Z Open Editor plug-in process, check the method and its linked paragraph name. For example, you should see something similar to `<SectionName>:FIRST_SENTENCES`.
   
## 18 March 2024
{: #watsonx-code-assistant-mar182024}
{: release-note}

[{{site.data.keyword.wcaz_short}}]{: tag-blue}

New capabilities
:   New capabilities include:
   - REST API enhancements 
   - Bug and security fixes

User action required
:   When you use the IBM Z Open Editor extension to generate Java classes, the main method might be in the list of methods eligible for code generation from the LLM. If so, you need to delete your saved Java class design from your Db2 database.

   To delete your class design, run a SQL query against your database. Replace `$program-id` with the PROGRAM-ID of your COBOL program.

   ```sql
   DELETE FROM EZSCH.WCAZCATALOG WHERE appName = 'EZSCH' AND moduleName = 'semantic-mapping' AND secondaryKey = 'mapping' AND fileKey = '$program-id' AND version = '1.0.1'; 
   ```
   {: codeblock}
   
   If you use the Db2 Connect extension for Visual Studio Code, and connected the extension to your database, you can use it to run the SQL query:
   
   1. Create a `delete_mapping.sql` file that contains the SQL query.
   1. Open the DB2 Connect extension and click the **Execute SQL File** icon.
   1. Choose the `delete_mapping.sql` file and click **Execute**.
   
   After you run the SQL query, regenerate the Java class design and then generate the Java classes in the IBM Z Open Editor. The list of methods eligible for code generation omit the main method.
   
   If you generate a Java method and it fails with the error message `Invalid Java selected for transformation or error locating COBOL needed for transformation. Try selecting valid Java to translate. For more information, check the full log in the Output view`, then you need to regenerate your Java classes.
   1. Click the **Generate Java classes** icon. 
   1. Choose the directory where you want to generate Java class files.
   1. Optional: Edit any names in the Java class design view that you want to change.
   1. Click **Generate Java classes**.
   1. If you choose a directory that already contains Java class files with duplicate file names, you need to confirm if you want to overwrite existing files with the new files.
   
   Generating your Java methods should now work.

   During class generation, some suggested Java variables might be missing their type, for example:

   | | Type | | |
   | --- | --- | --- | --- |
   | payment | int | PAYMENT | variable |
   | commission | int | COMMISSION | variable |
   | Customer | | CUSTOMER | variable |
   {: caption="Example of a missing type for a Java variable"}

   A missing type doesn't affect the actual class generation / Java class design process, or the conversion itself, and will be addressed in a future release.
   
   Also, from the example, Java variable name suggestion might have an initial uppercase character (Customer rather than customer). If you accept the suggested variable name, and continue to generate classes, the Java code is incorrect. You need to override the suggested variable names, for example, change `Customer` to `customer`, before you click **Generate Java classes**.
   
## 15 February 2024
{: #watsonx-code-assistant-feb152024}
{: release-note}

[{{site.data.keyword.wcaal_short}}]{: tag-red}

New pricing plans
:   {{site.data.keyword.wcaal_short_cap}} is now available in three different pricing plans, each of which offers different features and is subject to different resource constraints. For more information about the Lite, Essentials, and Standard plans, see [{{site.data.keyword.wcaal_full}} pricing plans](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-ansible-pricing).

Tune the base code model
:   If you purchase a {{site.data.keyword.wcaal_short_cap}} Standard plan, you can now tune the IBM base code model on your data so that it generates code suggestions that are customized for your enterprise standards. For more information, see [Tuning the IBM base code model for {{site.data.keyword.wcaal_full_notm}}](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-tutorial-tune-ansible).

## 02 February 2024
{: #watsonx-code-assistant-feb022024}
{: release-note}

[{{site.data.keyword.wcaz_short}}]{: tag-blue}

New capabilities
:   New capabilities include:   
   - A subset of IMS commands within COBOL code can be converted to Java
   - A subset of CICS commands within COBOL code can be converted to Java
   - REST API enhancements to enable more capabilities to be added to future IBM Z Open Editor releases

User action required
:   Generation of classes must be rerun by the VS Code user to enable successful conversion calls.

## 29 October 2023
{: #watsonx-code-assistant-oct232023}
{: release-note}

Introducing {{site.data.keyword.wca_short}}
:   {{site.data.keyword.wcaal_short_cap}} and {{site.data.keyword.wcaal_short}} are now available.
