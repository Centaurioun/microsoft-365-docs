---
title: "Troubleshoot issues for the Copilot Tuning EXpert Q&A model FAQ"
author: jasonjoh
ms.author: jasonjoh
manager: calvind
ms.date: 06/10/2025
audience: Admin
ms.topic: troubleshooting-general
ms.reviewer: calvind
ms.localizationpriority: medium
recommendations: false
---

# Troubleshoot issues for the Copilot Tuning Expert Q&A model FAQ

This article describes some of the most common issues with the Microsoft Admin Center task fine-tuning FAQ and how to troubleshoot them.


Setup and Access Issues

## I get a permission or access error when connecting to my content source (e.g. a SharePoint site)

An access or permission denied" error usually means your account doesn't have the rights to that data source. Make sure you have the appropriate permissions to the content repository[1]. For example, if adding a SharePoint site, confirm with your SharePoint administrator that your account (or a group you belong to) has access to that site or document library. If the fine-tuning process uses a Security Group for access control, ensure that the correct security group is set up and that your user account is included in it[1] before retrying the operation.

## I created a fine-tuned Q&A model, but it isn't showing up when I try to add it to my Copilot agent

If your newly trained model isn't listed in the selection dropdown while configuring the agent, it's likely a permissions issue. The model is associated with a security group or access policy, and your account might not be included. Ensure that the security group used during the model creation includes your account (the person building the agent)[1]. You may need to ask your IT admin to add you to that group or re-create the model with a group that you are part of. Once your permissions are fixed, the fine-tuned model should appear for selection.

## I clicked "Prepare data for training," but no labeling interface or data appeared

Not necessarily. Some fine-tuning scenarios do not require manual labeling of data[1]. In the Q&A fine-tuning pipeline, if the system doesn't present any data to label after preparation, it means that step is automatically skipped for your scenario. In other words, not all recipes require a labeling stage[1]. You can proceed to the next step of the process. (If you expected a labeling step but didn't get one, it could be that the system determined there's nothing to label, which is normal for certain Q&A tasks.)

## The "Processing data" stage is taking a very long time

The data preparation or training phase can take quite a while, depending on the size of your content. It's normal for this stage to take several hours[1], especially if you provided a large document collection. You should have received a notification (for example, an email) when the processing is complete. If you haven't received a notification yet, please be patient -- it likely means the process is still running. If it's been more than a few hours, check your spam or junk email folder to ensure the notification didn't get misfiled[1]. You can also manually refresh or revisit the fine-tuning page; once processing is done (even if an email was missed), the status on the site will indicate that the data is ready or the next step is available.

## I never got the email notification that my data processing is finished

First, double-check your email spam or junk folder for a message about the fine-tuning process being completed[1]. Sometimes automated notifications can be filtered out. If you don't find an email, don't worry --- you do not strictly need the email to proceed[1]. Go back to the fine-tuning interface and check the status of your model there. If the preparation step is completed, the interface will show that your data is ready for the next step (for example, ready for evaluation or ready to train). At that point, you can continue with the fine-tuning workflow even without having clicked an email link.

## The fine-tuning process *stalled or failed* partway through (I see an error status, or it stopped with no message)

If the training/fine-tuning process fails or hangs without a clear error message, it can be tricky because the system might not have provided feedback. (The current system has limited error handling, so occasionally it might just stop without a specific error code or explanation[1].) Here's what you can do:

Retry the process: In some cases, simply rerunning the fine-tuning process or restarting from the last step can resolve a transient issue. Make sure any configurations are set correctly and try again.

Check for known issues: See if any error message was logged or displayed. If an error code was given, follow any guidance associated with that code. Often, documentation or forums might have additional information for specific errors.

Contact support if the issue persists: If you consistently get a failure with no helpful information or no change after retrying, the best course is to reach out to Microsoft support for assistance[1]. Provide them with details of what you were doing when it stalled. Since the system might not show a descriptive error in these cases, support can help diagnose behind the scenes. (If the entire application or interface crashed, this is also a situation where you should contact support immediately.)[1]

## My evaluation (test) dataset came back empty, or I see *0 Q&A pairs* generated for evaluation

An empty evaluation file usually indicates that the system could not generate any Q&A samples from your content. One common reason is that the content collection you provided was too small or had no usable data[1]. In other words, the model didn't have enough material to create Q&A examples. To address this:

Verify your knowledge source content: Double-check that the documents or data source you selected actually contain the information you expect. If the content repository was empty or too limited, add more relevant documents and then rerun the fine-tuning process.

Run the process again: Once you've ensured the content is in place, try the "prepare data" or fine-tuning step again. This time, it may produce a set of Q&A pairs for evaluation.

If it's still empty, seek help: If, after adding content and retrying, you still get an empty evaluation or an empty training set, there might be an underlying issue. At that point, contact support for further assistance[1]. They might check if there were any filtering rules or errors that caused your data to be discarded. In rare cases, extremely strict filtering or all content being out-of-scope could result in no data; support can help identify if that happened.

