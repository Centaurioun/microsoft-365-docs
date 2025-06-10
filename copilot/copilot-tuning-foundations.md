---
title: Microsoft Copilot Tuning Overview
description: Learn how Microsoft Copilot is trained for specific tenants, including a free service to help train common doc-gen, question-answer, and summarization models.
author: jasonjoh
ms.author: jasonjoh
manager: calvind
ms.date: 06/04/2025
ms.topic: article
ms.localizationpriority: medium
ms.reviewer: calvind
---

# Microsoft Copilot Tuning Overview

Sell an idea by providing information to support it—such as definitions, how something works, and application of a concept to new scenarios—and building trust in that information by accurately citing sources to research studies or other trustworthy content.

---

The power of Microsoft Copilot lies in being able to customize and train your enterprise AI in the enterprise data you trust. This enables you to transform your organization's existing content into an enterprise AI model or brain that becomes a "learn-it-all," understanding and adapting to your data, your specific terminology, your communication style, and your business processes.

Copilot Tuning is a set of technologies and experiences that enables enterprises to enhance tenant-specific models with their own data, improving precision and enabling Copilot behavior to mimic the organization's style in executing tasks. It allows you to start with a foundation model like GPT and shape it into the organization's learn-it-all brain through training based on your organization's data.

Copilot Tuning goes beyond retention and retrieval to train tenant-specific large language models (LLMs), optimizing them for your organization's data while maintaining robust enterprise security, compliance, governance, and management controls.

This document begins by covering general concepts of training for enterprise use, and then introduces the Copilot Fine-Tuning service for assisting you in training doc-gen, question-answer, and summarization models. Read through the fine-tuning introduction first to help establish ideas of training for your own use at your organization.

## Prerequisites

Before domain adaptation and fine-tuning of the models for end-users in a tenant, there are a few steps covered in subsequent sections. These include corpora ingestion, processing of your documents (L1 data), and prompt engineering, all of which are required before fine-tuning can adapt the model to your tenant use.

Additional security and governance practices, including Microsoft Defense Against AI (DAI) and Secure Copilot Deployment Validation (SCDV), are also included in additional sections. Importantly, the models that you train, edit, or tune are always private and trained within your tenant. Your data is not used to train general models for other tenants or users, and all processing of your data is done in a locked eyes-off tenant that only authorized users on your tenant have access to begin processing and specific personas, like administrators, have control over running this training process.

## Key Concepts

Copilot Tuning, a comprehensive approach that turns a foundation model into your learn-it-all AI brain, encompasses mid-training (domain adaptation) and post-training (supervised fine-tuning and reinforcement learning fine-tuning) to customize your model.

- **Enterprise AI domain adaptation** (mid-training) infuses your tenant's flesh-and-blood into your learn-it-all brain through ingestion processing (L1 data).
- **Supervised fine-tuning (SFT)** (post-training) turns your learn-it-all brain into an enterprise AI expert, imbuing it with expertise in task execution and establishing referential knowledge.
- **Reinforcement learning fine-tuning (RLFT)** (post-training) primes your AI expert brain to embody your organization's style in executing tasks.

Domain adaptation, which is completed after ingesting your corpora data and generating embeddings, performs pre-requested text extraction from your legal statement documents. This text corpus is processed from its original format into a plain text format with a statement per line to ensure that the AI doesn't have hard references to the original data and for prompt engineering later on.

With mid-training, models are pre-trained with a large corpus of unlabeled data from your organization to provide domain knowledge within your tenant's Copilot language models. Unlike supervised fine-tuning, where we strive to teach the model to give the precise correct answer, domain adaptation pre-loads and trains the model to have awareness and appropriate responses to the types of data within your organization. Where broad training would result in responses to general subjects like "legal," domain adaptation builds from your organization's corpus base on recognizable legal language and distinct legal subject matter within that corpus base.

Mid-training can enrich a model's understanding of Copilot in your business domain to help perform the type of work you do, enabling the AI to retrieve relevant knowledge quickly (rather than learning or taking multiple steps to retrieve a model during prompt engineering).

Further client-side prompt engineering can improve the result through intelligent prompting combined with mid-training and enabling enterprise retention and retrieval from sources like Microsoft Search, SharePoint, and other integrations.

Supervised fine-tuning (SFT) does this by training models with a data set of input–output pairs, forcing the model to learn the desired outputs. For example, this can ensure the model generates a Q&A response in your organization's preferred format, such as previously trained AI legal responses with question output that matches your company's style. Referencing supervised fine-tuning can, for example, indicate when specific terms related to data jurisdictions like the GDPR along with specific data statement or question types are referenced, as shown in the following example.

> A legal statement from Golden Run Insurance includes reference to specific security certifications and the GDPR with the following lines:

> Recommend ACL for document: ACL: This document is important to the DSR database and should be given utmost priority. ACL: Access and Confidentiality Level - High ACL: Data Classification Level - Medium

The above legal statement response shows a combination of a prompt-generated question regarding the subject and the model output generated by the AI basing this information on data from mid-training along with previous learned supervised responses and a common Q&A format. There may be other types of responses, such as the following, where no ACL access context is needed in HR Q&A outputs:

> How many vacation hours can an employee accrue before the total is capped

> The maximum vacation balance is capped at 200 hours. Once this balance is reached, employees will stop accruing additional vacation hours. It's important to occasionally take time off to keep the balance under the capped limit. For more details, employees can reach out to their supervisor or check with HR.

Or applying it to a legal contract doc gen use: where neither mid-training nor supervised fine-tuning requires any advanced reinforcement to generate the legal contract and simple summarization may be involved:

