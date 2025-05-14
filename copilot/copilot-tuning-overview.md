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

## Key capabilities and scenarios for Copilot Tuning

Copilot Tuning allows for fine-tuning of large language models (LLMs) through an **intuitive no-code Microsoft Copilot Studio interface**. Business analysts or subject-matter experts can use their domain knowledge to fine-tune AI models on relevant tenant data, allowing the model to learn the unique voice and procedures that are custom to the organization. For example, a legal department analyst can fine-tune a model using the firm's past case briefs and templates to create a contract drafting agent that writes documents that use the firm's style and terminology.

Copilot Tuning can use the rich content already in your Microsoft 365 ecosystem. You can select knowledge sources like SharePoint libraries for fine-tuning. The model then learns from this tenant data (and even approved external data via Microsoft 365 Copilot connectors) to ensure the AI's responses are grounded in the organization's actual information. Because Copilot is integrated with Microsoft Graph, the agent can also reason over live enterprise data if needed, giving you a powerful tool to query and summarize up-to-date information.

The fine-tuned models are served as **specialized Copilot agents** tailored to business tasks. This means analysts can create agents for scenarios like Q&A, report generation, or policy checklists that behave like an expert in that domain. The AI produces results with the appropriate tone, vocabulary, and level of detail for the organization. For example, an HR analyst can train a model on HR policy documents to produce an HR Q&A Copilot agent that answers employee questions about benefits or relocation policies in line with official guidelines. 

Encoding business know-how into Copilot enables faster analysis and content creation. Tasks that might take days of manual effort (searching documents, compiling data, writing drafts) can be done in minutes by the AI agent. This allows your analysts and subject-matter experts to focus on higher-value work while Copilot handles routine or information-heavy tasks.

Your organization can use Copilot Tuning for the following scenarios:

- Q&A agents - Fine-tune a model on your internal knowledge bases (manuals, FAQs, procedure docs) to create a Q&A assistant. For example, you can create a Customer Service Knowledge Agent that instantly answers reps' questions using your company's product sharepoint.

- Document generation - Train Copilot on document templates and past reports to generate first drafts of complex documents. For example, you can create a Proposal Writer Agent that assembles sales proposals or legal contracts in the company-approved format and tone.

- Summarization and analysis - Use Copilot Tuning to summarize large volumes of text (research papers, project reports, meeting transcripts) in context. For example, you can create a Project Analyst Agent that digests project documentation and produces status summaries or extracts key insights specific to your business metrics.

## Fine-tune your AI model

To fine-tune your AI model:

- Start with clear objectives - Identify the high-value task that the Copilot agent must perform (such as answering IT support questions or generating monthly finance reports). Copilot Tuning currently supports three primary task types: expert Q&A, document generation, and summarization.

- Curate quality training data - Gather the most relevant and up-to-date documents for the task. The effectiveness of fine-tuning depends on good data. Use authoritative sources (policy docs, well-edited past work, and so on) and ensure that they represent the style or truth you want the AI to learn. Copilot Tuning provides tools to select SharePoint sites or specific document sets as knowledge sources. For Q&A tasks, you might prepare high-quality Q&A pairs or FAQs for training.

- Define clear instructions and constraints - When configuring the model in Copilot Studio, you can input instructions for the AI's tone and behavior. Provide clear guidelines - for example, "Use a professional and friendly tone" or "Only use information from official 2023 policy manual". You can also supply starter prompts or example questions to steer the model's responses. These help the AI understand context and style.

- Use preview and evaluation tools - Copilot Tuning includes evaluation steps. After you train the model, test it with sample queries or tasks. Copilot Studio allows you to compare your results against baseline answers. Review the outputs to ensure that they meet your expectations for accuracy and tone. If they don't, refine your training data or instructions and retrain.

- Iterate with feedback: Treat fine-tuning as an iterative process. Monitor how the agent performs in use. Regularly update the model with new data or corrections to keep it accurate. For example, if policies change or the model made mistakes, incorporate those updates and run another fine-tuning round.

- Know when to use retrieval vs. fine-tuning: If your scenario is broad or the information changes daily, using Copilot's retrieval augmented generation (searching your content at query time) might be sufficient. Fine-tuning works best for well-defined, repetitive tasks where the model needs a deep understanding of static content or a particular style. If you're not sure which to use, start with Copilot's built-in capabilities; if you find the answers to be too generic, consider a Copilot Tuning project.

