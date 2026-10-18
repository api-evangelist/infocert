---
name: infocert-send-message
description: Send a message through various Infocert messaging channels.
api: openapi/infocert-legalmail-business-mailboxes-openapi.yml
operations:
- sendMessage
- createSubmission
- sendMessageMIME
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/infocert-legalmail-business-mailboxes-openapi.yml ; every operationId checked against the contract
---

# infocert-send-message

Send a message through various Infocert messaging channels.

## Steps

1. 1. Send a standard message using `sendMessage` with the mailboxId path parameter and message content in the request body
2. 2. Send a registered message using `createSubmission` with the mailboxId path parameter and submission details in the request body
3. 3. Send a MIME-formatted message using `sendMessageMIME` with the mailboxId path parameter and MIME content in the request body

## Rules

- Authentication requires APIKeyAuth with X-InfoCert-GS-APIKey header
- All operations require mailboxId path parameter
- Multiple authentication schemes available including oauth2, BasicAuth, and BearerAuth
