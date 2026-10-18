<p align="center">
  <img src="assets/Hardening-Challenge.jpg" alt="KHAHP open defensive cybersecurity hardening challenge" width="100%">
</p>

# KHAHP — Kicksecure High-Assurance Hardening Project

**200+ HOURS OF HANDS-ON CYBERSECURITY ENGINEERING, SYSTEM HARDENING AND VERIFICATION**  
**Elite Cybersecurity Specialist · Malaysia**  
**Public technical update: v4.0 · 18 October 2026**

> **The open challenge:** Can you demonstrate a stronger, more reproducible and better-evidenced defensive operating-system hardening result?

KHAHP is an independently developed hardening and assurance project built on [Kicksecure](https://www.kicksecure.com/). It combines Debian-based security engineering, a distinct USER/SYSMAINT administrative boundary, hardware and boot assurance, kernel protections, network privacy, application isolation, logging, recovery and repeatable negative testing.

**200+ hours** is the project owner's reported cumulative engineering effort, not an independently time-tracked metric.

<p align="center">
  <img src="assets/ECS-Deep-Security-Hardening-Services.png" alt="ECS Deep Security Hardening Services" width="100%">
</p>

## Progress and scope

| Measure | Current position |
|---|---|
| Hardening domains | **44** sections |
| Control families | **308** (7 per section) |
| Planned A/B/C acceptance gates | **924** (3 per family) |
| Working milestone | **Sections 01–40 covered by the implementation / investigation program** |
| Remaining program phases | **41 — persistence/supply chain; 42 — secrets/backup; 43 — standards mapping; 44 — final acceptance** |
| BIOS / firmware Section 39 | **Owner-declared complete; further BIOS retesting excluded** |
| Formal 924-gate reviewer signoffs in supplied register | **0 — not yet reconciled into signed evidence** |
| Proposed commercial-image release tests | **60; planned, not executed** |

**Status distinction:** The owner reports the 01–40 engineering milestone. This is *not* a claim that every Section 01–40 A/B/C gate has been independently signed or that no unverified requirement remains. Section 40 auditd/AIDE lifecycle acceptance and other specifically listed tests still require evidence. Open tests are not, by themselves, confirmed vulnerabilities.

## Engineering results — selected evidence

| Security domain | What was demonstrated | Evidence boundary |
|---|---|---|
| USER / SYSMAINT trust boundary | Dedicated ordinary-user and privileged maintenance workflows; read-only USER and SYSMAINT evidence collection | Full lifecycle acceptance remains independent |
| Filesystem protections | `/tmp` hardened with `nodev,nosuid`; later `/boot` / `/boot/efi` fstab ordering corrected and root validator passed | `/tmp` `noexec` deliberately not applied; fstab post-reboot proof still to be filed |
| Encryption and boot | LUKS root; Secure Boot enabled in a privileged snapshot; signed Tirdad DKMS observed | Offline key recovery and unsigned-module rejection need controlled proof |
| Kernel protections | Restricted ptrace, dmesg, BPF, ASLR and protected-file operations observed | Boot flags are not proof of every mitigation |
| Network and DNS | Local Unbound; DNSSEC positive AD and negative SERVFAIL; configured DNS-over-TLS; active nftables and Tor | Browser bypass, authenticated DoT negative and effective external DNS drop tests are separate |
| USB and privacy hardware | USBGuard authorizes known input/recovery devices; camera/microphone direct USER opens denied; Bluetooth blocked | External keyboard/mouse and composite-device policy test scope remains explicit |
| Firefox | Privacy preferences observed; some child processes have seccomp filtering | Vendor AppArmor Firefox profile remains `unconfined` — not a strict-confinement PASS |
| Desktop privacy and lock | Thumbnail restrictions applied; synthetic and restart evidence; interactive screen lock worked | Five-minute and suspend/resume behavior require distinct evidence |
| Monitoring | AIDE daily timer active | Auditd snapshot showed no active rules / no daemon PID; Section 40 event and AIDE alert lifecycle pending |

### What did we actually fix?

The **924 gates are questions to be verified, not 924 discovered weaknesses**. The earlier register has **69 mixed backlog items** (reviews, manual tests, exceptions and changes), not 69 proven vulnerabilities.

At least **three distinct configuration-change events** are identified in the supplied October 18 evidence history: `/tmp` mount hardening, disabling thumbnail generation, and correcting fstab boot-entry ordering. That is **not** a complete tally of all historic fixes or proof that all three changes arose from exploited vulnerabilities. A defensible total needs issue-by-issue before/after evidence review; the [technical register](KHAHP_FULL_TECHNICAL_REGISTER.md) explains what is known.

## Technical documentation

- **[Full 44-section technical register — v4.0](KHAHP_FULL_TECHNICAL_REGISTER.md)** — all 308 family names, 924 A/B/C IDs, evidence findings, historical issue reconciliation and 60 future release tests.
- **[Public master technical evidence PDF — v4.0](docs/KHAHP_Public_Master_Evidence_Sections_01-44_v4.0.pdf)** — structured, portable public technical report.

Raw host-specific logs, identifiers, credentials, device serials, private firewall configurations and encryption/recovery materials are **not** published.

## Premium Hardened OS — proposed product, not a released build

**Target price: USD $1,250.** Planned formats: physical ISO/USB installation, KVM/QCOW2 virtual machine and VirtualBox/OVA appliance. Each future delivery requires a clean build, unique customer identifiers and keys, compatibility testing, verified recovery and relevant security/third-party licensing. **No consumer ISO or virtual appliance is represented here as currently released or certified.**

## Rules of the open challenge

Provide a threat model, exact configuration provenance, narrowly scoped defensive changes, authorized runtime and negative tests, reboot/upgrade persistence, recovery/rollback proof and reproducible evidence. A screenshot, benchmark score or untested security claim alone is not enough.

**Engineering references:** CIS Debian Linux 13 Level 2 (where applicable), DISA General Purpose OS SRG objectives, KSPP and Kicksecure's own hardening model. These references do not amount to third-party CIS/DISA certification.

**Project:** [Elite Cybersecurity Specialist](https://github.com/elite-cybersecurity-specialist) · Malaysia  
**Revision policy:** evidence-first, read-only review before approved changes, no unreviewed publication of private machine data.
