---
name: infocert-send-certified-email
description: Send a Legalmail certified email (PEC) from a business mailbox and track
  its acceptance and delivery receipts.
api: openapi/infocert-legalmail-business-mailboxes-openapi.yml
operations:
- listMailboxes
- getMailbox
- sendMessage
- createSubmission
- getSubmissionStatus
- searchSubmissions
generated: '2026-10-18'
method: generated
---

# Send Certified Email

Send a Legalmail certified email (PEC) from a business mailbox and track its acceptance and delivery receipts.

Spec: `openapi/infocert-legalmail-business-mailboxes-openapi.yml` (LegalMail Business API - Mailboxes). Security schemes declared: busapiv2_mailboxes_oauth2 (oauth2).

## Steps

1. `listMailboxes` — `GET /` — listMailboxes
2. `getMailbox` — `GET /{mailboxId}` — getMailbox
3. `sendMessage` — `POST /{mailboxId}/send` — sendMessage
4. `createSubmission` — `POST /{mailboxId}/submissions` — createSubmission, send a new registered message
5. `getSubmissionStatus` — `GET /{mailboxId}/submissions/{submissionId}/status` — getSubmissionStatus, know the acceptance and consignment of a given submission
6. `searchSubmissions` — `GET /{mailboxId}/submissions` — searchSubmissions

## Rules

- Only call the operations listed above; inputs are defined by each operation's parameters and requestBody in the spec.
- The spec does not document idempotency keys: do not blindly retry create/send operations — check status first.
- InfoCert services are qualified trust services (eIDAS); calls create legally relevant evidence, so confirm intent with the user before sending, signing or preserving.
