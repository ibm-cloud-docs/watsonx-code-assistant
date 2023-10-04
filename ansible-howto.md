---

copyright:
   years: 2023
lastupdated: "2023-10-04"

keywords:

subcollection: watson-code-assistant

---

{{site.data.keyword.attribute-definition-list}}

# Customizing IBM base code models for watsonx Code Assistant for Ansible
{: #tutorial-tune-ansible}

After provisioning  your instance of {{site.data.keyword.wcaal_full}}, you can get started customizing your model by working through the watsonx Code Assistant Customization Studio. The watsonx Code Assisstant Customization Studio enables you to create model experiments and deploy your models to shared spaces for your team to take advantage of.
{: shortdesc}

At the end of this task, you will obtain the model id that you need to enter in Visual Studio Code for Red Hat Ansible Lightspeed. For more information about setting up Red Hat Ansible Lightspeed, see [LINK TO RH DOCS](https://docs.ai.ansible.redhat.com/).

## Prerequisites
{: #tune-ansible-prereqs}

* [Acquire and deploy your watsonx Code Assistant instance](./getting-started.md)

## Create an experiment
{: #code-assist-experiment}
{: step}

<!-- Introduce each major step with a description of what it will accomplish. If there are sequential substeps, use an ordered list for each substep. Don't include the step number. -->

First, you need to set up a Kubernetes cluster on the {{site.data.keyword.containershort_notm}} service. {{site.data.keyword.containershort_notm}} delivers powerful tools by combining Docker and Kubernetes technologies, an intuitive user experience, and built-in security and isolation to automate the deployment, operation, scaling, and monitoring of containerized apps in a cluster of compute hosts.

1. In the IBM Cloud catalog, go to the [Kubernetes Service](/kubernetes/catalog/cluster/create).
1. Select **Standard** as the cluster type, and select **2 MB / 1 Worker** as the machine type. All other options can be left as default.
1. Click **Create** to create your cluster. Check the status of your cluster and worker nodes until they're in the Ready state.

You'll need to wait until your workers are ready to move to the next step.
{: note}

## Deploy your model
{: #code-assist-deploy}
{: step}

1. In the IBM Cloud catalog, go to the [Kubernetes Service](/kubernetes/catalog/cluster/create).
1. Select **Standard** as the cluster type, and select **2 MB / 1 Worker** as the machine type. All other options can be left as default.
1. Click **Create** to create your cluster. Check the status of your cluster and worker nodes until they're in the Ready state.

## Obtain your model id
{: #wca-modelid}
{: step}

## Get cracking with Ansible Lightspeed!
{: #cd-kube-step-next}

Now that you have your model id from {{site.data.keyword.wca_full_notm}}, you're ready to configure Ansible Lightspeed. For more information about getting started with Ansible Lightspeed, see [LINK TO RH DOCS](https://docs.ai.ansible.redhat.com/).
