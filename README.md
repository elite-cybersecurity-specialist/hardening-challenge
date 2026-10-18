<p align="center">
  <img src="assets/Hardening-Challenge.jpg" alt="KHAHP open defensive cybersecurity hardening challenge" width="100%">
</p>

<p align="center">
  <img src="assets/ECS-Deep-Security-Hardening-Services.png" alt="Elite Cybersecurity Specialist — Deep Security Hardening Services" width="100%">
</p>

<p align="center">
  <img src="assets/ECS-Defensive-Cloud-Hardening-Services.png" alt="Elite Cybersecurity Specialist — Defensive Cloud Hardening Services" width="100%">
</p>

# KHAHP — Kicksecure High-Assurance Hardening Project

### Beyond Conventional CIS Level 2 Baselines | Defense-in-Depth Security Engineering

**ELITE CYBERSECURITY SPECIALIST · MALAYSIA**  
**200+ HOURS OF HANDS-ON HARDENING AND SECURITY VERIFICATION (OWNER-REPORTED)**  
**Public documentation v4.1 · 19 October 2026 · Evidence observations through 18 October 2026**

> **The open challenge:** Can you engineer and demonstrate deeper, more reproducible operating-system defenses — with source evidence, functional security tests, and reliable recovery — than the controls shown here?

## Why we go beyond standard hardening

A system can benefit from **security hardening even without a demonstrated exploit**. Unnecessary exposure, overly broad permissions, weak isolation, incomplete audit coverage, default configurations, and gaps in persistence/recovery can create genuine opportunities to strengthen defensive posture. Our objective is **attack-surface reduction, defense in depth, privacy, reliable enforcement, and recoverable security controls** — not merely a list of known CVEs.

