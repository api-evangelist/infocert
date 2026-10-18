---
name: infocert-download-and-send-message
description: Download a message from a mailbox folder and send it to another recipient.
api: openapi/infocert-legalmail-business-openapi.yml
operations:
- fullyExplodedMessage
- rawMessageDownload
- sendMessage
- sendRawMessage
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/infocert-legalmail-business-openapi.yml ; every operationId checked against the contract
---

# infocert-download-and-send-message

Download a message from a mailbox folder and send it to another recipient.

## Steps

1. 1. Use `fullyExplodedMessage` with path parameters `mailboxId`, `folderId`, and `messageId` to download the fully exploded JSON version of a message.
2. 2. Use `rawMessageDownload` with path parameters `mailboxId`, `folderId`, and `messageId` to download the raw version of the same message.
3. 3. Use `sendMessage` with path parameter `mailboxId` and request body to send a new message.
4. 4. Use `sendRawMessage` with path parameter `mailboxId` and request body containing raw EML to send a raw message.

## Rules

- Authentication is required using one of the available auth schemes: APIKeyAuth (header X-InfoCert-GS-APIKey), oauth2, BasicAuth, BearerAuth, or others listed.
- All operations require specific path parameters: `mailboxId` for send operations, and `mailboxId`, `folderId`, and `messageId` for download operations.
- The API supports multiple server environments including production (https://api.infocert.digital/atum/v1) and staging/test environments.
- Send operations (`sendMessage` and `sendRawMessage`) use POST method and require request body content.
