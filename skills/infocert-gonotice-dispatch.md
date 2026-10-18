---
name: infocert-gonotice-dispatch
description: Set up a GoNotice process type and send a certified notification dispatch,
  then follow its status, history and audit.
api: openapi/infocert-gonotice-openapi.yml
operations:
- createProcessType
- enableProcessType
- createSingleDispatch
- GetSingleDispatch
- disableSingleDispatch
- auditSingleDispatch
- cancelSingleDispatch
generated: '2026-10-18'
method: generated
---

# Gonotice Dispatch

Set up a GoNotice process type and send a certified notification dispatch, then follow its status, history and audit.

Spec: `openapi/infocert-gonotice-openapi.yml` (GoNotice stats API). Security schemes declared: openID (openIdConnect); oAuth2 (oauth2).

## Steps

1. `createProcessType` — `POST /pt` — Creates a new Process Type
2. `enableProcessType` — `PUT /pt/{ptExternalID}/enable` — Enable a Process Type if it is in Draft or Disable state
3. `createSingleDispatch` — `POST /single` — Creates a new single dispatch to attempts to communicate with the destination user
4. `GetSingleDispatch` — `GET /single/{dispatchExternalID}` — Get information of a dispatch
5. `disableSingleDispatch` — `GET /single/{dispatchExternalID}/status` — Find the status of a dispatch
6. `auditSingleDispatch` — `GET /single/{dispatchExternalID}/audit` — Get a Dispatch audit content
7. `cancelSingleDispatch` — `POST /single/{dispatchExternalID}/cancel` — Cancel a Dispatch

## Rules

- Only call the operations listed above; inputs are defined by each operation's parameters and requestBody in the spec.
- The spec does not document idempotency keys: do not blindly retry create/send operations — check status first.
- InfoCert services are qualified trust services (eIDAS); calls create legally relevant evidence, so confirm intent with the user before sending, signing or preserving.
