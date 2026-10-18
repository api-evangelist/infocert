---
name: infocert-remote-sign-hash
description: 'Remotely sign document hashes with a qualified credential through the
  Cloud Signature Consortium (CSC) API: authenticate, pick a credential, authorise
  with OTP, sign.'
api: openapi/infocert-csc-openapi.json
operations:
- info
- authLogin
- credentialsList
- credentialsInfo
- credentialsSendOTP
- credentialsAuthorize
- signaturesSignHash
- authRevoke
generated: '2026-10-18'
method: generated
---

# Remote Sign Hash

Remotely sign document hashes with a qualified credential through the Cloud Signature Consortium (CSC) API: authenticate, pick a credential, authorise with OTP, sign.

Spec: `openapi/infocert-csc-openapi.json` (CSC Api). Security schemes declared: BasicAuth (http basic); BearerAuth (http bearer).

## Steps

1. `info` — `POST /info` — Returns several information about the Remote Service and the list of the API methods implemented and supported by it.
2. `authLogin` — `POST /auth/login` — Obtain an access token for service authorization from the Remote Service using HTTP Basic Authentication or HTTP Digest 
3. `credentialsList` — `POST /credentials/list` — Returns the list of credentials associated with a user identifier
4. `credentialsInfo` — `POST /credentials/info` — Retrieve the credential and return the main identity information and the public key certificate or the certificate chain
5. `credentialsSendOTP` — `POST /credentials/sendOTP` — Start the online OTP generation mechanism associated with a credential and managed by the Remote Service.
6. `credentialsAuthorize` — `POST /credentials/authorize` — Authorize the access to the credential for remote signing, according to the authorization mechanisms associated to it.
7. `signaturesSignHash` — `POST /signatures/signHash` — Calculate the remote digital signature of one or multiple hash values provided as an input.
8. `authRevoke` — `POST /auth/revoke` — Revoke a service access token or refresh token that was obtained from the Remote Service or an associated Authorization 

## Rules

- Only call the operations listed above; inputs are defined by each operation's parameters and requestBody in the spec.
- The spec does not document idempotency keys: do not blindly retry create/send operations — check status first.
- InfoCert services are qualified trust services (eIDAS); calls create legally relevant evidence, so confirm intent with the user before sending, signing or preserving.
