# CVE Proofs of Concept

This directory contains proofs of concept for specific, publicly disclosed vulnerabilities, each tied to its CVE (Common Vulnerabilities and Exposures) identifier. A CVE identifies one exact flaw in one specific product and version, so each entry here documents a reproducible exploit against a known-vulnerable target in my lab.

Where applicable, each writeup also lists the CWE (Common Weakness Enumeration) that describes the root cause. The CVE answers "which exact flaw in which product?" and the CWE answers "what class of mistake is this?"

## Directory Layout

```
CVEs/
├── README.md
└── CVE-<YEAR>-<ID>/
    ├── CVE-<YEAR>-<ID>.md     # Writeup: analysis, kill chain, detection, remediation
    └── CVE-<YEAR>-<ID>.py     # Proof-of-concept script
```

Each folder is named for the CVE ID, in uppercase.

## Entry Format

Every writeup opens with a metadata table:

```
| Field                  | Description                                               |
|------------------------|-----------------------------------------------------------|
| **CVE ID**             | The assigned identifier                                   |
| **Product / Version**  | The affected software and the exact version tested        |
| **CWE**                | Root-cause weakness, if applicable                        |
| **Vulnerability Type** | e.g., Remote Code Execution, Authentication Bypass        |
| **CVSS**               | Base score and vector as published at the time of writing |
| **Patched In**         | The fixed version, if one exists                          |
| **Lab Target**         | Where the vulnerable instance ran                         |
```

The rest of the writeup follows this order:

1. **Summary:** what the flaw is and why it matters
2. **Environment:** how the vulnerable target was built
3. **Exploitation:** step-by-step kill chain
4. **Detection:** what the IDS saw, missed, or could be tuned to catch, where applicable
5. **Remediation:** patch, configuration fix, or mitigation
6. **Lessons Learned**

## Index

```
| CVE                               | Product         | Type   | CWE       | CVSS  | Detected?            |
|-----------------------------------|-----------------|--------|-----------|-------|----------------------|
| [CVE-YYYY-NNNNN](CVE-YYYY-NNNNN/) | [Product x.y.z] | [Type] | CWE-[xxx] | [x.x] | [Yes / No / Partial] |
```
## Notes

* Scripts are written for a lab environment and kept small and focused on the single documented flaw. They are not general-purpose attack tools.
* Scripts may need adjustments (target address, port, versions) before they work in another environment.
* CVSS scores and CWE assignments are recorded as they stood when I wrote the entry. They can be revised later.

## Scope and Disclaimer

Every PoC in this directory was run only against vulnerable instances that I had authorized access to or built and own, on an isolated lab networks. This material is for education and defensive research only. Do not run any of it against systems you do not own or lack explicit written permission to test. Unauthorized access to computer systems is illegal.

My classifications and summaries are made in good faith and may contain errors. The author assumes no liability for misuse of this material or for any damage, data loss, or legal consequences resulting from it. Everything is provided "as is," without warranty of any kind.