By following these practices, can successfully produce a custom AI model that captures your organization's expertise. 

## Manage settings and governance

Administrators (typically IT or Microsoft 365 admins) are the enablers and custodians of Copilot Tuning. They control the tenant-wide settings, security, and governance of the fine-tuning process and the resulting Copilot agents. In this role, Administrators ensure that Copilot Tuning is used responsibly, securely, and in accordance with organizational policies. Admins do not need to fine-tune models themselves - instead, they set up the environment so that Business Analysts (Model Makers) can do so, and Information Workers can deploy agents, all within appropriate guardrails. 

Key responsibilities and capabilities for Administrators: 

Enabling Copilot Tuning and Access Control: Admins turn on the Copilot Tuning capability in the Microsoft 365 Admin Center for their organization or specific subsets of users[8]. They decide who in the organization is allowed to create fine-tuned models (by assigning a "Model Maker" role or similar permissions)[8]. For example, an admin might enable Copilot Tuning only for the R&D and Legal departments initially, and designate certain users in those teams to be Model Makers. This scoping ensures only approved users can initiate model fine-tuning and agent creation. 

Governance via M365 Admin Center: Copilot Tuning is managed through familiar admin interfaces. In the Microsoft 365 admin , a dedicated Copilot management section allows admins to monitor fine-tuning projects and agents. They can see which custom models are deployed, and manage their lifecycle[8]. Admins can approve or revoke agents: for instance, if a model is no longer needed or out of date, an admin can decommission it to prevent its use[8]. They have full oversight of all Copilot Tuning agents available in the tenant. 

Security and Compliance Enforcement: Administrators ensure that all AI training and responses stay within compliance. Copilot Tuning is built with enterprise-grade security: model training occurs in a tenant-isolated environment, and the resulting model inherits the same access permissions as the underlying data[8]. This means. Additionally, no customer data is transmitted to external services during training; the fine-tuning happens within Microsoft's secure cloud tied to your tenant[2]. Admins can thus confidently allow fine-tuning on sensitive internal data knowing it won't leak -[2][6]. 

Fine-Tuning Workflow Management: Admins oversee the two modes of fine-tuning: Turnkey vs. White-Glove. In Turnkey (the standard self-serve mode), the Business Analyst handles everything in Copilot Studio. The admin's job is primarily to ensure that user has the proper license and permission, and that the necessary data sources (like SharePoint sites or connectors) are available for selection[8]. In the White-Glove scenario (a special program where Microsoft engineers assist with custom AI needs), admins coordinate with Microsoft's team and provide necessary approvals or data access for deeper engagement[8]. In both cases, admins might need to configure which data sources are allowed for fine-tuning - for example, they may approve certain SharePoint repositories or enable Graph connectors to specific external systems as needed. 

Deployment and Monitoring: Once a model is fine-tuned and ready, it gets deployed as a Copilot Declarative Agent accessible to end-users (e.g., appearing in the Copilot interface or Teams). Administrators ensure the deployment targets are correct - perhaps only a particular group should see the new agent. They can use security groups to control agent availability[6]. Admins also have the ability to monitor usage: through telemetry or reports, they can see how often the custom Copilot is used, by whom, and even measure its performance or impact (for example, via Copilot usage analytics dashboards)[3]. This helps in demonstrating ROI and ensuring the AI is providing value. 

Safeguarding Responsible Use: As with any AI rollout, admins maintain oversight to prevent misuse. Microsoft provides auditing and logging for Copilot interactions; admins can retrieve logs of prompts and responses if needed (for compliance or debugging)[6]. They can also configure Communication Compliance policies to detect if any sensitive info is being inappropriately asked or shared via Copilot[7]. Essentially, the Administrator acts as the gatekeeper so that Copilot Tuning is used in a secure, compliant, and well-governed way across the organization.

Security features and compliance notes: Administrators should be aware of the robust security built into Copilot Tuning: all fine-tuning occurs within your tenant's trusted boundary, so the training data and the model never leave your tenant[2]. The model produced is treated as customer data - it's stored and served within your tenant. Moreover, Copilot's responses will honor document permissions: if a user asks the agent something that involves data they don't have access to, Copilot will not reveal it (this is because the model is linked with your Microsoft Graph security model)[2]. Microsoft's Responsible AI principles are also applied - for example, there are content filters to avoid inappropriate outputs, and admins can further configure these settings in the admin center. Finally, any data output by the agent can inherit sensitivity labels (via Microsoft Purview) just like normal documents, and retention policies can apply to content generated by Copilot[6]. In short, Copilot Tuning extends your organization's security and compliance envelope into the AI realm, under admin control.

