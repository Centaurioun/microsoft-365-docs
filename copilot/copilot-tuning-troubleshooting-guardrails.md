
---
recommendations: false
ms.topic: troubleshooting-general
description: FAQ and troubleshooting guide for Tenant Guardrail issues, including false positives, negatives, duplicate alerts, and overall system response issues.
---


# FAQ for Tenant Guardrails

Use the following FAQ approach when addressing issues with Tenant Guardrails.

- **The system crashed, froze, or became unresponsive:**
  - Contact Microsoft support or your IT administrator—this is a technical problem that cannot be fixed by the user.
- **I see an error message when processing guardrails in Tenant Guardrails (guardrails analysis):**
  - If it's an AI model error (for example Language Model API error), retry the analysis.
  - If the error persists, retry and then escalate—Contact Microsoft support or your IT administrator.
- **The guardrails are not flagging the issues I am concerned about (misses critical errors):**
  - Broaden the criteria in the guardrails rules. Add additional rules for key issues.
- **The guardrails are flagging things that are not of concern (emits false positives):**
  - Refine the criteria in the guardrails rules.
- **I am seeing duplicate alerts for the same issue:**
  - Adjust frequency and sensitivity. Test guardrails rules thoroughly before deploying to end users. Consider using initial testing in test environments.


## Prerequisites

Before attempting to resolve any issues, make sure that you have the proper configurations and conditions. This includes ensuring that your guardrail rules are correctly set up and that your system meets the necessary requirements for running guardrails. If you are experiencing a system crash, freeze, or unresponsiveness, check if your tenant is correctly set up.


## Potential Quick Workarounds

For transient issues, like temporary system freezes and AI-related error messages during guardrails analysis, the first step is to retry the action. If the problem persists, it's recommended to follow the troubleshooting checklist or escalate the issue by contacting Microsoft support or your IT administrator.


## Troubleshooting Guidance

Use the following guidance when attempting to resolve issues related to Tenant Guardrails:

- **Verify the symptoms**:
  - Is the system crashed, frozen, or unresponsive?
  - Is there an error message displayed while processing guardrails in Tenant Guardrails (guardrails analysis)?
- **Initial steps**:
  - Review any related documentation, guides or common troubleshooting tips to ensure steps and configurations are correctly followed.
- **Escalate**:
  - Contact Microsoft support or your IT administrator if you're unable to resolve the issues.


## Causes and/or solutions

Causes can vary based on observed symptoms. For example, false positives and negatives can occur because the guardrail rules have been misconfigured. Duplicate alerts can appear if overlapping rules have been set. Identifying the causes of issues often centers around refining the criteria for your guardrail rules and adjusting the configurations.

If you're unable to resolve your problems, you can escalate issues to Microsoft Support or the Tenant Copilot product team.

For issues where the guardrails don't flag specific types of content or flag too much, evaluate if the guardrail rules are correctly designed. Frequently, refining the criteria or broadening it can rectify these problems.

### Solution

- **Refining guardrails criteria**:
  - Ensure you use precise language and detailed conditions in your rules.
  - Include examples and illustrative content for clarity.
  - Use AND and OR grouping for conditions within rules to make them more relevant to different types of audiences.

- **Broadening criteria**:
  - Identify key issues and add rules that are specific to those concerns.
  - Test rules before deploying to production to ensure accuracy.

- **Handling duplicates**:
  - Identify overlapping conditions across rules.
  - Consolidate rules where possible to minimize overlap.
  - Configure threshold to control sensitivity of flags or alerts when available (editing capability to threshold coming soon).

If issues persist after troubleshooting, escalate to Microsoft support or the Tenant Copilot product team.


## In-Depth Analysis and Data Collection

For issues that don't resolve through initial troubleshooting, thorough analysis or extra data collection may be required. This might involve diving deeper into error messages or logs to figure out the underlying problem. In persistent cases, consider contacting Microsoft support or your IT administrator.


## Related Content

[Placeholder for related articles and resources content.]
