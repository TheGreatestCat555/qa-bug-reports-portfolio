# CHATGPT-CODEX-001 Assistant stops at a public login redirect before retrieving available project context

> **Status:** Draft

## Summary

In a new Codex conversation using the same local project as an earlier task, the assistant treated a public ChatGPT project link's login redirect as sufficient reason to stop. It asked the user to paste content without first checking the available conversation-history tools. After the user corrected the response, those tools successfully retrieved the previous task and conversations associated with the project.

## Product and platform

- Product: Codex, ChatGPT conversation retrieval
- Platform: Windows workspace; exact client build not recorded
- Language: Russian requested after the first response
- Observation date: 2026-10-01
- Browser session: the in-app browser subsequently showed a login page; access through another browser was not established

## Preconditions

- An earlier conversation in the same local workspace contains a workflow for analyzing ChatGPT links and saving project ideas locally.
- A new conversation is started to continue work with a shorter context.
- Conversation-history tools can retrieve the earlier task and relevant ChatGPT conversations.

## Steps to reproduce

1. Start a new conversation in the existing project workspace.
2. Send a private ChatGPT project URL previously processed in the earlier conversation.
3. Observe the assistant's initial access check and response.
4. Tell the assistant to recover the previous task context and examine available access paths.
5. Compare the initial refusal with the subsequent successful conversation retrieval.

## Actual result

The assistant used public web access, received a login redirect, and said it could not read the project contents through the link. It then asked the user what to do and requested pasted text or files. It did not inspect the earlier task or available conversation retrieval before returning that response.

After correction, the earlier task and seven relevant conversations were retrieved through the application's tools. The new task could continue without the user pasting the source material.

## Expected result

Before concluding that the requested source cannot be processed, inspect the available project context and authorized retrieval paths. When the previous workflow is recoverable, continue it and report the actual limits of the available source. Distinguish a public web login redirect from the availability of conversation-history access.

## Reproducibility

One observed sequence. No controlled repeated trials. The user reports similar work in the earlier conversation; that does not establish the frequency of this defect.

## Severity

Medium candidate — recoverable interruption of an existing workflow, requiring the user to repeat context and correct an unsupported access conclusion.

## Priority

To be assessed — frequency and behavior across fresh conversations and clients remain unmeasured.

## Category

Conversation Context / Tool Selection / Error Handling / Workflow Continuity

## Evidence

- Initial response and subsequent recovery are recorded in the private source conversation.
- Subsequent tool results confirm successful retrieval of the earlier task and relevant conversations.
- Public screenshots, video and sanitized conversation export: not available.
- Private project identifiers, conversation identifiers and local personal paths are deliberately excluded from this report.

## Notes and follow-up

The observation establishes a premature tool-selection and context-retrieval failure. It does not establish a defect in browser authentication or a requirement that every new conversation automatically inherit the full history of adjacent conversations. The browser available during recovery was not authenticated to the source page.

Repeat with a controlled private project, a known prior workflow, and available history tools. Record which retrieval options are exposed, whether they are attempted, and whether the user must supply context again. Keep this report as Draft until independent reproduction and publishable evidence are available.