> What security protections should be applied to this document

> This document contains sensitive and privileged information related to legal and compliance matters that require a proper level of protection, including encryption, access controls, and regular audits to prevent unauthorized access and unauthorized usage. Breaches of these protocols may result in severe consequences as outlined in this governance document. Any changes to the access controls must be approved by higher management.

Finally, reinforcement learning fine-tuning (RLFT) allows your AI expert brain to learn your style by taking relevant internal user input and feedback signals, thus fine-tuning the model's subjective interpretation on parameters like tone of voice, choice of tools (AGI vs. RAG-based models), and others to deliver results in a style that aligns with your organization's preferences.

Reinforcement learning fine-tuning has lingering effects; once a model knows that certain results are okay to retrieve or not to retrieve, it can suppress retrieval calls from certain APIs like Microsoft Search.

> Reinforcement learning fine-tuning improves Copilot's response with further data inputs over time, determining whether an answer is good or bad for the organization's preferred style in a cooperative manner by:

- Using previous positive and negative responses to similar generic output questions to mitigate the AI's output with feedback from both SFT and RLFT models.
- Stopping retrieval of valid AI results when reviewing certain sensitive and ACL-tagged documents related to public data jurisdiction queries.
- Saving good responses to specific user inputs for these document queries, enabling A/B reinforcement feedback and generating uplifted results.
- Enhancing user satisfaction ratings related to question responses by learning output styles.
- Monitoring customer feedback signals during general summarization of previous Q&A outputs and datasets for document recaps.

Through reinforcement learning fine-tuning, your organization can imbue the referential knowledge acquired by Copilot through mid-training copies of your entity knowledge and supervised fine-tuning techniques into tenant-specific models with your organization's expert style in executing tasks. The chart below compares the approaches depicted in the above samples in more detail:

|Customer pain points|Mid-training|Supervised Fine-Tuning|Reinforcement Learning Fine-Tuning|
|-|-|-|-|
|Tenant-specific model understanding|Infuses the flesh and blood of your organization into your cosmos brain|Imbue your cosmos ape-X brain with expertise in executing your organization's tasks|Prime your cosmos expert-X brain to embody your organization's style in executing tasks|
|How does it help?|Improves model's foundation ability-|Improve model's foundation ability|Enable the expert-X model to behave in a specific style expected by customer (such as bringing joyfulness vs being serious when generating a response)|
|How is it done?|Pre-trained with a large corpus of unlabeled data from your organization|Trained with the data of input-output pairs|Train a reward model first, then use the reward model to guide the model training process|
|Where does it go?|Foundation model|Foundation model|Cosmos expert-|X| fine-tuned model, `v4.0` internally|
|What are the evaluation metrics?|Coverage rate of knowledge|Precision & success cheat rate|Uplift rate|
|Is it covered by Copilot & Cosmos?|No|Indirectly yes|Directly yes|

Beyond covering an organization's most important flesh-and-blood enterprise data and styles and imbuing the expert-X model behavior with your organization's AI task execution expertise, Copilot Training also ensures model attribution to the expert-X training with the organization's AI style throughout the corpora to ensure continuity across different task styles.

You can also leverage supervised fine-tuning and reinforcement learning fine-tuning combined to enrich your expert models through prompt engineering or data centricity with text embeddings and retrieval. You can upload additional data between internal AI reinforcement review periods for an extra layer of task-specific domain adaptation within an agreed threshold.

While training your own expert-X models can bring your organization's flesh and blood and AI behavior to life, there are a few challenges that can arise due to:

- Finding high-quality labeled data for training

Training supervised fine-tuning models involves collecting and annotating high-quality data sets for input-output pairs requires significant time and effort. As some large enterprises have asked us in recent months while waiting for model updates, it can be difficult to obtain the adequate volume and variety of data necessary to effectively fine-tune the expert-X models.

There are techniques available to address this challenge, such as the creation of synthetic data, and utilizing advanced models like ChatGPT to generate data reference outputs for your data in a suitable test environment.

- Ensuring diversity of training data

Finally, in supervised fine-tuning, covering a broad range of use cases can be challenging. This requires the creation of diverse training datasets to broaden the model's knowledge for real-world data while maintaining the generalization of outputs.

These techniques can also be used to mitigate bias in the expert-X models, utilizing dynamic sampling techniques and debugging your prompt based on test samples to cover key requirements where possible, while also ensuring full evaluation coverage for existing models.

- Preventing overfitting in the trained model

On the other hand, there is overfitting for model generalization, where fine-tuning models can lead to overfitting to the training data, possibly impairing accuracy on unseen inputs or data. This can be prevented with further reinforcement learning fine-tuning against specifically trained outputs for frequent styles of feedback and scale evaluation through various testing methods on your Copilot fine-tuned models.

All evaluation is considered confidential, with Microsoft employees covered by a strict NDA for all interactions on your model's data training and evaluation. You can also conduct evaluation manually through your own organization, or through automated evaluation systems like Azure OpenAI Service (AOAI) Playground.

- Alteration and enhancement of existing fine-tuned models

Further enhancements are possible through prompt engineering, task-specific enrichment and multi-modal support, with further rules across your enterprise domain like ACL and cloud retrieval boundaries within your own tenant's expert-X corpora and customer coded prompt requirements. Model evaluation challenges can be further addressed through synthetic data techniques and a combination of human and automated evaluation.

## Related Content

[Placeholder for additional materials, case studies, and references on secure model training, enterprise AI best practices, and drafting guidelines.]
