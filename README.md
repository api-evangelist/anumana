# Anumana

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
