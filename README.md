# PoC Library

A collection of documented proof-of-concept attack chains against intentionally vulnerable targets on ethical hacking platforms and/or my own home lab. 

## Purpose

This library maps each proof of concept back to two public vulnerability indexes:

* **CWE (Common Weakness Enumeration):** A catalog of software and hardware weakness types. Each PoC is tied to the CWE that describes the root cause of the flaw being exploited, such as CWE-89 for SQL injection.
* **CVE (Common Vulnerabilities and Exposures):** A catalog of specific, publicly disclosed vulnerabilities in real products. A PoC is tied to a CVE only when one exists for the flaw being demonstrated.

The goal is to show how a hands-on attack relates to the standard vocabulary that defenders, vendors, and researchers use. A CWE answers "what class of mistake is this?" and a CVE answers "which exact flaw in which product?"

## How Entries Are Mapped

Every PoC begins with a metadata table that includes:

| Field | Description |
|-----------------|------------------------------------------------------------------------|
| **CWE**         | The most specific weakness that describes the root cause.              |
| **CVE**         | A specific assigned vulnerability ID, if one applies. Otherwise `N/A`. |
| **Related CVE** | Optional real-world CVE with a similar flaw, listed for context only.  |

**Why many entries have no CVE:** Intentionally vulnerable applications contain their flaws by design and generally are not assigned CVEs for them. In those cases the CWE is the authoritative classification. A related CVE is never presented as the vulnerability being exploited. It only illustrates how the same weakness appears in real software.

**Choosing a CWE:** I map to the most specific CWE that describes the root cause rather than the symptom. When a chain exploits multiple flaws, each CWE is listed under the stage where it applies.


## Repository Structure

```
poc-library/
├── README.md
├── pocs/
│   ├── CVEs/    # Relevant CWEs included in writeup where applicable
│   |   ├── README.md          
│   |   └── CVE-<YEAR>-<ID>/
|   |       ├── CVE-<Year>-<ID>.md
|   |       └── CVE-<YEAR>-<ID>.py
|   └── CWEs/    # For weaknesses and exposures with no CVE
|       ├── README.md
|       └── CWE-<ID>/   
|           ├── CWE-<ID>.md
|           └── exampleScript.c
└── writeups/
    ├── HTB/
    |   └── <LabName>/
    |       └── <LabName>.md
    └── OffSec/
        └── <LabName>/
            └── <LabName>.md          
```

## Lab Environment

All targets on ethical hacking platforms or segmented home lab with a firewall, VLAN-capable managed switch, and an IDS fed by a mirrored port. Environment details are documented in my separate [homelab repository](https://github.com/zbarnett-sec/homelab).

## Scope

* Every entry targets software built to be vulnerable (such as training applications and CTF machines) or infrastructure I own and operate.
* Nothing here is demonstrated against systems I do not own or lack explicit authorization to test.
* Entries from platforms with publishing restrictions are shared only when public writeups are permitted. Flags are never included.

## Disclaimer

This repository is for educational and defensive research purposes only. The techniques documented here must only be used against systems you own or have explicit written permission to test. Unauthorized access to computer systems is illegal.

The vulnerable targets described here are dangerous by design and should be run only on isolated lab networks, never on production or personal networks. The CWE and CVE mappings are my own good-faith classifications and may contain errors or be superseded as the indexes are revised. They should not be treated as authoritative.

The author assumes no liability for misuse of this material or for any damage, data loss, or legal consequences resulting from reproducing these techniques. Everything is provided "as is," without warranty of any kind.
