
---
title: " Troubleshoot Tenant Guardrails"
ms.topic: troubleshooting-general
description: FAQ and troubleshooting guide for Tenant Guardrail issues, including false positives, negatives, duplicate alerts, and overall system response issues.
---


# Troubleshoot Tenant Guardrails

This article describes some of the most common issues with Tenant Guardrails and how to troubleshoot them.

## The system crashed, froze, or became unresponsive

Contact Microsoft support or your IT administrator—this is a technical problem that cannot be fixed by the user.

## I see an error message when processing guardrails in Tenant Guardrails (guardrails analysis)

If it's an AI model error (for example, Language Model API error), retry the analysis. If the error persists, retry and then escalate—Contact Microsoft support or your IT administrator.

## The guardrails are not flagging the issues I am concerned about (misses critical errors)

Broaden the criteria in the guardrails rules. Add additional rules for key issues.

## The guardrails are flagging things that are not of concern (emits false positives)

Refine the criteria in the guardrails rules. To refine the guardrails criteria effectively, follow these steps:

1. Ensure you use precise language and detailed conditions in your rules. 
2. Include examples and illustrative content for clarity.
3. Use AND and OR grouping for conditions within rules to make them more relevant to different types of audiences.

## I am seeing duplicate alerts for the same issue

Adjust frequency and sensitivity. Test guardrails rules thoroughly before deploying to end users. Consider using initial testing in test environments.

## I need to broaden the criteria

To broaden the criteria, follow these steps:

   1. Identify key issues.
   2. Add rules that are specific to those concerns.
   3. Test rules before deploying to production to ensure accuracy.

## I need to handle duplicates

  1. Identify overlapping conditions across rules.
  2. Consolidate rules where possible to minimize overlap.
  3. Configure threshold to control sensitivity of flags or alerts when available (editing capability to threshold coming soon).

If issues persist after troubleshooting, escalate to Microsoft support or the Tenant Copilot product team.

## Related Content
- **Escalate**:
  - Contact Microsoft support or your IT administrator if you're unable to resolve the issues.



[Placeholder for related articles and resources content.]