KHAHP builds on the existing protections of [Kicksecure](https://www.kicksecure.com/) and Debian 13, while investigating additional hardening against **applicable CIS Level 2 benchmark recommendations**, **DISA General Purpose Operating System SRG / relevant STIG-inspired control objectives**, **KSPP**, and project-specific high-assurance requirements. These frameworks are references for engineering depth; the project is not claiming external CIS or DISA certification.

**Our direction: go deeper than a conventional benchmark-only hardening exercise.** The public engineering register documents the observed defenses, additional changes, improvement opportunities, and exact evidence still required. The detailed CIS/DISA control-by-control comparison remains an explicit Section 43 completion task.

## Security engineering scope

| Engineering measure | Scope / current state |
|---|---|
| **Hardening domains** | **44 sections** across OS, boot, kernel, privilege, isolation, storage, network, privacy, devices, monitoring and recovery |
| **Control families** | **308** individual technical families (seven per section) |
| **Evidence checkpoints** | **924** A/B/C checkpoints: source/provenance, effective enforcement, persistence/recovery |
| **Engineering workstream** | Sections **01–40** investigated/implemented to varying evidence depth; **Section 40** auditd/AIDE end-to-end acceptance is still active |
| **Owner-completed domain** | **Section 39 — BIOS/firmware**; no further owner BIOS retests |
| **Next program phases** | **41** persistence/supply chain; **42** secrets/backup; **43** benchmark mappings; **44** formal acceptance |

**What 924 means:** There are 308 control families, each with three separate evidence requirements. This is a substantial **security configuration and assurance program**, not an assertion that stock Kicksecure has 924 exploits or that every checkpoint identifies a misconfiguration. A checkpoint may document an existing protection, expose a hardening gap, suggest an improvement, test a policy exception, or establish whether protection survives reboot and recovery.

## Demonstrated protections and corrective engineering

| Defensive domain | Work supported by the public technical register |
|---|---|
| **Privilege separation** | Distinct USER desktop and privileged SYSMAINT maintenance roles; no weakening of USER administrative restrictions to speed up testing |
| **Kernel and memory protections** | Observed `kptr_restrict=2`, `dmesg_restrict=1`, `ptrace_scope=3`, restricted unprivileged BPF, ASLR, and additional kernel protections |
| **Boot and encrypted storage** | Observed LUKS root, Secure Boot, signed Tirdad DKMS; controlled `/boot` and `/boot/efi` mount-order correction with successful immediate root validation |
| **Filesystem exposure** | Applied `/tmp` `nodev,nosuid` hardening, with deliberate compatibility review instead of blindly enabling `noexec` |
| **DNS, network and filtering** | Working local Unbound; DNSSEC valid-AD and invalid-SERVFAIL tests; configured authenticated DoT; inspected nftables and Tor/SOCKS paths |
| **Peripheral and device privacy** | USBGuard policy for authorized input and recovery storage; demonstrated USER camera/microphone device-open denial; Bluetooth blocked in tested state |
| **Browser and application privacy** | Firefox privacy restrictions and observed seccomp filtering; thumbnail-generation hardening with synthetic and post-reboot tests |
| **Security monitoring** | AIDE scheduled checking observed; auditd event-rule and end-to-end alert coverage remain active improvement/verification areas |

**Corrective work is documented, not theoretical:** At least three distinct configuration-change events are supported by the October 18 records: `/tmp` hardening, privacy-thumbnail protection, and correction of the `/boot`/`/boot/efi` mount ordering. They are examples, **not a comprehensive historical count of every hardening action**.

## How we classify a hardening finding

| Classification | Meaning |
|---|---|
| **Observed protection** | An existing Kicksecure/Debian or project protection whose present state has been inspected or tested |
| **Security configuration weakness / confirmed defect** | A demonstrably undesirable configuration with a defined security consequence or violated requirement |
| **Hardening enhancement opportunity** | An additional defensive control worth evaluating, even without a reproduced exploit |
| **Policy or compatibility decision** | A consciously selected trade-off, exception or not-applicable requirement |
| **Verification outstanding** | A security claim requiring more runtime, negative, reboot, or recovery evidence |

An incomplete verification gate is **not automatically a vulnerability**; equally, a weakness need **not be exploited** before it merits remediation. Both principles are essential for engineering an exceptionally hardened OS.

## Technical documentation — complete evidence scope

- **[Full 44-section technical register — v4.1](KHAHP_FULL_TECHNICAL_REGISTER.md)** — 308 individual control families, all 924 A/B/C gate identifiers, observed protections, improvement decisions, full 63-item historic follow-up reconciliation, and 60 proposed image-release tests.
- **[Public master technical evidence PDF — v4.1](docs/KHAHP_Public_Master_Evidence_Sections_01-44_v4.1.pdf)** — professionally formatted, complete portable publication of the updated register.

**Evidence status:** The baseline formal sign-off ledger provided on 18 October still has **0 of 924 reviewer-signed gates**. This is a documentation/acceptance state, **not a statement that no defenses have been implemented or that 924 controls failed**. Some successful demonstrations remain to be linked to the correct signed A/B/C records. The owner reports Section 39 BIOS complete and has excluded it from retesting. Section 40 auditd/AIDE acceptance and specified earlier follow-ups remain open. The underlying evidence and its limitations are listed in the register.

## Planned premium Kicksecure hardened OS

**Target price: USD $1,250.** Intended formats include physical ISO/USB, KVM/QCOW2 and VirtualBox/OVA. A public commercial image is **not represented as currently released**. Production delivery is conditional on clean-room build, unique machine identities and keys, reproducible tests, recovery proof, compatible licensing and formal image-release acceptance.

## Challenge and responsible publication

**Show the engineering:** Submit a threat model, provenance, baseline/changed values, narrowly scoped configuration, bounded authorized positive and negative testing, persistence, recovery/rollback results, and reproducible evidence. We welcome technically stronger defensive implementations and independent review.

**Privacy and publication:** No passwords, private keys, personal device identifiers, private firewall rules, raw audit histories, or sensitive host evidence are published. Existing vendor protections are credited to Kicksecure/Debian; project changes and deeper enhancement objectives are differentiated in the technical register.

**Project:** [Elite Cybersecurity Specialist](https://github.com/elite-cybersecurity-specialist) · Malaysia  
**Version:** v4.1 editorial revision (19 October 2026); machine evidence remains dated to the observations cited in the register.
