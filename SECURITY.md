# Security Policy

At **Kreflux**, security and transparency are foundational to everything we build. We process high-throughput reasoning workloads across multi-provider inference graphs, local-first CLI companion agents, and real-time scientific chat interfaces. Protecting user data, API credentials, compute budgets, and sandboxed execution environments is a critical priority.

---

## Supported Versions

Security updates are actively maintained for the following projects:

| Project | Branch / Version | Supported | Notes |
| :--- | :--- | :--- | :--- |
| **`kreflux`** | `main` | :white_check_mark: | Production Web App & Route Handlers |
| **`klucid`** | `>= 0.1.0` | :white_check_mark: | Official CLI Agent Releases |
| **`openkreflux`** | `main` | :white_check_mark: | Evaluation Engine & Router |
| **`.github`** | `main` | :white_check_mark: | Organization Workflows & Config |

Historical releases and unmaintained experimental forks do not receive backported security patches. Users are encouraged to run the latest versions.

---

## Threat Model & Scope

We welcome vulnerability reports concerning:

- **Inference Router & Credential Safety**: Leaks or exposure of upstream provider API keys (Featherless, Neokens, OpenRouter, vLLM).
- **Authentication & Device Pairing**: Flaws in the `klucid` device authorization flow, session token rotation, or Supabase Row-Level Security (RLS) bypasses.
- **Compute Metering & Budget Bypass**: Exploits allowing unauthorized compute drain, lease spoofing, or denial-of-service against provider routing tiers.
- **Frontend / Client Security**: Stored or reflected XSS vulnerabilities in the markdown rendering pipeline, KaTeX mathematical typesetting engine, or Mermaid SVG diagram generator.
- **Local Sandbox Execution**: Arbitrary code execution or sandbox escapes in local agent tool execution within `klucid`.

### Out of Scope

- Model output hallucination or non-deterministic reasoning output (unless demonstrating severe memory corruption or unauthorized sandbox breakout).
- Theoretical prompt injection without measurable privilege escalation or access boundary breach.
- Denial of Service attacks targeting high-volume network exhaustion (DDoS).
- Automated scanner reports without a verifiable proof of concept (PoC).
- Social engineering attacks targeting Kreflux team members or contributors.

---

## Reporting a Vulnerability

If you discover a security vulnerability in any Kreflux repository or service, **do not open a public GitHub issue, discussion, or pull request**.

Please submit all security disclosures directly to:

📧 **[security@kreflux.com](mailto:security@kreflux.com)**

### What to Include in Your Report

To help us triage and resolve the issue quickly, please provide:

1. **Repository & Component**: The repository name (`kreflux`, `klucid`, `openkreflux`) and specific file/service impacted.
2. **Vulnerability Type**: e.g., Authentication bypass, RLS policy gap, XSS in diagram renderer, remote code execution.
3. **Step-by-Step Reproduction**: Detailed steps, command lines, or minimal code snippets reproducing the issue.
4. **Proof of Concept (PoC)**: A functional proof-of-concept demonstrating security impact.
5. **Impact Assessment**: What an attacker could achieve if this vulnerability were exploited.
6. **Suggested Fix (Optional)**: Any remediation or patch suggestions.

---

## Response & Disclosure Timeline

We adhere to coordinated vulnerability disclosure standards:

- **Initial Acknowledgement**: Within **48 hours** of report receipt.
- **Triage & Severity Assessment**: Within **5 business days**, confirming reproduction and assigning a severity rating (CVSS).
- **Remediation & Patching**: Patches are developed in private forks and tested against CI suites. High and critical vulnerabilities are prioritized for immediate hotfix deployment.
- **Coordinated Disclosure**: We aim to release security advisories and publish fixes within **90 days** of initial disclosure, or sooner with mutual agreement from the reporter.

---

## Safe Harbor & Research Guidelines

Kreflux supports responsible, good-faith security research. We will not pursue legal action against security researchers who:

- Comply with this Security Policy and act in good faith.
- Avoid violating user privacy, accessing non-public user data, or destroying system integrity.
- Promptly report findings to [security@kreflux.com](mailto:security@kreflux.com) and allow reasonable time for remediation before public disclosure.
- Do not exploit a vulnerability beyond the minimal proof required to demonstrate impact.

Thank you for helping keep the Kreflux ecosystem secure for researchers and developers worldwide!
