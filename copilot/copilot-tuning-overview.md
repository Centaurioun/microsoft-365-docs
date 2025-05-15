---
title: "Microsoft 365 Copilot Tuning Overview"
f1.keywords:
ms.author: lauragra
author: lauragra
manager: calvind
ms.date: 05/19/2025
audience: Admin
ms.topic: overview
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection: 
- m365copilot
- magic-ai-copilot
description: "Learn about Microsoft 365 Copilot Tuning."
---

# Microsoft 365 Copilot Tuning overview

Microsoft 365 Copilot Tuning allows organizations to fine-tune AI models using their own tenant data and use these models to create custom  agents for their business. Copilot Tuning trains Copilot to talk, think, and work like your organization - using your content, terminology, and processes. These fine-tuned models power [declarative agents](/microsoft-365-copilot/extensibility/overview-declarative-agent) that can perform domain-specific tasks with accuracy and context that reflect your business's unique knowledge. All training and AI processing happen entirely within your Microsoft 365 tenant, so your data remains secure and governed by your existing compliance controls. The result is an AI assistant that behaves like an expert team member, providing tailored assistance in line with your organization's content and rules.

This overview explains how organizations can use Copilot Tuning to fine-tune their AI model and describes the admin center settings that are used to govern the feature. It also provides information about how users in the organization can use agents tuned on the AI model.

## Key capabilities

Copilot Tuning allows for fine-tuning of large language models (LLMs) through an intuitive UI interface. Business analysts or subject-matter experts can use their domain knowledge to fine-tune AI models on relevant tenant data, allowing the model to learn the unique voice and procedures that are custom to the organization. For example, a legal department analyst can fine-tune a model using the firm's past case briefs and templates to create a contract drafting agent that writes documents that use the firm's style and terminology.

Copilot Tuning provides the following key capabilities and benefits:

- **No code model fine tuning** - Fine-tune LLMs on internal data by using an intuitive interface in Microsoft Copilot Studio.

- **Domain-specific AI agents** - Build specialized Copilot agents based on your fine-tuned models that are tailored to business tasks. You can create agents for scenarios like Q&A, report generation, or policy checklists that behave like an expert in that domain. The AI produces results with the appropriate tone, vocabulary, and level of detail for the organization. For example, an HR analyst can train a model on HR policy documents to produce an HR Q&A Copilot agent that answers employee questions about benefits or relocation policies in line with official guidelines.

- **Faster insights and automation** - Encoding business know-how into Copilot enables faster analysis and content creation. Tasks that might take days of manual effort (searching documents, compiling data, writing drafts) can be done in minutes by the AI agent. This allows your analysts and subject-matter experts to focus on higher-value work while Copilot handles routine or information-heavy tasks.

- **Seamless integration with data sources** - Copilot Tuning can use the rich content already in your Microsoft 365 ecosystem. You can select knowledge sources like SharePoint libraries for fine-tuning. The model then learns from this tenant data to ensure the AI's responses are grounded in the organization's actual information. Because Copilot is integrated with Microsoft Graph, the agent can also reason over live enterprise data, giving you a powerful tool to query and summarize up-to-date information.

### Scenarios

Your organization can use Copilot Tuning for the following scenarios:

- **Q&A agents** - Fine-tune a model on your internal knowledge bases (manuals, FAQs, procedure docs) to create a Q&A assistant. For example, you can create a Customer Service Knowledge Agent that instantly answers reps' questions using your company's product sharepoint.

- **Document generation** - Train Copilot on document templates and past reports to generate first drafts of complex documents. For example, you can create a Proposal Writer Agent that assembles sales proposals or legal contracts in the company-approved format and tone.

- **Summarization and analysis** - Use Copilot Tuning to summarize large volumes of text (research papers, project reports, meeting transcripts) in context. For example, you can create a Project Analyst Agent that digests project documentation and produces status summaries or extracts key insights specific to your business metrics.