## The model training finished, but the *answers it gives seem strange or irrelevant* ("weird")

If your fine-tuned Q&A model's responses are not making sense or seem unrelated to your domain, the culprit is often the training data quality or quantity. A model can only perform as well as the data it was trained on. Here are steps to troubleshoot a \"weird\" or low-quality model output:

1. Ensure sufficient training data: Check that the knowledge source you provided has enough useful content. If your content collection was very small or empty, the model may have essentially trained on nothing, resulting in effectively a "vanilla" or nonsense model[1]. Make sure you include enough documents or Q&A pairs covering the subject matter you expect the model to handle.
2. Provide relevant data: If the model's answers are off-topic, some of your training documents might not match the intended domain. For example, if you're building a finance Q&A bot but the content fed in was mostly generic or unrelated, the model won't have the right knowledge. Refine your content set to be more relevant to the expected questions.
3. Retrain after improvements: After adding more or better data, run the fine-tuning process again. Improving the dataset often leads to a direct improvement in answer quality.

If outputs are still poor: If you've done the above and the model's answers are still incorrect or incoherent, consider reaching out to support. There could be an edge-case issue with the fine-tuning pipeline itself. But in most cases, bolstering your training data (or adjusting the task instructions) should greatly improve the model's responses.

##  The model's evaluation answers looked good, but when I integrated it into an agent (the Copilot chat interface), the answers weren't as good (e.g. the tone or detail changed)

This is a known behavior. The fine-tuned model might perform well in the isolated evaluation, but the deployed Copilot agent's behavior can differ if the agent configuration doesn't fully carry over the model's nuances. In particular, the agent might need additional instructions to use the model effectively. To resolve this:

1. Compare evaluation vs. agent outputs: Identify what's missing or different. For example, maybe the evaluation answers had a friendly, empathetic tone that you liked, but the agent's answers feel more generic or terse.
2. Adjust the agent's instructions: In Copilot Studio (or wherever you configure the agent), add or refine the system instructions/prompts for the agent. Reinforce the qualities you want that you saw in the evaluation stage[1]. For instance, "Ensure responses are in an empathetic tone," or "Include the detailed steps if available," etc. This guides the agent to preserve those aspects.
3. Test again: After updating instructions, test the agent with the same questions. You should see the answers align more closely with the fine-tuned model's expected behavior. This iterative tuning of the agent is sometimes necessary to get the best results. (Essentially, the fine-tuned model provides the knowledge, and the agent's instructions shape how that knowledge is expressed. Both need to be in harmony.)

# The answers from my Q&A bot are still not what I expected -- some are inaccurate or not on point. How can I improve the results?\ A: If you find the overall answer quality unsatisfactory, you may need to refine your fine-tuning setup further. Consider these steps:

1. Improve or increase training data: Ensure that the dataset used for fine-tuning is high quality, relevant, and comprehensive for the domain of questions. If possible, add more examples or documents that cover the scope of queries you expect. A richer dataset can significantly improve the model's accuracy.
2. Refine the initial configuration (questionnaire/settings): During the model setup, you likely provided some initial instructions or filled out a form (sometimes referred to as a questionnaire about the domain and task). It's worth revisiting those inputs. Edit or refine the task description and settings to better guide the model[1]. For example, if you realize the model is answering at too high a level, make sure the instructions specify the desired depth or context.
3. Provide clear examples: If the system allows, give example Q&A pairs or further guidance. Some fine-tuning processes let you review or label data. Use that opportunity to teach the model what correct answers look like.
4. Iterate and test: Fine-tuning is often an iterative process. After making changes, retrain (or partially train if supported) and then test the Q&A agent again. Gradually, you can converge on better performance. Remember that open-ended or extremely complex questions might always be challenging, but the goal is to get the majority of expected queries answered well.

## Some answers from the Q&A Copilot not have any citations

In the current version of the system, not every answer will include a citation, even if it's pulling information from your content. The Q&A fine-tuning pipeline works in tandem with retrieval: when the answer comes directly from retrieved documents (using the RAG retrieval component), the system will show citation links. However, if the answer is coming from the fine-tuned model's own knowledge (for example, something it learned during training that isn't a direct quote from a document), it may respond without attaching a source citation[1]. This behavior is expected.

The presence of citations is generally a good sign that the answer used the documents you provided at runtime. Lack of a citation doesn't necessarily mean the answer is wrong; it might just mean the answer was generated from the model's internal knowledge or the question didn't require retrieving a document.

If you believe an answer should have a citation (for instance, it seems to be quoting a document you provided) but no citation is shown, double-check that your knowledge sources were properly connected during the agent's run. It's possible the agent answered from the fine-tuned model rather than the real document.

As the product evolves, citation features may be improved. For now, remember that an answer without a citation isn't unusual in some cases[1]. You can always verify critical information by manually searching your source content, and if you feel something is missing a citation or is incorrect, use the feedback mechanisms in the tool to let the developers know (for example, by reporting a bad answer through the interface).

## Related Content

[Placeholder for related content and resources.]
