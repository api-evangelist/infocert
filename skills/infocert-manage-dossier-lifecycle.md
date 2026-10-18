---
name: infocert-manage-dossier-lifecycle
description: Create, retrieve, check status, and delete a dossier in the Infocert platform.
api: openapi/infocert-gosign5-openapi.yml
operations:
- createDossier
- getDossierUsingGET
- getDossierStatusUsingGET
- deleteDossier
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/infocert-gosign5-openapi.yml ; every operationId checked against the contract
---

# infocert-manage-dossier-lifecycle

Create, retrieve, check status, and delete a dossier in the Infocert platform.

## Steps

1. 1. Create a new dossier using `createDossier` with required dossier fields in the request body
2. 2. Retrieve dossier details (excluding document content) using `getDossierUsingGET` with the `dossierExternalId` path parameter
3. 3. Check dossier status using `getDossierStatusUsingGET` with the `dossierExternalId` path parameter
4. 4. Delete the dossier using `deleteDossier` with the `dossierExternalId` path parameter

## Rules

- Use APIKeyAuth with X-InfoCert-GS-APIKey header for authentication
- All operations require proper authentication as specified in auth schemes
- Operations are performed on servers like https://api.infocert.digital/atum/v1
- Path parameters like dossierExternalId must be provided for GET and DELETE operations
