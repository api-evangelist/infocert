---
name: infocert-signing-envelope
description: Create, resend or cancel an InfoCert Sign signing envelope (signature
  workflow) for one or more signers.
api: openapi/infocert-infocert-sign-ext-5-1-openapi.yml
operations:
- getCurrentUserAvailableTaskActionTypes
- insertEnvelope
- resendEnvelope
- cancelEnvelope
generated: '2026-10-18'
method: generated
---

# Signing Envelope

Create, resend or cancel an InfoCert Sign signing envelope (signature workflow) for one or more signers.

Spec: `openapi/infocert-infocert-sign-ext-5-1-openapi.yml` (Infocert API). Security schemes declared: oAuth2 (oauth2).

## Steps

1. `getCurrentUserAvailableTaskActionTypes` — `GET /users/current/tasks/{action}/types` — For the connected user, gets the available action types for the action specified
2. `insertEnvelope` — `POST /envelopes` — Insert a new Envelope in Infocert Sign
3. `resendEnvelope` — `GET /envelopes/{externalId}/resend` — Resend notification
4. `cancelEnvelope` — `PUT /envelopes/{externalId}/cancel` — Cancel an Envelope (i.e. stops the process)

## Rules

- Only call the operations listed above; inputs are defined by each operation's parameters and requestBody in the spec.
- The spec does not document idempotency keys: do not blindly retry create/send operations — check status first.
- InfoCert services are qualified trust services (eIDAS); calls create legally relevant evidence, so confirm intent with the user before sending, signing or preserving.