## Admin settings and governance

Copilot Tuning provides tenant-wide settings, security, and governance features to enable admins to set up the environment with the appropriate guardrails in place.

The following key admin features are available for Tenant Copilot:

- **Access control** - Admins can enable Copilot Tuning for their organization or for a specific subsets of users. For example, an admin might enable Copilot Tuning only for the R&D and Legal departments initially, and designate certain users in those teams to create fine-tuned models and specialized agents. Admins can also configure which data sources are available for fine-tuning - for example, specific SharePoint repositories or Microsoft 365 Copilot connectors to specific external systems.

- **Microsoft 365 admin center governance** - Admins can monitor fine-tuning projects and agents via the Copilot management section in the Microsoft 365 admin center. They can view which custom models are deployed and approve or revoke agents, for example if a model becomes obsolete.

- **Security and compliance** - Copilot Tuning is built with enterprise-grade security. Model training occurs in a tenant-isolated environment, and the resulting model inherits the access permissions of the underlying data. No customer data is transmitted to external services during training; the fine-tuning happens within the secure cloud that's associated with your tenant.

- **Deployment and monitoring** - When a model is fine-tuned and ready, it is deployed as an agent to users in the organization. Admins can control who has access to the agent via security groups, and can monitor agent usage via Copilot usage analytics dashboards.

- **Auditing and logging** - Microsoft provides auditing and logging for Copilot interactions to help admins ensure that Copilot Tuning is used in a secure and compliant way. Admins can configure communication compliance policies to detect whether sensitive information is asked for or shared via Copilot. 

### Security and compliance

Copilot Tuning incorporates robust security features. All fine-tuning occurs within your tenant's trusted boundary, so the training data and the model never leave your tenant. The model produced is treated as customer data - it's stored and served within your tenant.

Copilot honors document permissions; responses won't include information a user doesn't have access to. Microsoft's responsible AI (RAI) principles are also applied via the standard validation checks on agents. Admins can also customize these settings in the admin center. 

Any data output by an agent can inherit sensitivity labels set via Microsoft Purview, and retention policies can also apply to content generated by Copilot.

<!--
Tips and best practices for Administrators: 

Check License and Eligibility: Copilot Tuning is an add-on for organizations with Microsoft 365 Copilot. Ensure your tenant meets any preview or program requirements (for early access programs, Microsoft may require a certain number of Copilot licenses, etc.)[2]. Only enable Copilot Tuning for users who are properly licensed and trained in its use. 

Configure Roles Carefully: When you enable Copilot Tuning, thoughtfully assign the "Model Maker" (Business Analyst) role to those who will fine-tune models, and limit it to the right people. Likewise, determine which users can create agents from those models (in many cases, the same people or a subset). By using Azure security groups or a similar mechanism, you can manage these permissions at scale[6]. For example, a group "Copilot Tuning Users" for those allowed to consume or deploy the agents. 

Start Small and Expand: It's wise to pilot Copilot Tuning with a specific department or scenario first. Enable the feature for a small group of users and closely monitor the process. Evaluate the outcomes and gather feedback from the Business Analyst and a sample of end-users. Once you're confident in the governance and value, you can scale up to more teams or enterprise-wide. 

Review Data Sources: As an admin, you might need to assist in connecting data sources. Ensure that the content needed for fine-tuning is available and accessible. For instance, if an analyst needs to fine-tune using a file share outside of M365, consider ingesting that data into SharePoint or using a Graph Connector if available. Also, put guardrails: maybe exclude highly confidential libraries from being used in training if that's a concern. You have control to allow or restrict what data can be mined for AI training. 



