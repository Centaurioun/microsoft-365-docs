---
ms.topic: troubleshooting
title: Troubleshoot MAC Task Fine Tuning FAQ
---

# Troubleshoot MAC Task Fine Tuning FAQ

This article addresses common questions that arise when engaging in MAC for Task Fine Tuning. It covers answers to concerns such as missing task-specific models in the settings, eligibility requirements for seeing Copilot models, delays in setup, managing user access, and handling errors related to insufficient data, inaccessible links, validation problems, and security group coverage.

This article also includes a pattern to help you write other troubleshooting articles. This pattern includes standard information for Microsoft troubleshooting articles from the document creation perspective.

### Prerequisites

Before you engage in troubleshooting, ensure that you have verified prerequisites such as licenses and permissions. Make sure you have at least 5,000 Copilot Licenses as required.

### Potential Quick Workarounds

If you are experiencing any problems that can be temporarily resolved with a quick fix, list those workarounds here. You should also link to a possible standard solution in the solution section of this article. In some cases, you may be experiencing issues related to licenses or permission settings. You can troubleshoot the issue by:

- Understanding which task-specific models are missing from your settings in relation to licensing and the prerequisites for this feature.

- Checking the initial screen for eligibility if you are unable to see task-specific Copilot models.

### Troubleshooting Checklist

In this section, you can define steps that people can take if known action items can be performed to know why the issue is happening.

For example, certain errors display an error screen that explains why admins are unable to see task-specific Copilot models because of eligibility.

If you are experiencing any errors during configuration or setup of the feature, follow the steps below to troubleshoot:

1. Verify the prerequisites of licenses.
2. Check configurations and settings.
3. Check connectivity of data to base knowledge sources.
4. Validate configuration requirements: Ensure you have completed all required fields in the validation screen.
5. Check security group coverage.

### Causes and/or Solutions

Define the cause of the issue if it's known. If the problem is correctable, include one or more solutions.

There can be multiple possible causes for an issue such as:

- Insufficient data for training where not all links can be accessed.
- Validation errors occur when you haven't completed all required fields.
- Security group coverage errors occur when you are unable to adjust security groups because they are missing or empty.

Potential solutions to troubleshoot your issue include:

### Troubleshooting Checklist

Follow these guidelines to assess the remediations. Refer to the detailed guidelines below:

- Verify prerequisites of missing prerequisites such as licenses or permissions.
- Check for eligibility issues to ensure you have the correct licenses.

### Solution

Ensure to provide solution steps with a description of the solution that explains the steps users will be taking to solve their issue.

- Delayed setup and contact support if taking more than 1 hour
- Manage user access and email invitations to users
- Deletion of model is irreversible

### Advanced Troubleshooting and Data Collection

This section can include advanced troubleshooting and data collection steps to help people submit a support ticket.

- Delayed setup and contact support if taking more than 1 hour
- Manage user access and email invitations to users.
- Data validation errors occur when you haven't completed all required fields

### Related Content

[Placeholder for related articles and additional resources]


# Troubleshooting Article Pattern

Use this pattern to write an article that addresses specific issues and follows a standard format in the documentation.

## Troubleshooting Article Formatting

### Headline Requirements

1. The headline is formatted as "Troubleshoot <problem>"
2. Avoid using "errors" or "issues" in the title.
3. This headline is set as the H1 at the top of the article.
4. The headline should match the `ms.topic attribute` as **troubleshooting**.
5. Choose the best headline that matches the information topic.

### Introductory Paragraphs

1. The introductory paragraphs of the article don't include a heading.
2. Write concise paragraphs with a brief introduction to the issue being covered.
3. There might be scenarios where you can list more than one issue in a troubleshooting article.

### Metadata Requirements

Use the proper metadata for troubleshooting articles:

1. As mentioned earlier, the `ms.topic` metadata should be **troubleshooting** or **troubleshooting-general**.
2. Ensure to have metadata attributes and information about title, author, description, and search attributes.
   **Troubleshooting articles should always have metadata that includes title and description.**

### Content Fields and Definitions

#### Problem-Solution Format

The article uses a problem-solution format with the solution split from the problem statement.

#### Introductory Paragraphs

1. First, use plain text. The introductory paragraphs should be visible at the beginning of the article after the metadata.
2. Clearly state the issue or problem as the first H2 heading in the article.
3. The H2 section should be created using the Markdown syntax:

```md
## Troubleshoot <problem>
```

Make sure ## aligns with the heading tag that creates an H2 formatted heading.

Examples of Introductory Paragraphs:

- Use an introductory paragraph that briefly explains what the issue is about and what users should do as they work through this issue.
- Avoid explaining the solution within the introductory paragraph of the body content without having a proper **troubleshooting step heading** or **solution heading** within the article.
 - The below example keeps the introductory paragraph on its own, using concise language and introducing the issue without having the way of implementing this solution within the first few sentences.

example #example, /example, and #example are both examples of introductory paragraphs.

#### FAQ Troubleshooting Example

