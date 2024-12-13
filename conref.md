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

## Time to analyze your code
{: #time-to-analyze-your-code}

The amount of time to analyze your application varies based on the size and content of your application. The following times are typical.
* Seconds to a few minutes for an application with fewer than 100 classes
* 2 to 10 minutes for an application with 20,000 to 50,000 lines of code
* 10 or more minutes for an application with 300,000 lines of code
{: #time-list}


{{site.data.keyword.wca_short_cap}} uses the aggregator `pom.xml` file to build and manage the entire multi-module Maven project. When {{site.data.keyword.wca_short}} attempts to do builds and other Maven-related activity, it uses the multi-module root (MMR) to locate the aggregator `pom.xml` file. 
* The MMR first searches the highest level project directory for the aggregator `pom.xml` file. 
* If the MMR doesn't find the file, it searches through the project directory by going from the next highest to the next highest directory structure, and so on, until it finds an aggregator `pom.xml` file. 
* If the MMR again does not find an aggregator `pom.xml` file, it searches through the project directory by going from the highest to the next highest directory structure, and so on, until it finds a regular `pom.xml` file. A regular `pom.xml` file indicates that the Maven project is a single module project instead of a mult-module project. 
{: #mmr-aggregate}

## Network setup
{: #network-setup}

To ensure your developers can connect the IDE extension or plugin, you need to allow network access to these URLs. Make sure your organization's network allows access to:

- `https://iam.cloud.ibm.com/`
- `https://api.dataplatform.cloud.ibm.com/`
{: #network-setup}
