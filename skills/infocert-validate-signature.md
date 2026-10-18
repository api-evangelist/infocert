---
name: infocert-validate-signature
description: Validate a signed document or a certificate with the InfoCert Signature
  Validation API.
api: openapi/infocert-signature-validation-openapi.yml
operations:
- validateDocumentCustom
- validateCertificateCustom
generated: '2026-10-18'
method: generated
---

# Validate Signature

Validate a signed document or a certificate with the InfoCert Signature Validation API.

Spec: `openapi/infocert-signature-validation-openapi.yml` (Signature Validation API). Security schemes declared: bearerAuth (http bearer).

## Steps

1. `validateDocumentCustom` — `POST /v4/qsvs/document` — Validate single document operation
2. `validateCertificateCustom` — `POST /v3/certificate` — Validate single certificate document operation

## Rules

- Only call the operations listed above; inputs are defined by each operation's parameters and requestBody in the spec.
- The spec does not document idempotency keys: do not blindly retry create/send operations — check status first.
- InfoCert services are qualified trust services (eIDAS); calls create legally relevant evidence, so confirm intent with the user before sending, signing or preserving.