The FAQ example represents an example activity (without full explanation) that could be defined within a solution heading. This introduction should not be combined with the main explanation of the issue (e.g. why a task-specific model is missing). The FAQ solution steps of this example are formatted in other parts of this article writing troubleshooting activity guidelines.

1. Example Introduction:
     - Task-specific models missing from settings - missing licenses (admin can't see models).

2. Example Solution Heading:
```#### Check configuration settings for missing prerequisites
```

3. Example Solution Steps:
```md
1. To determine why you are unable to see task-specific Copilot models, you can examine your eligibility by clicking the example.
```

#### Troubleshooting Section

1. The main H2 introduction should use a consistent heading named **troubleshooting**. This H2 heading name should be added between each instance of HTML headings used for defining each issue covered in an article.
2. A set of structured steps should accompany the H2 heading names of **troubleshooting**.
3. Use consistent language for each issue, such as referring to the problem by its name, explaining the issue using concise language, or including an example in the form of a sentence that would refer back to the opening sentences.

Examples of the Troubleshooting Statements:

1. Examples that need detailed steps can contain steps or blocks of text that have content listed after or based on the example steps introduced within a specific article.

      - The examples should be ordered in a logical way that represents each step needed to solve some of the specific issues found within an article. For example, multiple steps shown above can explain some of these specific examples that need more elaborate steps to resolve some of the problems or to define each issue within an article.
         examples: #example, #example, #example, #example, #example, #example, and #example.
         examples: If your example is configured to example, you can verify example, you can perform a test example, you can example the example,
         examples: If your example is configured to example, you must example the example example, you must agree on example, you must send email example,
         examples: To troubleshoot example, you can example your example to example, you can perform a test example, you can example the example,

2. Examples that don't need detailed steps can contain steps or blocks of text that have content listed after or based on the example steps defined within a specific article.
    - The examples should be ordered in a somewhat logical way, or contain a difference in emphasis on certain pieces of information. For example, multiple steps can only cover some portions of an example for explaining detailed steps for defining each issue found within an article.
      Examples: #example and #example.

##### Solutions Section

#### Define the Cause and Solution Steps

If a certain cause is known, it's important to include this within the troubleshooting article.

1. The main H2 introduction should use a consistent heading named **causes**. This introduction should use a consistent heading name for each issue covered in an article.
2. The H3 solution heading name should use the consistent pattern is defined within this section of this pattern. Follow the pattern that provides an example headline that should start with a headline name named **solutions**, and refer back to the name of the H2 headline that's needed within an article.
3. Each issue found within the troubleshooting article should include detailed solution steps that should have content listed below the solution heading. Make sure each of these solutions should include a sentence that refers back to the solution steps found within this section of this pattern.
4. The solutions in this section are formatted as snippets for writing troubleshooting articles based on some of these examples. Refer to the structured snippet of each solution and follow its structure and pattern.

Examples of the Solution Steps:

1. Example Troubleshooting FAQ found within common errors
     - You must assign or create a security group name appropriate for the example purpose.
     - You must assign or add example users to the individual example of multiple-centered security grouping.
     - You must attach assigned example group to example area or applicable section within example security group setup procedure steps.
     - You must have at least 5,000 examples as required prerequisites permissions purposes
     - You must select configured example model using selected option found within applicable organization screen of main page settings option, this can be checked or unselected depending on which suited purpose.

Examples of the Solution Headings:

1. The FAQ Example should use this heading. This can be exported based on opening examples. The pattern should follow examples defined towards the top of the FAQ Example pattern snippet of this guide.
- You can build out all the solution steps that refer back to the single opening examples of this snippet for the writing troubleshooting examples based for common errors.

#### Common Errors Guidelines

Common errors can appear within the Markdown section of the article writing troubleshooting guideline. Consult the steps that explain common errors in this document before writing an article pattern explanation.

1. See if there's an error or a combination of errors.
2. Use consistent solution steps that follow the pattern definition.
3. See if there's a method that can be tested for this specific error.


Common Error Example:

**Example Check Configuration Settings for the Security Group Guidelines**

1. Check configuration settings for the example name
    If your example is configured to the example name, you must create the appropriate example name as the step example.

**Example Check for Eligibility Issues**

1. Check for eligibility issues
   To troubleshoot example, you must attach assigned security group to example name as the step example.

**Example Solution Steps**

     EXAMPLES: Example Security Group and Permissions Troubleshooting, Example Check Configuration Settings & Missing Prerequisites>>>Job Title>Explorer Explorer User Progress Organization Explorer User Training Explorer Site Certification Explorer Management Explorer User Leader Explorer Analyst Explorer User Training Explorer Site Explorer Leader Management Explorer Assignment Explorer Navigator Explorer Management This Orchestra Next Orchestra Music Hall Expansion Orchestra User Explorer Leader Organization Explorer User Example Management Explorer Site Organization Explorer Intermediate Leadership GCC Explorer Explorer User Explorer Site Explorer Leader Management Explorer Assignment Explorer Navigator Explorer Management
