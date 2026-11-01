# CWE Proofs of Concept

This directory contains proofs of concept for weaknesses that have **no CVE of their own**. They cover vulnerability classes demonstrated in intentionally vulnerable applications, training targets, or purpose-built example code. Each entry is organized by its CWE (Common Weakness Enumeration) identifier, which names the class of mistake behind the flaw, such as CWE-89 for SQL injection.

CVEs identify specific flaws in real products, so intentionally vulnerable software generally has none. Here, the CWE is the authoritative classification. Weaknesses that do have a CVE are documented in the `CVEs/` directory instead.

## Directory Layout

```
CWEs/
├── README.md
└── CWE-<ID>/
    ├── CWE-<ID>.md          # Writeup: weakness explanation, demonstration, fix
    └── exampleScript.c      # Minimal example code demonstrating the weakness
```

Each folder is named for the CWE ID, in uppercase.

## Entry Format

Every writeup opens with a metadata table:

```
| Field | Description |
|---------------------|------------------------------------------------------------------|
| **CWE ID and Name** | e.g., CWE-121: Stack-based Buffer Overflow                       |
| **Category**        | e.g., Memory Safety, Injection, Authentication                   |
| **Demonstrated In** | The target or example code used                                  |
| **Related CVE**     | An optional real-world CVE with a similar flaw, for context only |
```

The rest of the writeup follows this order:

1. **Description:** what the weakness is and why it occurs
2. **Vulnerable Code or Target:** where the flaw lives
3. **Demonstration:** how it is triggered and exploited, step by step
4. **Detection:** what the IDS, compiler warnings, or static analysis revealed or missed
5. **Remediation:** the secure coding pattern or configuration that fixes it
6. **Lessons Learned**

A related CVE is never presented as the vulnerability being demonstrated. It only shows how the same weakness appears in real software.

## Index

```
| CWE                 | Name            | Category   | Demonstrated In     | Detected?            |
|---------------------|-----------------|------------|---------------------|----------------------|
| [CWE-NNN](CWE-NNN/) | [Weakness name] | [Category] | [Target or example] | [Yes / No / Partial] |
```

## Notes

* Example code is intentionally insecure and minimal, written only to demonstrate the specific weakness. Compile and run it only in an isolated lab environment.
* Each writeup includes the fixed version of the pattern, so the example works as a before-and-after comparison.
* Weakness names and IDs are recorded as I understood them when writing the entry and may be revised or reorganized.

## Scope and Disclaimer

Every demonstration here targets software built to be vulnerable or code I wrote myself, run on an isolated lab network. This material is for education and defensive research only. Do not use these techniques against systems you do not own or lack explicit written permission to test. Unauthorized access to computer systems is illegal.

My classifications are made in good faith and may contain errors. The author assumes no liability for misuse of this material or for any damage, data loss, or legal consequences resulting from it. Everything is provided "as is," without warranty of any kind.
