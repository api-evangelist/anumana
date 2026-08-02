# Anumana

Anumana, Inc. is a cardiac AI health-technology company founded as a joint venture between
Mayo Clinic and nference. Its FDA-cleared ECG-AI algorithms read standard 10-second, 12-lead
electrocardiograms to surface disease signals that are not visible to the human eye —
low ejection fraction, cardiac amyloidosis, and pulmonary hypertension among them.

Anumana ships as a **regulated medical device**, not as a developer API. The algorithms run
inside the customer's own ECG management system and EHR environment: digital waveform files
(XML or DICOM) go in, and results flow back into clinical workflow over configured HL7
datapoints.

- Website: https://anumana.ai/
- Platform sign in: https://api.anumana.ai/auth/signin/
- Trust center: https://trust.anumana.ai/
- Forge Global secondary-market listing: https://forgeglobal.com/anumana_stock/

## API posture

**No public machine-readable contract.** Contract discovery on 2026-08-02 probed every
Anumana host for OpenAPI, GraphQL, MCP, AsyncAPI, and an A2A agent card. All missed.
`api.anumana.ai` is a fully authenticated application that 302-redirects *every*
unauthenticated path to `/auth/signin/`, so 200s from that host are the sign-in shell, not
API responses. There are no published SDKs, no CLI, and no GitHub organization.

The full negative-result record — every host, path, and status code — is in
[`discovery/anumana-contract-discovery.yml`](discovery/anumana-contract-discovery.yml) so a
later pass does not re-litigate the same probes.

## Artifacts

| Artifact | File |
|---|---|
| Contract discovery record | `discovery/anumana-contract-discovery.yml` |
| Conformance (regulatory + protocol) | `conformance/anumana-conformance.yml` |
| FDA 510(k) verbatim openFDA response | `conformance/anumana-fda-510k.json` |
| Vulnerability disclosure policy | `security/anumana-vulnerability-disclosure.yml` |
| Trust center | `security/anumana-trust-center.yml` |
| Domain security probe | `security/anumana-domain-security.yml` |
| Well-known negative-result record | `well-known/anumana-well-known.yml` |
| llms.txt | `llms/anumana-llms.txt` |

## Regulatory

Six Traditional 510(k) clearances, verified against the openFDA device database:
K250652, K253801, K252360, K260300, K233160, K232699.
