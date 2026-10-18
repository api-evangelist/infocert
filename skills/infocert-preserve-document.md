---
name: infocert-preserve-document
description: Send a document to Safe LTA qualified long-term preservation, follow
  the ingestion and retrieve the deposit attestation and archived package.
api: openapi/infocert-safe-lta-business-openapi.yml
operations:
- preflightPreservation
- preservation
- getPreservationProcessByExternalRefId
- getPreservationProcess
- getDepositAttestation
- downloadAip
- searchArchiveAips
generated: '2026-10-18'
method: generated
---

# Preserve Document

Send a document to Safe LTA qualified long-term preservation, follow the ingestion and retrieve the deposit attestation and archived package.

Spec: `openapi/infocert-safe-lta-business-openapi.yml` (Safe LTA - Preservation & Archive - Business API). Security schemes declared: oauth2 (oauth2).

## Steps

1. `preflightPreservation` — `POST /safelta/business/v1/ingestions/companies/{company_title}/documentClasses/{document_class_title}/preflight` — Preflight Preservation
2. `preservation` — `POST /safelta/business/v1/ingestions/companies/{company_title}/documentClasses/{document_class_title}` — Preservation
3. `getPreservationProcessByExternalRefId` — `GET /safelta/core/v1/ingestions/extrefid/{ext_id}` — Get Preservation Process by External Ref ID (Strongly recommended)
4. `getPreservationProcess` — `GET /safelta/core/v1/ingestions/{sip_submission_id}` — Get Preservation process
5. `getDepositAttestation` — `GET /safelta/core/v1/documents/deposit-slip/{sip_submission_id}` — Get Deposit Attestation
6. `downloadAip` — `GET /safelta/core/v1/documents/{sip_submission_id}` — Download AIP
7. `searchArchiveAips` — `POST /safelta/core/v1/search/advanced` — Search Archive AIPs

## Rules

- Only call the operations listed above; inputs are defined by each operation's parameters and requestBody in the spec.
- The spec does not document idempotency keys: do not blindly retry create/send operations — check status first.
- InfoCert services are qualified trust services (eIDAS); calls create legally relevant evidence, so confirm intent with the user before sending, signing or preserving.