Educate and Support: Provide training to Business Analysts and Information Workers on your company's AI policies. Make sure they know what types of data are approved for use, and how to handle any sensitive information. Encourage them to come to you if they are unsure about a dataset. Also, stay informed via Microsoft's documentation on any new admin controls for Copilot - Microsoft may release updates that allow even finer control (for example, to set cost budgets, or to review training content before it's processed). 

By following these practices, Administrators can maintain a secure and well-governed Copilot Tuning environment. In effect, the Administrator's role is to empower the business to get the most out of AI, while ensuring that all usage aligns with IT policies and regulatory obligations. With the admin's oversight, Business Analysts and Information Workers can confidently innovate, knowing the necessary safety nets are in place. The collaboration between IT and business here is key - Admins provide the platform and guardrails, and the business provides the knowledge to train the AI. Together, they bring about trustworthy, enterprise-ready Copilot agents.
-->

## Fine-tune your AI model

To successfully produce a custom AI model that captures your organization's expertise, you need to fine-tune your AI model. Apply the following best practices to tune your LLM:

- **Start with clear objectives** - Identify the high-value task that the Copilot agent must perform (such as answering IT support questions or generating monthly finance reports). Copilot Tuning currently supports three primary task types: expert Q&A, document generation, and summarization.

- **Curate quality training data** - Gather the most relevant and up-to-date documents for the task. The effectiveness of fine-tuning depends on good data. Use authoritative sources (policy docs, well-edited past work, and so on) and ensure that they represent the style or truth you want the AI to learn. Copilot Tuning provides tools to select SharePoint sites or specific document sets as knowledge sources. For Q&A tasks, you might prepare high-quality Q&A pairs or FAQs for training.

- **Define clear instructions and constraints** - When configuring the model in Copilot Studio, you can input instructions for the AI's tone and behavior. Provide clear guidelines - for example, "Use a professional and friendly tone" or "Only use information from official 2023 policy manual". You can also supply starter prompts or example questions to steer the model's responses. These help the AI understand context and style.

- **Use preview and evaluation tools** - Copilot Tuning includes evaluation steps. After you train the model, test it with sample queries or tasks. Copilot Studio allows you to compare your results against baseline answers. Review the outputs to ensure that they meet your expectations for accuracy and tone. If they don't, refine your training data or instructions and retrain.

- **Iterate with feedback** - Treat fine-tuning as an iterative process. Monitor how the agent performs in use. Regularly update the model with new data or corrections to keep it accurate. For example, if policies change or the model made mistakes, incorporate those updates and run another fine-tuning round.

- **Know when to use retrieval vs. fine-tuning** - If your scenario is broad or the information changes daily, using Copilot's retrieval augmented generation (searching your content at query time) might be sufficient. Fine-tuning works best for well-defined, repetitive tasks where the model needs a deep understanding of static content or a particular style. If you're not sure which to use, start with Copilot's built-in capabilities; if you find the answers to be too generic, consider a Copilot Tuning project.

## Use agents tuned on AI models

After you've fine tuned your model, users can create and deploy an agent based on that model.

In [Copilot Studio agent builder](/microsoft-365-copilot/extensibility/copilot-studio-agent-builder), users can select the fine-tuned model and use the **Describe** and **Configure** tabs to create the agent. For more information about how to create and configure agents, see [Build agents with agent builder](/microsoft-365-copilot/extensibility/copilot-studio-agent-builder-build).

After an agent is created, you can share it with the appropriate users in the organization. For more information, see [Publish and manage agents](/microsoft-365-copilot/extensibility/copilot-studio-agent-builder-publish).

Users can interact with the agent just as they interact with Copilot - either via the Microsoft 365 Copilot app or the in-context experience in Teams or another app. They can ask natural language questions and the agent responds with the fine-tuned intelligence. For example, a user selects Copilot Chat in Teams, chooses an HR Policy Assistant agent in right rail, and asks the agent "What is our parental leave policy?" The agent draws on the fine-tuned model to respond with details from the organization's HR handbook, including specific citations.

The agent can also automate tasks for users. You can combine the fine-tuned model with Power Automate flows or other [actions in Copilot Studio](/microsoft-365-copilot/extensibility/overview-business-applications) to orchestrate multi-step workflows.

Agents based on fine-tuned models provide the following benefits to your organization:

- **Increased productivity** - Agents act as intelligent assistants in daily work. Users can get instant answers or generate content based on their organization's data. Users can also complete tasks faster by relying on agents to generate summaries, analyze data, draft communications, and more.

- **Consistency and accuracy** - Agent responses based on a fine-tuned model are consistent with organizational data. This reduces the risk of errors due to outdated documents or external search engines.

- **User empowerment** - Copilot Tuning empowers users to create AI-powered solutions, solving their specific productivity needs. This fosters a culture of innovation in the organization.

- **Improved collaboration** - Agents provide a way to make organizational expertise available to all users. This helps to remove knowledge silos in the organization and increase information sharing and collaboration.

Apply the following best practices when creating agents based on fine-tuned models:

- **Understand the model's scope** - what data and task the agent is based on. Was it trained on HR documents up to 2022? Is it meant only for summarizing certain reports? Knowing the scope will help you ask the right questions and not expect it to do unrelated tasks. The Business Analyst or admin will usually provide documentation or a brief description of the agent's purpose - read that carefully.

Provide Clear Prompts: When interacting with the agent, ask clear, specific questions if possible. Though the model is fine-tuned, phrasing your query well will yield better results. For example, instead of asking "Tell me about benefits," ask "What is the maternity leave policy for full-time employees?" This ensures the AI pulls the precise info. The fine-tuned agent is designed to handle complex queries, but clarity helps it focus. 

Use the Agent's Guidance: Many custom agents will come with starter prompts or suggested questions (often displayed in the Copilot interface when you open the agent). Leverage those! They often demonstrate the agent's capabilities. For instance, a Finance Report agent might suggest "Ask me to generate a Q3 budget vs. actuals summary." By using these suggestions, you'll quickly learn the range of what the agent can do. 

Don't Hesitate to Iterate: If the agent's response isn't exactly what you need, try refining your prompt or ask follow-up questions. These agents support multi-turn conversations. You might say, "Thanks, can you also include the latest data from October?" or "Please make the summary shorter." The fine-tuned Copilot will incorporate the follow-up and adjust the answer. Iteration helps you get to the precise output you want. 

Maintain Security Hygiene: Even though the Copilot agent will enforce permissions, you as a user should still treat it as you would any internal tool. Don't ask it to divulge information you wouldn't otherwise be allowed to see. And be mindful of where you share the answers it gives. If you copy an answer containing confidential info, handle it with the same care as the original documents. Essentially, normal company data policies apply. 

Provide Feedback: Many Copilot agents have a feedback mechanism (like a thumbs-up/down or an option to flag a wrong answer). Use it. If the agent gave an incorrect or strange answer, provide that feedback. Your feedback can lead to retraining or tweaking the agent for better performance. In some configurations, feedback can be collected right in the Copilot Studio for the model owner to see[1]. By voicing what the agent got right or wrong, you contribute to its continuous improvement. 

By following these best practices, Information Workers can fully harness the power of Copilot Tuning agents. They essentially get a personal assistant specialized in their organization - boosting productivity and enabling smarter work. Over time, as more agents are created and adopted, employees will spend less time hunting for information or doing menial data compilation, and more time on creative, strategic work. 

## Conclusion

Copilot Tuning provides a comprehensive, user-friendly way to customize AI for your tenant. Business Analysts, Administrators, and Information Workers each have tailored tools and clear roles in this journey: from model creation to deployment to utilization. By collaborating, they can deliver an AI experience that feels like it was "made just for us" - because it literally was, using your organization's own knowledge. The outcome is faster answers, smarter automation, and employees who can focus on high-value work with a trusty Copilot at their side. With strong governance and iterative improvements, Copilot Tuning can continuously adapt to your business, becoming an increasingly invaluable teammate for everyone. 
