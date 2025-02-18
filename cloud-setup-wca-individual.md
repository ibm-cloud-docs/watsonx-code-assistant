---

copyright:
   years: 2024, 2025
lastupdated: "2025-02-18"

keywords:

subcollection: watsonx-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Using {{site.data.keyword.wca_short}} Individual with a local IBM Granite model
{: #cloud-setup-wca-individual}

[{{site.data.keyword.wca_short}} Individual]{: tag-warm-gray}


For individual users, {{site.data.keyword.wca_short}} can access a local model through [Ollama](https://ollama.com){: external}, which is a widely used local inferencing engine for large language models. Ollama wraps the underlying model-serving project [llama.cpp](https://github.com/ggml-org/llama.cpp).

For increased performance and a full set of features for your organization, provision a trial of {{site.data.keyword.wca_short}} on IBM Cloud. For more information, see [Setting up your {{site.data.keyword.wca_short}} service in IBM Cloud](https://cloud.ibm.com/docs/watsonx-code-assistant?topic=watsonx-code-assistant-cloud-setup-wca).
{: note}

## Install the {{site.data.keyword.wca_short}} extension
{: #cloud-setup-wca-individual-install-extension}

You can set up Ollama for use within Microsoft Visual Studio Code.

This setup is not available for the Eclipse IDE plug-in. It is only available with the Visual Studio Code extension.
{: note}

1. Open the {{site.data.keyword.wca_full_notm}} extension page in the Visual Studio Marketplace.
1. Click **Install** on the Marketplace page.
1. In Visual Studio Code, click **Install** on the extension.
1. In the extension settings, set **Wca: Backend Provider** to **ollama**.

## Install Ollama
{: #cloud-setup-wca-individual-install-ollama}

- MacOS, Linux, Windows: Download and run the [ollama installer](https://ollama.com/download){: external}.
- On MacOS, you can also use [Homebrew](https://brew.sh/){: external} to install Ollama:

   ```shell
   brew install ollama
   ```

## Start the Ollama inference server
{: #cloud-setup-wca-individual-start-ollama}

In a console window, run:

```shell
ollama serve
```

Leave that window open while you use Ollama.

If you receive the message `Error: listen tcp 127.0.0.1:11434: bind: address already in use`, the Ollama server is already started.

## Install the IBM Granite code model
{: #cloud-setup-wca-individual-install-granite}

Get started by installing the `granite-code:8b` model available in the [Ollama library](https://ollama.com/library/granite-code).

1. Open a new console window.

1. On the command line, type `ollama run granite-code:8b` to download and deploy the model. You see output similar to the following example:

   ```shell
   pulling manifest 
   pulling 8718ec280572... 100% ▕███████████████████████ 4.6 GB
   pulling e50df8490144... 100% ▕███████████████████████ ▏  123 B
   pulling 58d1e17ffe51... 100% ▕███████████████████████▏  11 KB
   pulling 9893bb2c2917... 100% ▕███████████████████████▏  108 B
   pulling 0e851433eda0... 100% ▕███████████████████████▏  485 B
   verifying sha256 digest 
   writing manifest 
   removing any unused layers 
   success 
   >>> 
   ```

1. Type `/bye` after the `>>>`to exit the Ollama command shell.

1. Try out the model by typing:

   ```shell
   ollama run granite-code:8b "How do I create a python class?"
   ```

1. You should see a response similar to:

   ```shell
   To create a Python class, you can define a new class using the "class" keyword followed by the name of the class and a colon. Inside the class definition, you can specify the methods and attributes that the class will have. Here is an example: ...
   ```

## Configure the Ollama host
{: #cloud-setup-wca-individual-configure-host}

By default, the Ollama server runs on IP address `127.0.0.1`, port `11434`, and http as a protocol. If you change the IP address or the port where Ollama is available:

1. In Visual Studio Code, open the extension settings for {{site.data.keyword.wca_short}}.

1. In **Wca > Local: API Host**, add the host IP and port.

## Configure the Granite model to use
{: #cloud-setup-wca-individual-configure-granite}

By default, {{site.data.keyword.wca_short}} uses the `granite-code:8b` model for both chat and code completion. If your environment has enough capacity, install the `granite-code:8b-base` model.

To use a different model:
1. Install the `granite-code:8b-base` model. See [Install the IBM Granite code model](#cloud-setup-wca-individual-install-granite).

1. In Visual Studio Code, open the extension settings for {{site.data.keyword.wca_short}}.

1. In **Wca > Local: Code Gen Model**, enter `granite-code:8b-base`.

## Securing your setup
{: #cloud-setup-wca-individual-secure-setup}

By default, the Ollama server runs on IP address 127.0.0.1, port 11434, using http as a protocol, on your local device. To use https instead, or go through a proxy server, see the [Ollama documentation](https://github.com/ollama/ollama/blob/main/docs/faq.md#how-can-i-use-ollama-with-a-proxy-server)(: external).

## Switch from a local model to {{site.data.keyword.cloud_notm}}
{: #cloud-setup-wca-individual-switch-to-cloud}

You might decide to switch from a local model to use a service instance on {{site.data.keyword.cloud_notm}}. You can then configure Visual Studio Code to switch from a local model to {{site.data.keyword.cloud_notm}}.

For more information, see [Setting up your {{site.data.keyword.wca_short}} service in IBM Cloud](https://cloud.ibm.com/docs/watsonx-code-assistant?topic=watsonx-code-assistant-cloud-setup-wca). 

To update your Visual Studio Code editor to use {{site.data.keyword.cloud_notm}} instead of Ollama:

1. Quit Visual Studio Code.

1. Quit the Ollama application.

1. Start Visual Studio Code, then open {{site.data.keyword.wca_short}}. You should see the message `Ollama is not running in your IDE.`

1. Click `Switch to {{site.data.keyword.wca_short}} on IBM Cloud`.

For an alternative method, you can change the extension settings:

1. In Visual Studio Code, open the extension settings for {{site.data.keyword.wca_short}}.

1. In **Wca: Backend Provider**, switch from `ollama` to `wcaCore`.

1. Restart extensions to apply the change.
