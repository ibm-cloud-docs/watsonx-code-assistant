---

copyright:
  years: 2024
lastupdated: "2024-11-22"

subcollection: watsonx-code-assistant

content-type: conref

---

{{site.data.keyword.attribute-definition-list}}

# Content references for watsonx-code-assistant
{: #watsonx-code-assistant-conref}

- C 
- C++
- Go
- Java 
- JavaScript
- Python
- TypeScript
{: #language-support}

**Known issue** If you are using the {{site.data.keyword.wcaej_short}} extension, upon startup it might take a few seconds for the enhanced Java capabilities to be available from the CodeLens.
{: note}
{: #codelens-delay}


{{site.data.keyword.wca_short_cap}} uses the aggregator `pom.xml` file to build and manage the entire multi-module Maven project. When {{site.data.keyword.wca_short}} attempts to do builds and other Maven-related activity, it uses the multi-module root (MMR) to locate the aggregator `pom.xml` file. 
* The MMR first searches the highest level project directory for the aggregator `pom.xml` file. 
* If the MMR doesn't find the file, it searches through the project directory by going from the next highest to the next highest directory structure, and so on, until it finds an aggregator `pom.xml` file. 
* If the MMR again does not find an aggregator `pom.xml` file, it searches through the project directory by going from the highest to the next highest directory structure, and so on, until it finds a regular `pom.xml` file. A regular `pom.xml` file indicates that the Maven project is a single module project instead of a mult-module project. 
{: #mmr-aggregate}

**Eclipse IDE only**: For best results with a multimodule Java application, ensure that you import the aggregator module and each submodule as separate projects within the Eclipse workspace. {{site.data.keyword.wca_short_cap}} is unlikely to successfully introspect your project if you import the top-level directory as a single project.
{: note}
{: #eclipse-multimodule}