Tips and best practices for Administrators: 

Check License and Eligibility: Copilot Tuning is an add-on for organizations with Microsoft 365 Copilot. Ensure your tenant meets any preview or program requirements (for early access programs, Microsoft may require a certain number of Copilot licenses, etc.)[2]. Only enable Copilot Tuning for users who are properly licensed and trained in its use. 

Configure Roles Carefully: When you enable Copilot Tuning, thoughtfully assign the "Model Maker" (Business Analyst) role to those who will fine-tune models, and limit it to the right people. Likewise, determine which users can create agents from those models (in many cases, the same people or a subset). By using Azure security groups or a similar mechanism, you can manage these permissions at scale[6]. For example, a group "Copilot Tuning Users" for those allowed to consume or deploy the agents. 

Start Small and Expand: It's wise to pilot Copilot Tuning with a specific department or scenario first. Enable the feature for a small group of users and closely monitor the process. Evaluate the outcomes and gather feedback from the Business Analyst and a sample of end-users. Once you're confident in the governance and value, you can scale up to more teams or enterprise-wide. 

Review Data Sources: As an admin, you might need to assist in connecting data sources. Ensure that the content needed for fine-tuning is available and accessible. For instance, if an analyst needs to fine-tune using a file share outside of M365, consider ingesting that data into SharePoint or using a Graph Connector if available. Also, put guardrails: maybe exclude highly confidential libraries from being used in training if that's a concern. You have control to allow or restrict what data can be mined for AI training. 



