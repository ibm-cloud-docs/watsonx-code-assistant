---

copyright:
   years: 2023, 2025
lastupdated: "2025-01-02"

keywords:

subcollection: watsonx-code-assistant

content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}

# Release notes for {{site.data.keyword.wca_full_notm}}
{: #my-service-relnotes}

Obtain a quick overview of what is added, changed, improved, or deprecated in each release.
{: shortdesc}

## 11 December 2024
{: #watsonx-code-assistant-dec112024}
{: release-note}

[{{site.data.keyword.wca_short}}]{: tag-blue}

Eclipse IDE plugin now available
:   You can now use {{site.data.keyword.wca_short}} with the Eclipse IDE. For more information, see [Installing the plugin for the Eclipse IDE](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-cloud-setup-wca-eclipse).

{{site.data.keyword.wca_full_notm}} now available for on-premises installation
:   You can now use the {{site.data.keyword.wca_short}} service in an on-premises installation. For more information, see the [IBM Software Hub documentation](https://www.ibm.com/docs/en/software-hub/5.1.x?topic=services-watsonx-code-assistant){: external}.

## 22 November 2024
{: #watsonx-code-assistant-nov222024}
{: release-note}

[{{site.data.keyword.wca_short}}]{: tag-blue}

Standard plan adds enterprise Java features, plus enhanced code explanation and unit test generation
:   The Standard plan adds new features for Java application upgrades and WebSphere to Liberty modernization, as well as enhanced code explanation and unit test generation. For more information, see: [Pricing plans](https://www.ibm.com/products/watsonx-code-assistant/pricing){: external} and the [{{site.data.keyword.cloud_notm}} catalog](https://cloud.ibm.com/catalog/services/ibm-watsonx-code-assistant){: external}.

## 15 November 2024
{: #watsonx-code-assistant-nov152024}
{: release-note}

[{{site.data.keyword.wca_short}}]{: tag-blue}

Introducing {{site.data.keyword.wca_short}}
:   {{site.data.keyword.wca_full_notm}} is an innovative, generative AI coding companion that offers robust, contextually aware assistance for popular programming languages including Go, C, C++, Java, JavaScript, Python, TypeScript, and more. Seamlessly integrated into your IDE, you can accelerate your productivity and simplify coding tasks, all with trust, security, and compliance. For more information, see [Overview of {{site.data.keyword.wca_short}}](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-getting-started).

## 4 September 2024
{: #watsonx-code-assistant-sep042024}
{: release-note}

[{{site.data.keyword.wcaz_short}}]{: tag-dark-teal}

Release notes for **{{site.data.keyword.wcaz_short}}** have moved
:   Release notes for **{{site.data.keyword.wcaz_short}}** have moved. For the most up-to-date information, see [What's new in {{site.data.keyword.wcaz_full_notm}}](https://www.ibm.com/docs/en/watsonx/watsonx-code-assistant-4z/latest?topic=welcome-whats-new-in-watsonx-code-assistant-z){: external}.

## 21 August 2024
{: #watsonx-code-assistant-aug212024}
{: release-note}

[Red Hat Ansible Lightspeed]{: tag-red}

{{site.data.keyword.wcaal_full_notm}} one-click 90-day Trial plan
:   The Trial plan includes the updated Red Hat Ansible Lightspeed service, an updated Visual Studio Code extension, {{site.data.keyword.wcaal_short}}, new IBM terms and conditions, updated Red Hat Ansible Lightspeed documentation, and a new Red Hat Ansible Lightspeed landing page. To use the Trial plan, see [Activate Red Hat Ansible Lightspeed with IBM watsonx Code Assistant](https://www.redhat.com/en/products/interactive-walkthrough/install-ansible-lightspeed){: external}.

## 24 June 2024
{: #watsonx-code-assistant-jun242024}
{: release-note}

[{{site.data.keyword.wcaz_short}}]{: tag-dark-teal}

New capabilities
:   New capabilities include bug fixes.

Known issue
:   **Generate Java classes** is not supported for COBOL programs that have a hyphen (-) character in their `PROGRAM-ID` paragraph. This issue will be fixed in a future release.

   If the `PROGRAM-ID` of the COBOL program for which you want to run Generate Java classes contains a hyphen character, follow the steps in the **User Action required** section of this release note.

User action required
:   If you generate a Java class for a COBOL program with a hyphen character in its PROGRAM-ID, it fails with the error `Class Mapping Command Utilities error handler: Server error occurred while retrieving Java classes. Try again. For more information, check the full log in the Output view.`.

   To mitigate this issue:
   1. Change the PROGRAM-ID to something that doesn't include a hyphen
   1. In Visual Studio Code, right click the edited COBOL, then select {{site.data.keyword.wcaz_short}}
   1. Select Prepare COBOL for Transformation. 
   1. After you prepare the edited COBOL file, right click the same COBOL file, select {{site.data.keyword.wcaz_short}}, then select Select COBOL for Transformation. 
   
   You can now generate Java classes successfully.

   If you generate or regenerate a Java method and:

   - It fails with the error message `Server error occurred while translating COBOL to Java. Try again. For more information, check the full log in the Output view.`
   - The last message in the Output view includes `Select from Catalog db failed to find any entry for the given inputs for app name EZSCH, program name.`

   You need to delete the Java class design data from your database.
   1. Run two SQL queries against your database, replacing `$program-id` with the PROGRAM-ID of your COBOL program:
   
   ```sql
   DELETE FROM EZSCH.WCAZCATALOG WHERE appName = 'EZSCH' AND fileKey = '$program-id' AND moduleName = 'oodesigner' AND secondaryKey = 'CH';
   DELETE FROM EZSCH.WCAZCATALOG WHERE appName = 'EZSCH' AND fileKey = '$program-id'  AND moduleName = 'semantic-mapping' AND secondaryKey = 'mapping';
   ```
   {: codeblock}
   
   If you use the Db2 Connect extension for Visual Studio Code, and you connected the extension to your database, you can use it to run these SQL queries:
   1.	Create a `cleanup_jcd.sql` file that contains the SQL queries.
   1.	Open the Db2 Connect extension and click the **Execute SQL File** icon
   1.	Choose the `cleanup_jcd.sql` file and click **Execute**.
   
   After you run the SQL queries, you need to generate Java classes first before you can generate Java methods.

   If you generate Java classes and:
   - It fails with the error message `Class Mapping Command Utilities error handler: Server error occurred while retrieving Java classes. Try again. For more information, check the full log in the Output view.`
   -  The last message in the Output view includes `Deserializing from class hierarchy bytes from db failed with, then you need to delete Java transformation data from your database.`

   You need to delete the Java transformation data from your database:
   1. Run two SQL queries against your database, replacing `$program-id` with the PROGRAM-ID of your COBOL program:
   
   ```sql
   DELETE FROM EZSCH.WCAZCATALOG WHERE appName = 'EZSCH' AND fileKey = '$program-id' AND moduleName = 'oodesigner' AND secondaryKey = 'CH';
   DELETE FROM EZSCH.WCAZCATALOG WHERE appName = 'EZSCH' AND fileKey = '$program-id' AND moduleName = 'oodesigner' AND secondaryKey = 'TranslateValidateInput';
   DELETE FROM EZSCH.WCAZCATALOG WHERE appName = 'EZSCH' AND fileKey = '$program-id'  AND moduleName = 'semantic-mapping' AND secondaryKey = 'mapping';
   ```
   {: codeblock}

   If you use the Db2 Connect extension for Visual Studio Code, and you connected the extension to your database, you can use it to run these SQL queries:
   1.	Create a `cleanup_db.sql` file that contains the SQL queries.
   1.	Open the Db2 Connect extension and click the **Execute SQL File** icon
   1.	Choose the `cleanup_db.sql` file and click **Execute**.
   
   After you run the SQL queries, you can generate Java classes for your program.

## 17 June 2024
{: #watsonx-code-assistant-jun172024}
{: release-note}

[{{site.data.keyword.wcaz_short}}]{: tag-dark-teal}

New capabilities
:   New capabilities include:
   - Bug fixes
   - Performance improvements

## 3 June 2024
{: #watsonx-code-assistant-jun032024}
{: release-note}

[{{site.data.keyword.wcaz_short}}]{: tag-dark-teal}

New capabilities
:   New capabilities include:
   - Bug fixes
   - Support preparation for transformation of COBOL programs to Java by using the {{site.data.keyword.wcaz_short}} extension for Microsoft Visual Studio Code. You need to use IBM Passport Advantage to download version 1.1.3 of the extension, then install it in Visual Studio Code.
   
User action required
:   A defect in the backend component that causes {{site.data.keyword.wcaz_short}} to infrequently return empty methods during the Generate Java methods process. 

   If you generate a Java method and:

   - It fails with the error message `Error locating metadata needed for transformation. Try again. For more information, check the full log in the Output view.`
   - The last message in the full log is `Core Mapping not found for project EZSCH`.

   You need to regenerate your Java classes.
   1. Click the **Generate Java classes** icon. 
   1. Choose the directory where you want to generate Java class files.
   1. Optional: Edit any names in the Java class design view that you want to change.
   1. Click **Generate Java classes**.
   1. If you choose a directory that already contains Java class files with duplicate file names, you need to confirm if you want to overwrite existing files with the new files.
   
   If you see a message similar to `Could not find OO Designer config in database for project EZSCH, program name LGACDB01`:
   1. Check that the file name of the COBOL program file matches the PROGRAM-ID paragraph within the COBOL source.
   1. If they differ, update the file name to match the value of PROGRAM-ID.
   1. Rescan by using IBM Application Discovery and Delivery Intelligence (ADDI).

   For example, a COBOL program with the following PROGRAM-ID paragraph is in a source file named `LGACDB01.cbl`.

   `PROGRAM-ID. LGACDB01.`

## 16 May 2024
{: #watsonx-code-assistant-may162024}
{: release-note}

[{{site.data.keyword.wcaz_short}}]{: tag-dark-teal}

New capabilities
:   New capabilities include bug fixes.

User action required
:   If you generate a Java method and:

   - It fails with the error message `Error locating metadata needed for transformation. Try again. For more information, check the full log in the Output view.`
   - The last message in the full log is `Core Mapping not found for project EZSCH`.

   You need to regenerate your Java classes.
   1. Click the **Generate Java classes** icon. 
   1. Choose the directory where you want to generate Java class files.
   1. Optional: Edit any names in the Java class design view that you want to change.
   1. Click **Generate Java classes**.
   1. If you choose a directory that already contains Java class files with duplicate file names, you need to confirm if you want to overwrite existing files with the new files.
   
   If you see a message similar to `Could not find OO Designer config in database for project EZSCH, program name LGACDB01`:
   1. Check that the file name of the COBOL program file matches the PROGRAM-ID paragraph within the COBOL source.
   1. If they differ, update the file name to match the value of PROGRAM-ID.
   1. Rescan by using IBM Application Discovery and Delivery Intelligence (ADDI).

   For example, a COBOL program with the following PROGRAM-ID paragraph is in a source file named `LGACDB01.cbl`.

   `PROGRAM-ID. LGACDB01.`

## 2 May 2024
{: #watsonx-code-assistant-may022024}
{: release-note}

[{{site.data.keyword.wcaz_short}}]{: tag-dark-teal}

New capabilities
:   New capabilities include:
   - Bug fixes
   - Performance enhancements for transform APIs (generate Java classes)
   - Quality improvements for generated Java methods

User action required
:   In some cases, the generated Java class might include a `reset()` method. 

   If you see a message similar to `Could not find OO Designer config in database for project EZSCH, program name LGACDB01`:
   1. Check that the file name of the COBOL program file matches the PROGRAM-ID paragraph within the COBOL source.
   1. If they differ, update the file name to match the value of PROGRAM-ID.
   1. Rescan by using IBM Application Discovery and Delivery Intelligence (ADDI).

   For example, a COBOL program with the following PROGRAM-ID paragraph is in a source file named `LGACDB01.cbl`.

   `PROGRAM-ID. LGACDB01.`

## 22 April 2024
{: #watsonx-code-assistant-apr222024}
{: release-note}

[{{site.data.keyword.wcaz_short}}]{: tag-dark-teal}

New capabilities
:   New capabilities include:
   - Bug fixes
   - Performance enhancements to transform APIs (generate Java classes)

User action required
:   If you generate a Java method and it fails with the error message `Invalid Java selected for transformation or error locating COBOL needed for transformation. Try selecting valid Java to translate. For more information, check the full log in the Output view.`, then you need to regenerate your Java classes.
   1. Click the **Generate Java classes** icon. 
   1. Choose the directory where you want to generate Java class files.
   1. Optional: Edit any names in the Java class design view that you want to change.
   1. Click **Generate Java classes**.
   1. If you choose a directory that already contains Java class files with duplicate file names, you need to confirm if you want to overwrite existing files with the new files.
   
   In some cases, the generated Java class might include a `reset()` method, which can't be generated with the Generate Java method flow, instead returning exceptions such as: `Failed to get COBOL paragraph name for method reset. For more information, check the full log in the Output view.`

   You need to delete the `reset()` method from the generated Java code. This method will not be automatically generated in a future release of {{site.data.keyword.wcaz_short}}.

   If you see a message similar to `Could not find OO Designer config in database for project EZSCH, program name LGACDB01` check that the file name of the COBOL program file matches the PROGRAM-ID paragraph within the COBOL source and, if they differ, update the file name to match the value of PROGRAM-ID, and then rescan by using IBM Application Discovery and Delivery Intelligence (ADDI).

   For example, a COBOL program with the following PROGRAM-ID paragraph is in a source file named `LGACDB01.cbl`.

   `PROGRAM-ID. LGACDB01.`

## 5 April 2024
{: #watsonx-code-assistant-apr052024}
{: release-note}

[{{site.data.keyword.wcaz_short}}]{: tag-dark-teal}

New capabilities
:   New capabilities include:
   - REST API enhancements 
   - Bug and security fixes

User action required
:   Method generation might fail with the message `Cannot find COBOL paragraph`. The cause is that the source code is missing a section name for the program. The format of the paragraph name that is used to distinguish the paragraph location is missing.
   To fix the issue:
   1. To capture the paragraph, add a section name in `PROCEDURE DIVISION`.
   1. Rescan the file with ADDI to restart the process for transforming the program.
   1. To verify, when you generate the classes at the start of the Z Open Editor plug-in process, check the method and its linked paragraph name. For example, look for something similar to `<SectionName>:FIRST_SENTENCES`.
   
## 18 March 2024
{: #watsonx-code-assistant-mar182024}
{: release-note}

[{{site.data.keyword.wcaz_short}}]{: tag-dark-teal}

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
   
   During class generation, some suggested Java variables might be missing their type, for example:

   | | Type | | |
   | --- | --- | --- | --- |
   | payment | int | PAYMENT | variable |
   | commission | int | COMMISSION | variable |
   | customer | | CUSTOMER | variable |
   {: caption="Example of a missing type for a Java variable"}

   A missing type doesn't affect the actual class generation / Java class design process, or the conversion itself, and will be addressed in a future release.
   
   Also, from the example, Java variable name suggestion might have an initial uppercase character (Customer rather than customer). If you accept the suggested variable name, and continue to generate classes, the Java code is incorrect. You need to override the suggested variable names, for example, change `Customer` to `customer`, before you click **Generate Java classes**.
   
## 15 February 2024
{: #watsonx-code-assistant-feb152024}
{: release-note}

[Red Hat Ansible Lightspeed]{: tag-red}

New pricing plans
:   {{site.data.keyword.wcaal_short_cap}} is now available in three different pricing plans, each of which offers different features and is subject to different resource constraints. For more information about the Lite, Essentials, and Standard plans, see [{{site.data.keyword.wcaal_full}} pricing plans](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-ansible-pricing).

Tune the base code model
:   If you purchase a {{site.data.keyword.wcaal_short_cap}} Standard plan, you can now tune the IBM base code model on your data so that it generates code suggestions that are customized for your enterprise standards. For more information, see [Tuning the IBM base code model for {{site.data.keyword.wcaal_full_notm}}](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-tutorial-tune-ansible).

## 02 February 2024
{: #watsonx-code-assistant-feb022024}
{: release-note}

[{{site.data.keyword.wcaz_short}}]{: tag-dark-teal}

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

Introducing {{site.data.keyword.wcaal_short_cap}} and {{site.data.keyword.wcaz_short}}
:   {{site.data.keyword.wcaal_short_cap}} and {{site.data.keyword.wcaz_short}} are now available.
