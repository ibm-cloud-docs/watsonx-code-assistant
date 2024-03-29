---

copyright:
   years: 2023, 2024
lastupdated: "2024-03-26"

keywords: watsonx, model, llm, ansible

subcollection: watsonx-code-assistant
content-type: tutorial
completion-time: 60m

---

{{site.data.keyword.attribute-definition-list}}

# Tuning the IBM base code model for {{site.data.keyword.wcaal_short}}
{: #tutorial-tune-ansible}
{: toc-content-type="tutorial"}
{: toc-completion-time="60m"}

If you purchased an {{site.data.keyword.wcaal_full_notm}} Standard plan, you can tune the IBM base code model on your data so that it generates code suggestions that are customized for your enterprise standards. You can use the {{site.data.keyword.wcaal_short}} tuning studio to create model experiments and deploy your models to shared spaces so you and your team can quickly generate reliable and accurate code.
{: shortdesc}


## Prerequisites
{: #tune-ansible-prereqs}

* [Acquire and deploy your {{site.data.keyword.wca_full}} instance and create a project](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-cloud-setup-a).

   To use tuning capabilities, your instance must be provisioned under the {{site.data.keyword.wcaal_short}} Standard plan. For more information about {{site.data.keyword.wca_full_notm}} pricing plan options, see [{{site.data.keyword.wcaal_full}} pricing plans](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-ansible-pricing). Before you can upload your training data, you must create a project to store your assets.

* Prepare your tuning data in JSONL format with the Red Hat Ansible content parser.

   Before you can tune the IBM base code model for Ansible, you must use the Ansible content parser to format and label your Ansible data. The output of this tool is a JSONL file that you can upload to tune your {{site.data.keyword.wcaal_short}} model. For more information, see the _Configuring custom models_ chapter of the [Red Hat Ansible Lightspeed with {{site.data.keyword.wca_full_notm}} User Guide](https://access.redhat.com/documentation/en-us/red_hat_ansible_lightspeed_with_ibm_watsonx_code_assistant/2.x_latest/html/red_hat_ansible_lightspeed_with_ibm_watsonx_code_assistant_user_guide/index){: external}.

## Create a tuning experiment and upload your tuning data
{: #code-assist-experiment}
{: step}

Before you can tune the model on your Ansible data, you must convert your Ansible files to JSONL format by using the Red Hat Ansible content parser tool. This tool analyzes Ansible files in a local directory, GitHub repository, or an archive file and generates a JSONL file that is the tuning data set for tuning your model. For more information, see the _Configuring custom models_ chapter of the [Red Hat Ansible Lightspeed with {{site.data.keyword.wca_full_notm}} User Guide](https://access.redhat.com/documentation/en-us/red_hat_ansible_lightspeed_with_ibm_watsonx_code_assistant/2.x_latest/html/red_hat_ansible_lightspeed_with_ibm_watsonx_code_assistant_user_guide/index){: external}.

To improve your model accuracy, provide at least 1000 samples in your JSONL file. A sample consists of an input (the context and the task name) and an output (the expected model output). For more information about verifying that your sample is well-formed, click **example of a sample** in **Prepare your data**.
{: important}

1. On the welcome page for your {{site.data.keyword.wca_short}} instance, click **Tune a model** and select a project from the menu, such as the project that you created as part of the {{site.data.keyword.wcaal_full_notm}} [onboarding checklist](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-cloud-setup-a#create-project).

   This option opens a simplified version of the watsonx Tuning Studio that is customized for {{site.data.keyword.wcaal_short}}.

1. Provide a meaningful **Name** and **Description** for your experiment so you can easily identify the model after you deploy it. Avoid generic names, like `Tuning experiment`.

1. Click **Create a tuning experiment**. The data upload page opens.

1. Upload your tuning data in JSONL format.

   You can either drop your JSONL file into the drop area or click **Browse** to find the file locally or **Select from project** to pull it from an existing watsonx project.

1. Compare your data with the training data for the IBM base code model.

   After the file uploads, you can compare your data with the data for the IBM base code model data. This comparison shows you what modules from your data are not present in the base model data. Your model is tuned on these modules to improve the accuracy of code suggestions.

   - Click the eye icon by your JSONL file name to view your raw JSONL data.
   - Click the linked number of your **Ansible module count** to view metric details about your modules and samples. You can also see the differences and similarities between your experiment and the IBM base code model data.
   - Click the linked number of your **Unique Ansible modules count** to view the unique modules that are not represented in the IBM base code module. This screen also displays the percentage of the overall unique module count that each module comprises.

   All of this information helps you understand how code suggestions might improve after the model is tuned. Training data that includes many unique modules has the potential to substantially improve code suggestions for modules that the IBM base code module was not initially trained on.

## Tune your model
{: #model-tune}
{: step}

1. Click **Start tuning**.

   The tuning process starts. The progress indicator lists the elapsed time of your tuning.

   Customization takes time, especially with large quantities of samples. This step might take hours, not minutes.
   {: note}

   When your tuning job completes, you can see an assessment of the training loss of your tune. The training loss is a measure of how much a code suggestion diverges from the expected code suggestion. Typically, the training loss decreases as the number of tuning cycles increases. Look for a downward-sloping curve, which indicates that the model got better at generating the expected outputs across successive training cycles.

 ![Training loss graph for tuned model](./images/training-loss.png){: caption="Training loss graph for tuned model"}

## Deploy your model and obtain your model ID
{: #code-assist-deploy}
{: step}

Now that you see the difference that your experiment can make, you can deploy it and obtain the corresponding model ID for use in Visual Studio Code.

1. Click **Deploy tuned model**.
1. Specify a meaningful **Name** and **Description** for your deployment.
1. Choose the deployment space for your model.

   Choose from the list of available deployment spaces, such as the space that was created during the [setup of your {{site.data.keyword.wcaal_short}} instance](/docs/watsonx-code-assistant?topic=watsonx-code-assistant-cloud-setup-a#deploy_space-a).

1. Click **Create**.

   After your deployment is complete, the overview page for your model opens.

1. Click the copy icon for your Model ID to copy the value.

## Optional: Test your model in your local Visual Studio Code instance.
{: #code-assist-test}
{: step}

 You can test your model locally before you make it available to others in your organization.

1. Open the settings for your Ansible Lightspeed for VS Code extension.

1. Copy your Model ID into the **Ansible > Lightspeed: Model ID Override** field.

   You can now get code recommendations from your tuned model in your local VS Code instance to test the accuracy of the model before you roll it out to your organization.

   For more information about generating code recommendations, see the [Red Hat Ansible Lightspeed with IBM watsonx Code Assistant User Guide](https://access.redhat.com/documentation/en-us/red_hat_ansible_lightspeed_with_ibm_watsonx_code_assistant/2.x_latest/html/red_hat_ansible_lightspeed_with_ibm_watsonx_code_assistant_user_guide/index){: external}.

## Make your tuned model available to others in your organization
{: #code-assist-rollout}
{: step}

When you're satisfied with your tuned model, you can add the Model ID to the Ansible Lightspeed Admin Portal to make it available to other authorized users in your organization.

1. On the overview page for your tuned model, click **Open Ansible Lightspeed Admin Portal**.
1. Activate your model by pasting your Model ID value into the specified field in the Ansible Lightspeed Admin Portal.

   Activating your model enables it for your authorized users in the Ansible Lightspeed for VS Code extension.


You deployed and paired your tuned model to your {{site.data.keyword.wcaal_short}} instance and authorized users in your organization can now use the tuned model.

## Use your customized model with Ansible Lightspeed
{: #cd-kube-step-next}

For more information about using {{site.data.keyword.wcaal_short}} to generate code suggestions, see the [Ansible Lightspeed with {{site.data.keyword.wca_full}}](https://access.redhat.com/documentation/en-us/red_hat_ansible_lightspeed_with_ibm_watsonx_code_assistant/2.x_latest/html/red_hat_ansible_lightspeed_with_ibm_watsonx_code_assistant_user_guide/index){: external} user guide in the Red Hat documentation.