Educate and Support: Provide training to Business Analysts and Information Workers on your company's AI policies. Make sure they know what types of data are approved for use, and how to handle any sensitive information. Encourage them to come to you if they are unsure about a dataset. Also, stay informed via Microsoft's documentation on any new admin controls for Copilot - Microsoft may release updates that allow even finer control (for example, to set cost budgets, or to review training content before it's processed). 

By following these practices, Administrators can maintain a secure and well-governed Copilot Tuning environment. In effect, the Administrator's role is to empower the business to get the most out of AI, while ensuring that all usage aligns with IT policies and regulatory obligations. With the admin's oversight, Business Analysts and Information Workers can confidently innovate, knowing the necessary safety nets are in place. The collaboration between IT and business here is key - Admins provide the platform and guardrails, and the business provides the knowledge to train the AI. Together, they bring about trustworthy, enterprise-ready Copilot agents.

## Use agents tuned on AI models

"Information Makers" refers to the people who actually put the fine-tuned models to work in day-to-day operations. In many cases, these are Information Workers or power users in a department who take a fine-tuned model (created via Copilot Tuning) and deploy it as a Copilot agent for others to use. They might also be the end-users themselves interacting with the agent. Essentially, this role covers those who configure, use, and benefit from the custom AI agents in their workflows. An Information Worker might be, for example, an HR specialist setting up an "HR Policy Assistant" Copilot for all employees, or a project manager using a "Project Summary Agent" to quickly get updates. They are the bridge between the AI capabilities and everyday business tasks.

How Information Workers leverage Copilot Tuning: 

Deploying Declarative Agents: Once a model is fine-tuned by a Business Analyst, an Information Worker can create a Declarative Agent in Microsoft 365 Copilot Studio using that model[1]. This involves going into Copilot Studio's agent builder, which is a user-friendly tool to configure custom Copilot . The Information Worker would select the available fine-tuned model from a list (for example, the "HR Policy Q&A Model" that was prepared)[1], and then configure the agent's settings. They give the agent a name, a brief description, and possibly an icon - essentially defining how it will appear to end-users. They can also write instructions for the agent's behavior (e.g. "This HR answers questions about company HR policies and should always be polite and concise."). Finally, they hit "Create" - the studio then deploys the agent. In a matter of seconds, the agent becomes available for use, for example in the Teams Copilot interface or other Copilot entry points within Microsoft 365[1]. 

Configuring Conversation Experience: Information Workers also define the initial experience of the agent. They can provide starter prompts or example questions to guide users on what to ask. For instance, when deploying an agent, the creator might input a few sample queries like "How do I update my healthcare plan?" to show end-users the agent's purpose[1]. They also ensure the agent's tone and style align with the context - if it's an internal bot for finance data, maybe it should output detailed numeric answers; if it's a help bot, maybe brief answers with links are better. Copilot Tuning allows these configurations without any coding - all through form fields and options in Copilot Studio. 

Sharing the Agent with Users: By default, a newly created agent might only be visible to its creator or a small group. Information Workers can publish or share the agent with a broader audience once ready[1].. 

Using the Copilot Agent in Workflows: After deployment, Information Workers (and their colleagues) will interact with the agent as they would with any Copilot feature - typically via a chat interface in Teams, the Copilot app. They can ask natural language questions or give commands, and the agent responds with the fine-tuned intelligence. For example, an employee opens Teams, goes to the Copilot chat and sees the HR Policy Assistant listed; they type "What is our parental leave policy?" - the agent, drawing on the fine-tuned model, answers with the exact details from the HR handbook, and even cites the handbook if configured to do so[2]. This delivers immediate, accurate information, saving time for both the employee and the HR team. 

Automating Tasks: In some cases, these custom agents can go beyond Q&A. They might automate a task. For instance, an Information Worker could combine the fine-tuned model with Power Automate flows or other actions in Copilot Studio (if they have advanced skills)[4]. Imagine a "Project Status Agent" that not only answers project metrics questions but also, when asked, goes and updates an Azure DevOps board via an action. While this is an advanced scenario, the Copilot framework supports such extensions. The key point is that Information Workers can orchestrate multi-step workflows with their agent, turning it into a mini-application for their needs, all using natural language configurations in Copilot Studio[4]. 

Benefits for Information Workers: 

Increased Productivity: The custom Copilot agents act as intelligent assistants in daily work. Employees can get instant answers or generate content without searching through documents or waiting on colleagues. For example, a new team member can ask the "Onboarding Copilot" a series of questions instead of emailing HR multiple times. This self-service ability frees up experts (HR, IT, finance, etc.) from routine queries[1] and lets employees help themselves 24/7. 

Consistency and Accuracy: Because the answers and outputs come from a fine-tuned model using verified company data, the responses are consistent and authoritative. An Information Worker using the agent can trust that, for instance, the sales figures or policy details provided are up-to-date and vetted. This reduces errors that might occur if employees use outdated documents or external search engines. Essentially, the agent becomes a single source of truth for the topic it covers. 

Speed in Complex Tasks: An Information Worker can accomplish complex tasks much faster. Consider an analyst who needs to prepare a summary of a legal case: with an appropriate agent, they could get a first draft of the summary in seconds, pulled from multiple internal sources, which they can then refine. What used to involve skimming dozens of files is now accelerated by AI. This speed advantage applies to many scenarios - summarizing lengthy reports, extracting trends from data, drafting communications, and more. 

Empowerment to Create Solutions: Copilot Tuning empowers non-developers to create AI-powered solutions for their team. In the past, building a custom bot or app might require developer resources and weeks of work. Now, an Information Worker with knowledge of the need can configure a Copilot agent in a afternoon. This democratizes solution-building: the people who face the problem can solve it directly with AI, rather than submitting IT requests. It fosters a culture of innovation, where Information Workers become "makers" of their own mini-apps (hence the term Information Maker). 

Improved Collaboration: With these Copilot agents available, team collaboration improves. Colleagues rely on the agent as a collaborative tool - for example, in a meeting a team might ask the Project Status agent to provide the latest figures, avoiding the need to guess or defer the question. It's like having an expert always in the room. Moreover, the existence of the agent means the knowledge of one expert (say the Business Analyst who trained it) is now shared and available to all in the team. This levels up the whole group's capability and ensures knowledge silos are broken down.

Best practices for Information Workers using Copilot Tuning agents: 

Understand the Model's Scope: As an Information Worker deploying or using an agent, know what data and task the agent is based on. Was it trained on HR documents up to 2022? Is it meant only for summarizing certain reports? Knowing the scope will help you ask the right questions and not expect it to do unrelated tasks. The Business Analyst or admin will usually provide documentation or a brief description of the agent's purpose - read that carefully. 

Provide Clear Prompts: When interacting with the agent, ask clear, specific questions if possible. Though the model is fine-tuned, phrasing your query well will yield better results. For example, instead of asking "Tell me about benefits," ask "What is the maternity leave policy for full-time employees?" This ensures the AI pulls the precise info. The fine-tuned agent is designed to handle complex queries, but clarity helps it focus. 

Use the Agent's Guidance: Many custom agents will come with starter prompts or suggested questions (often displayed in the Copilot interface when you open the agent). Leverage those! They often demonstrate the agent's capabilities. For instance, a Finance Report agent might suggest "Ask me to generate a Q3 budget vs. actuals summary." By using these suggestions, you'll quickly learn the range of what the agent can do. 

Don't Hesitate to Iterate: If the agent's response isn't exactly what you need, try refining your prompt or ask follow-up questions. These agents support multi-turn conversations. You might say, "Thanks, can you also include the latest data from October?" or "Please make the summary shorter." The fine-tuned Copilot will incorporate the follow-up and adjust the answer. Iteration helps you get to the precise output you want. 

Maintain Security Hygiene: Even though the Copilot agent will enforce permissions, you as a user should still treat it as you would any internal tool. Don't ask it to divulge information you wouldn't otherwise be allowed to see. And be mindful of where you share the answers it gives. If you copy an answer containing confidential info, handle it with the same care as the original documents. Essentially, normal company data policies apply. 

Provide Feedback: Many Copilot agents have a feedback mechanism (like a thumbs-up/down or an option to flag a wrong answer). Use it. If the agent gave an incorrect or strange answer, provide that feedback. Your feedback can lead to retraining or tweaking the agent for better performance. In some configurations, feedback can be collected right in the Copilot Studio for the model owner to see[1]. By voicing what the agent got right or wrong, you contribute to its continuous improvement. 

By following these best practices, Information Workers can fully harness the power of Copilot Tuning agents. They essentially get a personal assistant specialized in their organization - boosting productivity and enabling smarter work. Over time, as more agents are created and adopted, employees will spend less time hunting for information or doing menial data compilation, and more time on creative, strategic work. 



Collaboration and Integration Across Roles

Copilot Tuning introduces a new way for IT and business roles to collaborate: Business Analysts, Administrators, and Information Workers each bring their strengths to the table, and the outcome is a powerful AI assistant tailored to the organization. This collaboration can significantly enhance knowledge sharing and efficiency: 

Business Analysts encode tacit knowledge into the AI, making it accessible to everyone. This means tribal knowledge or specialized expertise is no longer siloed - the Copilot agent can disseminate it on demand. 

Administrators ensure the solution is delivered in a secure, managed way, building trust in the AI. Users know that the answers they get comply with company policies. IT and security teams, in turn, gain visibility into how corporate knowledge is used, which can inform compliance reporting or future training needs. 

Information Workers leverage the AI in everyday scenarios, providing real-world feedback and new ideas for improvement. They might discover additional use cases for Copilot, driving further innovation (for example, an employee finds that the HR bot could be expanded to handle onboarding tasks, and communicates that back to the team). 

The synergy of these roles essentially creates a virtuous cycle: Admins empower analysts with the tools; analysts create models to empower employees; employees use them and deliver feedback; admins and analysts then refine and expand the AI capabilities. This cross-functional loop can speed up digital transformation efforts, as AI becomes a co-pilot in many processes. Furthermore, Copilot Tuning's integration with the Microsoft 365 ecosystem means it fits naturally into existing workflows, and they draw from the data stored in Microsoft 365 (SharePoint, OneDrive, Exchange)[2]. It's not a separate siloed tool - it's woven into the fabric of work, which encourages adoption and continuous collaboration among stakeholders.


## Conclusion

Copilot Tuning provides a comprehensive, user-friendly way to customize AI for your tenant. Business Analysts, Administrators, and Information Workers each have tailored tools and clear roles in this journey: from model creation to deployment to utilization. By collaborating, they can deliver an AI experience that feels like it was "made just for us" - because it literally was, using your organization's own knowledge. The outcome is faster answers, smarter automation, and employees who can focus on high-value work with a trusty Copilot at their side. With strong governance and iterative improvements, Copilot Tuning can continuously adapt to your business, becoming an increasingly invaluable teammate for everyone. 
