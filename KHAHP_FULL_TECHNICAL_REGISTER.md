# KHAHP — Full Technical Evidence & Engineering Register

**Public Consolidated Release v5.0 · 19 October 2026 · Sections 01-40 project closeout**  
**Elite Cybersecurity Specialist · Malaysia**  
**200+ hours of owner-reported engineering · 44 security domains · 308 control families · 924 A/B/C assurance checkpoints**

> **Engineering mission:** expose enough real implementation detail to demonstrate the quality of our defensive hardening methodology while keeping private host identifiers, secrets and sensitive operational evidence out of the public repository.

## 1. Executive engineering position and integrity statement

KHAHP is a high-assurance defensive hardening and verification program for a Kicksecure / Debian 13 laptop. The project uses Kicksecure as a **public reference implementation** for the engineering discipline behind Elite Cybersecurity Specialist hardening services.

### 1.1. Kicksecure OS Royal Hardening — public reference implementation

**Kicksecure OS Royal Hardening details are deliberately revealed as an example of the quality, depth and evidence discipline of our work.** The public register shows the structure of the investigation, the defensive control families, implementation decisions and sanitized acceptance evidence.

The same evidence-led method is offered for other supported environments, but each target requires its own platform-specific implementation and validation:

| Platform / service | Hardening scope offered |
|---|---|
| **Kicksecure OS** | Public reference implementation / Royal Hardening engineering demonstration |
| **Ubuntu / Debian Linux** | Server and workstation hardening, service reduction, kernel/filesystem/network policy, logging and recovery |
| **RHEL / Rocky / AlmaLinux / CentOS Stream** | SELinux-aware hardening, service policy, network controls, provenance and recovery |
| **Windows Server / enterprise workstations** | Least privilege, Defender/audit policy, service reduction, network and identity controls |
| **AWS / Azure / Google Cloud / Oracle Cloud** | IAM, segmentation, encryption, logging, drift control and recovery assurance |
| **VMware ESXi / Proxmox VE** | Management-plane protection, segmentation, update provenance and restore validation |
| **Supported managed endpoints / devices** | Vendor-capability-based service, port, update, telemetry and lifecycle hardening |

A Kicksecure result does **not** automatically certify the other platforms. Every client environment requires its own scoped controls and evidence.

### 1.2. Program progress

<p align="center"><img src="assets/progress-reconnaissance.svg" alt="Reconnaissance and security review 40 of 44" width="100%"></p>
<p align="center"><img src="assets/progress-implementation.svg" alt="Hardening implementation 40 of 44" width="100%"></p>
<p align="center"><img src="assets/progress-assurance.svg" alt="A/B/C assurance 840 of 924" width="100%"></p>

| Workstream | Progress | Current state |
|---|---:|---|
| **Reconnaissance / security review** | **40 / 44 sections (90.9%)** | Sections 01-40 completed; Sections 41-44 are the next reconnaissance phase |
| **Hardening implementation** | **40 / 44 sections (90.9%)** | Sections 01-40 project-complete; Sections 41-44 have not yet completed reconnaissance or implementation |
| **A/B/C assurance checkpoints** | **840 / 924 (90.9%)** | Project-accepted for Sections 01-40 |
| **Remaining sections / checkpoints** | **4 sections / 84 checkpoints (9.1%)** | Sections 41-44: reconnaissance, implementation and final assurance still to be completed |

The **924 checkpoints are not 924 vulnerabilities**. They are 308 control families multiplied by three assurance dimensions: provenance/configuration (A), effective enforcement (B), and persistence/recovery (C). A checkpoint can validate an inherited protection, document a project hardening change, record an accepted compatibility decision, or prove lifecycle behavior.

### 1.3. What “01-40 complete” means

Sections **01-40 are project-accepted with no remaining implementation gaps** in the current KHAHP master. The 840 associated A/B/C checkpoints are closed as implemented, satisfied, accepted design, accepted compatibility/policy disposition, or not-applicable within project scope. Re-testing is required after material changes such as major updates, kernel changes, policy changes, hardware changes or release-image creation.

This is **project/owner acceptance**, not third-party CIS, DISA or KSPP certification. Section 43 remains the dedicated control-by-control standards-mapping phase, and Section 44 remains final whole-program acceptance for all 44 sections.

### 1.4. Security finding and acceptance vocabulary

| Classification | Meaning |
|---|---|
| **Observed protection** | Existing Kicksecure/Debian or project protection inspected or tested |
| **Confirmed security weakness / defect** | Demonstrated undesirable behavior against an approved security requirement |
| **Hardening enhancement** | Additional defense-in-depth improvement, even without a reproduced exploit |
| **Policy / compatibility disposition** | Deliberate design trade-off, exception or N/A decision accepted by the project |
| **Project accepted** | Implementation/control family closed within KHAHP scope and current baseline |
| **External certification** | Independent certification/assessment by the relevant external authority; **not claimed by this project** |

### 1.5. High-value completed engineering outcomes

| Defensive domain | Accepted project outcome |
|---|---|
| **Privilege separation** | Distinct USER desktop and privileged SYSMAINT maintenance roles retained; no weakening of USER administrative restrictions for convenience |
| **Kernel / memory** | Restricted kernel pointers, dmesg, ptrace and unprivileged BPF plus hardened boot/memory parameters |
| **Encrypted storage / boot** | LUKS root, Secure Boot evidence, signed DKMS evidence and corrected /boot -> /boot/efi ordering |
| **Filesystem** | /tmp nodev,nosuid hardening with compatibility-driven noexec disposition |
| **DNS / network / firewall** | Local Unbound, DNSSEC, authenticated DoT architecture, nftables and Tor/SOCKS policy reconciled into the hardened baseline |
| **Devices / privacy** | USBGuard owner policy, camera/microphone USER denial, Bluetooth block and desktop privacy controls |
| **Browser / application privacy** | Firefox privacy controls, seccomp observations and thumbnail-generation hardening |
| **Audit / integrity** | auditd active with effective KHAHP rules in normal USER boot; production AIDE scheduled check completed successfully; persistent AIDE lock-helper policy repaired |

## 2. Evidence model and status rules

| Gate | Assurance purpose |
|---|---|
| **A - provenance/configuration** | Approved source, package/file ownership, intended policy, accepted design or exception |
| **B - effective enforcement** | Role-appropriate runtime behavior, bounded allow/deny proof or accepted applicability determination |
| **C - persistence/recovery** | Relevant reboot/reconnect/update/recovery behavior or documented project exception |

For Sections 01-40 the authoritative private ledger marks all **840 gates as `PROJECT_ACCEPTED`**. Public documentation intentionally summarizes sensitive evidence rather than publishing raw host identifiers, private rulesets, keys, addresses or confidential logs.

## 3. Configuration changes, corrective actions and durable results

| ID / area | Accepted result |
|---|---|
| Filesystem / `/tmp` | `nodev,nosuid` retained; blanket `noexec` rejected as an owner-approved compatibility disposition |
| `/boot` and `/boot/efi` | fstab ordering corrected, immediate validation completed and carried into the accepted baseline |
| Desktop privacy | Thumbnail generation disabled and persistence verified |
| Section 40 AIDE | `/usr/bin/dotlockfile` persistent override corrected to `755 root:mail`; production `dailyaidecheck.service` subsequently completed successfully |
| Section 40 auditd | Persistent KHAHP rules compile cleanly and are effectively loaded in normal USER boot; SYSMAINT no-rules state is role-specific because auditd is inactive there |

## 4. Current project boundary

- **Sections 01-40:** complete / project-accepted / no open implementation gaps.
- **Section 39:** owner-complete and excluded from retest unless the owner intentionally reopens firmware work.
- **Section 40:** completed with final auditd/AIDE acceptance evidence captured on 19 October 2026.
- **Sections 41-44:** remaining program work: persistence/supply chain, secrets/backup/recovery, detailed standards mapping, and final 44-section acceptance.
- **Commercial image/release engineering:** separate from the laptop hardening baseline and remains subject to clean-room/release tests.

## 5. Implementation review by all 44 sections

Each section retains seven technical control families and 21 A/B/C checkpoint identifiers. For Sections 01-40, the status shown here is **project accepted**. Sections 41-44 remain the active next phase.

### 01 — Platform / OS / Hardware Baseline

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** Debian 13 / Kicksecure platform identity, kernel, hardware, storage and baseline health were reconciled into the authoritative master.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `01.01` | Operating-system identity and Debian/Kicksecure release baseline | `KHAHP-01.01A` · `KHAHP-01.01B` · `KHAHP-01.01C` |
| `01.02` | Kernel release, architecture and build identity | `KHAHP-01.02A` · `KHAHP-01.02B` · `KHAHP-01.02C` |
| `01.03` | CPU model, topology and virtualization capability | `KHAHP-01.03A` · `KHAHP-01.03B` · `KHAHP-01.03C` |
| `01.04` | Physical memory and swap capacity baseline | `KHAHP-01.04A` · `KHAHP-01.04B` · `KHAHP-01.04C` |
| `01.05` | Storage controller, disk and filesystem topology | `KHAHP-01.05A` · `KHAHP-01.05B` · `KHAHP-01.05C` |
| `01.06` | UEFI/bare-metal/virtualization platform state | `KHAHP-01.06A` · `KHAHP-01.06B` · `KHAHP-01.06C` |
| `01.07` | Failed-unit, uptime, boot-time and baseline health state | `KHAHP-01.07A` · `KHAHP-01.07B` · `KHAHP-01.07C` |

### 02 — Kicksecure Package Provenance

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** Package database health and security-package provenance were reviewed; package-owned and locally modified security configuration is tracked in the private evidence set.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `02.01` | Core Kicksecure package installation and exact versions | `KHAHP-02.01A` · `KHAHP-02.01B` · `KHAHP-02.01C` |
| `02.02` | Supporting security-package installation and exact versions | `KHAHP-02.02A` · `KHAHP-02.02B` · `KHAHP-02.02C` |
| `02.03` | APT source files and repository configuration | `KHAHP-02.03A` · `KHAHP-02.03B` · `KHAHP-02.03C` |
| `02.04` | APT policy and repository origin attribution | `KHAHP-02.04A` · `KHAHP-02.04B` · `KHAHP-02.04C` |
| `02.05` | Package ownership of security-critical configuration files | `KHAHP-02.05A` · `KHAHP-02.05B` · `KHAHP-02.05C` |
| `02.06` | Package holds, partial installs and dpkg database health | `KHAHP-02.06A` · `KHAHP-02.06B` · `KHAHP-02.06C` |
| `02.07` | Local modifications versus package-owned baseline | `KHAHP-02.07A` · `KHAHP-02.07B` · `KHAHP-02.07C` |

### 03 — USER / SYSMAINT Privilege Architecture

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** Normal USER and privileged SYSMAINT roles remain separated. Privileged maintenance is performed only in the dedicated maintenance boot context.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `03.01` | USER, SYSMAINT and root account separation | `KHAHP-03.01A` · `KHAHP-03.01B` · `KHAHP-03.01C` |
| `03.02` | Distinct UID/GID and home-directory boundaries | `KHAHP-03.02A` · `KHAHP-03.02B` · `KHAHP-03.02C` |
| `03.03` | user-sysmaint-split package and owned policy files | `KHAHP-03.03A` · `KHAHP-03.03B` · `KHAHP-03.03C` |
| `03.04` | sudo binary ownership, mode and SYSMAINT-only execution | `KHAHP-03.04A` · `KHAHP-03.04B` · `KHAHP-03.04C` |
| `03.05` | sudoers syntax and user-sysmaint- split policy | `KHAHP-03.05A` · `KHAHP-03.05B` · `KHAHP-03.05C` |
| `03.06` | USER negative sudo/root acquisition probe | `KHAHP-03.06A` · `KHAHP-03.06B` · `KHAHP-03.06C` |
| `03.07` | Login-shell and boot-role separation behavior | `KHAHP-03.07A` · `KHAHP-03.07B` · `KHAHP-03.07C` |

### 04 — SYSMAINT Boot Role

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** SYSMAINT boot markers and role-specific maintenance workflow are retained as part of the hardened operating model.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `04.01` | boot-role=sysmaint kernel marker | `KHAHP-04.01A` · `KHAHP-04.01B` · `KHAHP-04.01C` |
| `04.02` | systemd.unit=sysmaint-boot.target marker | `KHAHP-04.02A` · `KHAHP-04.02B` · `KHAHP-04.02C` |
| `04.03` | sysmaint-boot.target package provenance and unit content | `KHAHP-04.03A` · `KHAHP-04.03B` · `KHAHP-04.03C` |
| `04.04` | Required SYSMAINT dependencies and wanted units | `KHAHP-04.04A` · `KHAHP-04.04B` · `KHAHP-04.04C` |
| `04.05` | Intentionally omitted USER-only or incompatible hardeners | `KHAHP-04.05A` · `KHAHP-04.05B` · `KHAHP-04.05C` |
| `04.06` | Conflicting USER/graphical boot-role negative checks | `KHAHP-04.06A` · `KHAHP-04.06B` · `KHAHP-04.06C` |
| `04.07` | Failed units and SYSMAINT boot health | `KHAHP-04.07A` · `KHAHP-04.07B` · `KHAHP-04.07C` |

### 05 — Accounts / UID / GID / Local Identity

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** Local account, UID/GID, service-account and sensitive identity-file controls were reviewed and accepted for the hardened baseline.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `05.01` | root, USER and SYSMAINT account identity | `KHAHP-05.01A` · `KHAHP-05.01B` · `KHAHP-05.01C` |
| `05.02` | Duplicate UID and duplicate GID detection | `KHAHP-05.02A` · `KHAHP-05.02B` · `KHAHP-05.02C` |
| `05.03` | UID 0 exclusivity and privileged- account review | `KHAHP-05.03A` · `KHAHP-05.03B` · `KHAHP-05.03C` |
| `05.04` | Low-UID service-account shell classification | `KHAHP-05.04A` · `KHAHP-05.04B` · `KHAHP-05.04C` |
| `05.05` | Home-directory ownership and permissions | `KHAHP-05.05A` · `KHAHP-05.05B` · `KHAHP-05.05C` |
| `05.06` | shadow/gshadow/passwd/group ownership and modes | `KHAHP-05.06A` · `KHAHP-05.06B` · `KHAHP-05.06C` |
| `05.07` | NSS identity source configuration and root lock state | `KHAHP-05.07A` · `KHAHP-05.07B` · `KHAHP-05.07C` |

### 06 — LUKS / Disk / Swap Encryption

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** LUKS-encrypted root storage and encrypted-storage policy are part of the accepted baseline; recovery handling is governed by the project recovery policy.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `06.01` | Root filesystem source and dm-crypt mapping | `KHAHP-06.01A` · `KHAHP-06.01B` · `KHAHP-06.01C` |
| `06.02` | LUKS2 backing partition and cryptsetup status | `KHAHP-06.02A` · `KHAHP-06.02B` · `KHAHP-06.02C` |
| `06.03` | LUKS header metadata without key- material disclosure | `KHAHP-06.03A` · `KHAHP-06.03B` · `KHAHP-06.03C` |
| `06.04` | Root encryption chain from block device to mountpoint | `KHAHP-06.04A` · `KHAHP-06.04B` · `KHAHP-06.04C` |
| `06.05` | Active swap inventory and encrypted placement | `KHAHP-06.05A` · `KHAHP-06.05B` · `KHAHP-06.05C` |
| `06.06` | swapfile ownership, mode and containing filesystem | `KHAHP-06.06A` · `KHAHP-06.06B` · `KHAHP-06.06C` |
| `06.07` | crypttab/fstab encryption persistence and boot mapping | `KHAHP-06.07A` · `KHAHP-06.07B` · `KHAHP-06.07C` |

### 07 — Filesystem / Mount Security

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** Filesystem and mount hardening includes /tmp nodev,nosuid and corrected /boot before /boot/efi ordering. noexec exclusions are accepted compatibility decisions, not open defects.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `07.01` | Effective mount table and filesystem inventory | `KHAHP-07.01A` · `KHAHP-07.01B` · `KHAHP-07.01C` |
| `07.02` | Root mount source, filesystem and options | `KHAHP-07.02A` · `KHAHP-07.02B` · `KHAHP-07.02C` |
| `07.03` | /boot and /boot/efi separation, ownership and exposure | `KHAHP-07.03A` · `KHAHP-07.03B` · `KHAHP-07.03C` |
| `07.04` | /tmp tmpfs, sticky bit and mount- option review | `KHAHP-07.04A` · `KHAHP-07.04B` · `KHAHP-07.04C` |
| `07.05` | /var/tmp sticky-bit and separate- mount review | `KHAHP-07.05A` · `KHAHP-07.05B` · `KHAHP-07.05C` |
| `07.06` | /home containment, ownership and inherited options | `KHAHP-07.06A` · `KHAHP-07.06B` · `KHAHP-07.06C` |
| `07.07` | Writable mountpoints, fstab and remount-secure review | `KHAHP-07.07A` · `KHAHP-07.07B` · `KHAHP-07.07C` |

### 08 — GRUB / Bootloader Protection

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** GRUB and bootloader protections were reconciled with the project recovery model and accepted for the 01-40 implementation baseline.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `08.01` | GRUB package baseline and generated grub.cfg | `KHAHP-08.01A` · `KHAHP-08.01B` · `KHAHP-08.01C` |
| `08.02` | grub.cfg ownership, permissions and menu entries | `KHAHP-08.02A` · `KHAHP-08.02B` · `KHAHP-08.02C` |
| `08.03` | GRUB password_pbkdf2 and superusers directives | `KHAHP-08.03A` · `KHAHP-08.03B` · `KHAHP-08.03C` |
| `08.04` | Kicksecure CPU/kernel/ram-wipe/remount/signed -module fragments | `KHAHP-08.04A` · `KHAHP-08.04B` · `KHAHP-08.04C` |
| `08.05` | Quiet-boot and recovery-restriction fragments | `KHAHP-08.05A` · `KHAHP-08.05B` · `KHAHP-08.05C` |
| `08.06` | Effective boot command-line correlation | `KHAHP-08.06A` · `KHAHP-08.06B` · `KHAHP-08.06C` |
| `08.07` | /boot and EFI exposure versus cryptographic integrity limits | `KHAHP-08.07A` · `KHAHP-08.07B` · `KHAHP-08.07C` |

### 09 — CPU Vulnerability Mitigations

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** CPU vulnerability mitigations and hardened boot parameters are part of the accepted runtime baseline.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `09.01` | CPU identity, vendor and mitigation- capability baseline | `KHAHP-09.01A` · `KHAHP-09.01B` · `KHAHP-09.01C` |
| `09.02` | SMT/Hyper-Threading disablement and topology | `KHAHP-09.02A` · `KHAHP-09.02B` · `KHAHP-09.02C` |
| `09.03` | Runtime microcode revision and package baseline | `KHAHP-09.03A` · `KHAHP-09.03B` · `KHAHP-09.03C` |
| `09.04` | Kernel vulnerability-interface enumeration | `KHAHP-09.04A` · `KHAHP-09.04B` · `KHAHP-09.04C` |
| `09.05` | Spectre/Meltdown/L1TF/MDS/ Retbleed/BHI/SSB/TAA/GDS mitigations | `KHAHP-09.05A` · `KHAHP-09.05B` · `KHAHP-09.05C` |
| `09.06` | Mitigation-related kernel command- line parameters | `KHAHP-09.06A` · `KHAHP-09.06B` · `KHAHP-09.06C` |
| `09.07` | CPU mitigation flags and kernel-log confirmation | `KHAHP-09.07A` · `KHAHP-09.07B` · `KHAHP-09.07C` |

### 10 — IOMMU / DMA Protection

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** IOMMU / DMA isolation controls and firmware-related boundaries were reconciled with the owner-completed firmware policy.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `10.01` | CPU virtualization/VT-d capability baseline | `KHAHP-10.01A` · `KHAHP-10.01B` · `KHAHP-10.01C` |
| `10.02` | IOMMU kernel parameters and passthrough policy | `KHAHP-10.02A` · `KHAHP-10.02B` · `KHAHP-10.02C` |
| `10.03` | DMAR/IOMMU runtime enablement | `KHAHP-10.03A` · `KHAHP-10.03B` · `KHAHP-10.03C` |
| `10.04` | Translated default domain and strict invalidation | `KHAHP-10.04A` · `KHAHP-10.04B` · `KHAHP-10.04C` |
| `10.05` | IRQ/interrupt remapping | `KHAHP-10.05A` · `KHAHP-10.05B` · `KHAHP-10.05C` |
| `10.06` | IOMMU group topology and full PCI membership | `KHAHP-10.06A` · `KHAHP-10.06B` · `KHAHP-10.06C` |
| `10.07` | Early PCI DMA restriction and firmware WSMT evidence | `KHAHP-10.07A` · `KHAHP-10.07B` · `KHAHP-10.07C` |

### 11 — Kernel Sysctl Hardening

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** Effective kernel restrictions include kptr_restrict=2, dmesg_restrict=1, ptrace_scope=3 and restricted unprivileged BPF, alongside additional hardened sysctls.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `11.01` | Sysctl source-tree inventory and precedence | `KHAHP-11.01A` · `KHAHP-11.01B` · `KHAHP-11.01C` |
| `11.02` | Kicksecure security-misc sysctl source files | `KHAHP-11.02A` · `KHAHP-11.02B` · `KHAHP-11.02C` |
| `11.03` | Kernel information-leak restrictions | `KHAHP-11.03A` · `KHAHP-11.03B` · `KHAHP-11.03C` |
| `11.04` | ASLR, mmap, kexec and privileged- coredump controls | `KHAHP-11.04A` · `KHAHP-11.04B` · `KHAHP-11.04C` |
| `11.05` | BPF, ptrace, perf and TTY line- discipline restrictions | `KHAHP-11.05A` · `KHAHP-11.05B` · `KHAHP-11.05C` |
| `11.06` | Protected links/FIFOs/regular-file controls | `KHAHP-11.06A` · `KHAHP-11.06B` · `KHAHP-11.06C` |
| `11.07` | Network-stack sysctl hardening observations | `KHAHP-11.07A` · `KHAHP-11.07B` · `KHAHP-11.07C` |

### 12 — Kernel Boot / Memory Hardening

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** Kernel boot and memory-hardening parameters were reconciled as part of the accepted 01-40 baseline.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `12.01` | Slab allocator hardening and slab_nomerge | `KHAHP-12.01A` · `KHAHP-12.01B` · `KHAHP-12.01C` |
| `12.02` | init_on_alloc and init_on_free memory initialization | `KHAHP-12.02A` · `KHAHP-12.02B` · `KHAHP-12.02C` |
| `12.03` | page allocator shuffle and stack randomization | `KHAHP-12.03A` · `KHAHP-12.03B` · `KHAHP-12.03C` |
| `12.04` | vsyscall, vdso32 and 32-bit compatibility restrictions | `KHAHP-12.04A` · `KHAHP-12.04B` · `KHAHP-12.04C` |
| `12.05` | debugfs, KFENCE and kernel debug- surface controls | `KHAHP-12.05A` · `KHAHP-12.05B` · `KHAHP-12.05C` |
| `12.06` | CFI/KCFI and boot-time control acceptance | `KHAHP-12.06A` · `KHAHP-12.06B` · `KHAHP-12.06C` |
| `12.07` | pstore/ERST/proc_mem/entropy trust boot parameters | `KHAHP-12.07A` · `KHAHP-12.07B` · `KHAHP-12.07C` |

### 13 — Kernel Module Restrictions

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** Kernel-module restriction policy, prohibited/legacy module handling and compatibility exceptions are accepted within project scope.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `13.01` | security-misc module blacklist configuration | `KHAHP-13.01A` · `KHAHP-13.01B` · `KHAHP-13.01C` |
| `13.02` | Hard-disable install rules for risky modules | `KHAHP-13.02A` · `KHAHP-13.02B` · `KHAHP-13.02C` |
| `13.03` | Loaded-module inventory versus policy | `KHAHP-13.03A` · `KHAHP-13.03B` · `KHAHP-13.03C` |
| `13.04` | Legacy filesystem module restrictions | `KHAHP-13.04A` · `KHAHP-13.04B` · `KHAHP-13.04C` |
| `13.05` | Legacy network/protocol module restrictions | `KHAHP-13.05A` · `KHAHP-13.05B` · `KHAHP-13.05C` |
| `13.06` | USB/storage/media module restriction exceptions | `KHAHP-13.06A` · `KHAHP-13.06B` · `KHAHP-13.06C` |
| `13.07` | Module-load negative tests and compatibility exceptions | `KHAHP-13.07A` · `KHAHP-13.07B` · `KHAHP-13.07C` |

### 14 — Kernel Module Signing / DKMS

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** Secure Boot and signed Tirdad DKMS evidence were reconciled with the module-signing policy and accepted for the current baseline.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `14.01` | Loaded-module signer inventory | `KHAHP-14.01A` · `KHAHP-14.01B` · `KHAHP-14.01C` |
| `14.02` | DKMS package and built-module inventory | `KHAHP-14.02A` · `KHAHP-14.02B` · `KHAHP-14.02C` |
| `14.03` | tirdad DKMS build, signer and runtime state | `KHAHP-14.03A` · `KHAHP-14.03B` · `KHAHP-14.03C` |
| `14.04` | NVIDIA/other third-party module signer state | `KHAHP-14.04A` · `KHAHP-14.04B` · `KHAHP-14.04C` |
| `14.05` | Kernel module signature enforcement capability | `KHAHP-14.05A` · `KHAHP-14.05B` · `KHAHP-14.05C` |
| `14.06` | MOK/enrolled certificate readiness | `KHAHP-14.06A` · `KHAHP-14.06B` · `KHAHP-14.06C` |
| `14.07` | Secure-Boot compatibility and unsigned-module exceptions | `KHAHP-14.07A` · `KHAHP-14.07B` · `KHAHP-14.07C` |

### 15 — AppArmor / Mandatory Access Control

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** AppArmor is enabled broadly. Firefox retains the vendor unconfined placeholder as an explicit compatibility disposition; browser seccomp/privacy controls are retained. This is a documented project exception, not an open implementation gap.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `15.01` | AppArmor kernel/module enablement | `KHAHP-15.01A` · `KHAHP-15.01B` · `KHAHP-15.01C` |
| `15.02` | Profile inventory and parser status | `KHAHP-15.02A` · `KHAHP-15.02B` · `KHAHP-15.02C` |
| `15.03` | Enforce/complain/unconfined process counts | `KHAHP-15.03A` · `KHAHP-15.03B` · `KHAHP-15.03C` |
| `15.04` | Tor and network-service profile enforcement | `KHAHP-15.04A` · `KHAHP-15.04B` · `KHAHP-15.04C` |
| `15.05` | Browser/application profile coverage | `KHAHP-15.05A` · `KHAHP-15.05B` · `KHAHP-15.05C` |
| `15.06` | Denied-event review and false-positive handling | `KHAHP-15.06A` · `KHAHP-15.06B` · `KHAHP-15.06C` |
| `15.07` | USER versus SYSMAINT AppArmor behavior | `KHAHP-15.07A` · `KHAHP-15.07B` · `KHAHP-15.07C` |

### 16 — SUID / SGID / File Capabilities

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** SUID/SGID binaries and file capabilities were inventoried and reconciled against package ownership and compatibility requirements.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `16.01` | Complete SUID file inventory | `KHAHP-16.01A` · `KHAHP-16.01B` · `KHAHP-16.01C` |
| `16.02` | Complete SGID file inventory | `KHAHP-16.02A` · `KHAHP-16.02B` · `KHAHP-16.02C` |
| `16.03` | Package ownership of privileged binaries | `KHAHP-16.03A` · `KHAHP-16.03B` · `KHAHP-16.03C` |
| `16.04` | permission-hardener expected mode validation | `KHAHP-16.04A` · `KHAHP-16.04B` · `KHAHP-16.04C` |
| `16.05` | File-capability inventory and package attribution | `KHAHP-16.05A` · `KHAHP-16.05B` · `KHAHP-16.05C` |
| `16.06` | Unexpected privileged executable detection | `KHAHP-16.06A` · `KHAHP-16.06B` · `KHAHP-16.06C` |
| `16.07` | Privilege-binary negative/compatibility review | `KHAHP-16.07A` · `KHAHP-16.07B` · `KHAHP-16.07C` |

### 17 — Permissions / ACL / Umask

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** Permissions, ACL, umask and shared-directory controls were reconciled, including vendor-specific exceptions accepted by policy.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `17.01` | System file ownership baseline | `KHAHP-17.01A` · `KHAHP-17.01B` · `KHAHP-17.01C` |
| `17.02` | World-writable system path inventory | `KHAHP-17.02A` · `KHAHP-17.02B` · `KHAHP-17.02C` |
| `17.03` | Unexpected group-writable sensitive paths | `KHAHP-17.03A` · `KHAHP-17.03B` · `KHAHP-17.03C` |
| `17.04` | ACL inventory on sensitive configuration | `KHAHP-17.04A` · `KHAHP-17.04B` · `KHAHP-17.04C` |
| `17.05` | Root and user umask policy | `KHAHP-17.05A` · `KHAHP-17.05B` · `KHAHP-17.05C` |
| `17.06` | Home and evidence-directory permissions | `KHAHP-17.06A` · `KHAHP-17.06B` · `KHAHP-17.06C` |
| `17.07` | Sticky-bit and shared-directory permission policy | `KHAHP-17.07A` · `KHAHP-17.07B` · `KHAHP-17.07C` |

### 18 — PAM / Login / Faillock

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** PAM, yescrypt and login/lockout policy were reconciled with safe recovery requirements and accepted for the implementation baseline.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `18.01` | PAM stack package provenance | `KHAHP-18.01A` · `KHAHP-18.01B` · `KHAHP-18.01C` |
| `18.02` | password quality and hashing policy | `KHAHP-18.02A` · `KHAHP-18.02B` · `KHAHP-18.02C` |
| `18.03` | faillock/brute-force lockout policy | `KHAHP-18.03A` · `KHAHP-18.03B` · `KHAHP-18.03C` |
| `18.04` | login delay and retry controls | `KHAHP-18.04A` · `KHAHP-18.04B` · `KHAHP-18.04C` |
| `18.05` | su/sudo/polkit PAM interaction | `KHAHP-18.05A` · `KHAHP-18.05B` · `KHAHP-18.05C` |
| `18.06` | account aging and inactive-account policy | `KHAHP-18.06A` · `KHAHP-18.06B` · `KHAHP-18.06C` |
| `18.07` | USER/SYSMAINT login regression tests | `KHAHP-18.07A` · `KHAHP-18.07B` · `KHAHP-18.07C` |

### 19 — SSH Client / Server Security

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** Network SSH service exposure remains disabled in the normal USER baseline; client-side/key policy and local uses were separately classified.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `19.01` | Local SSH server service/socket state | `KHAHP-19.01A` · `KHAHP-19.01B` · `KHAHP-19.01C` |
| `19.02` | sshd listener and inbound port absence | `KHAHP-19.02A` · `KHAHP-19.02B` · `KHAHP-19.02C` |
| `19.03` | sshd_config security-misc policy if installed | `KHAHP-19.03A` · `KHAHP-19.03B` · `KHAHP-19.03C` |
| `19.04` | SSH client configuration and host-key verification | `KHAHP-19.04A` · `KHAHP-19.04B` · `KHAHP-19.04C` |
| `19.05` | Private-key ownership and permission baseline | `KHAHP-19.05A` · `KHAHP-19.05B` · `KHAHP-19.05C` |
| `19.06` | Password-authentication and root-login policy for future server use | `KHAHP-19.06A` · `KHAHP-19.06B` · `KHAHP-19.06C` |
| `19.07` | Known-hosts/key algorithm and crypto-policy review | `KHAHP-19.07A` · `KHAHP-19.07B` · `KHAHP-19.07C` |

### 20 — Enabled / Running Service Audit

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** Enabled/running services, sockets and listeners were reviewed per boot role; the accepted baseline avoids indiscriminate removal of required vendor services.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `20.01` | Enabled systemd service inventory | `KHAHP-20.01A` · `KHAHP-20.01B` · `KHAHP-20.01C` |
| `20.02` | Running systemd service inventory | `KHAHP-20.02A` · `KHAHP-20.02B` · `KHAHP-20.02C` |
| `20.03` | Socket/path/timer activated service inventory | `KHAHP-20.03A` · `KHAHP-20.03B` · `KHAHP-20.03C` |
| `20.04` | Kicksecure-required service attribution | `KHAHP-20.04A` · `KHAHP-20.04B` · `KHAHP-20.04C` |
| `20.05` | Unexpected or unnecessary service classification | `KHAHP-20.05A` · `KHAHP-20.05B` · `KHAHP-20.05C` |
| `20.06` | Listener-to-service ownership correlation | `KHAHP-20.06A` · `KHAHP-20.06B` · `KHAHP-20.06C` |
| `20.07` | Reboot persistence and failed-service review | `KHAHP-20.07A` · `KHAHP-20.07B` · `KHAHP-20.07C` |

### 21 — systemd Service Sandboxing

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** systemd service-sandboxing controls and compatibility limits were reconciled and accepted for the current service set.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `21.01` | systemd-analyze security baseline | `KHAHP-21.01A` · `KHAHP-21.01B` · `KHAHP-21.01C` |
| `21.02` | NoNewPrivileges adoption | `KHAHP-21.02A` · `KHAHP-21.02B` · `KHAHP-21.02C` |
| `21.03` | ProtectSystem/ProtectHome restrictions | `KHAHP-21.03A` · `KHAHP-21.03B` · `KHAHP-21.03C` |
| `21.04` | PrivateTmp/PrivateDevices isolation | `KHAHP-21.04A` · `KHAHP-21.04B` · `KHAHP-21.04C` |
| `21.05` | CapabilityBoundingSet and ambient capabilities | `KHAHP-21.05A` · `KHAHP-21.05B` · `KHAHP-21.05C` |
| `21.06` | RestrictNamespaces/SystemCallFilter/address-family controls | `KHAHP-21.06A` · `KHAHP-21.06B` · `KHAHP-21.06C` |
| `21.07` | Service-specific compatibility exceptions and regressions | `KHAHP-21.07A` · `KHAHP-21.07B` · `KHAHP-21.07C` |

### 22 — System.map / Core Dumps / PStore

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** Core-dump, pstore and crash-data privacy controls were reconciled with the owner-approved forensic/privacy trade-off.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `22.01` | System.map exposure and removal policy | `KHAHP-22.01A` · `KHAHP-22.01B` · `KHAHP-22.01C` |
| `22.02` | systemd-coredump configuration | `KHAHP-22.02A` · `KHAHP-22.02B` · `KHAHP-22.02C` |
| `22.03` | kernel.core_pattern effective state | `KHAHP-22.03A` · `KHAHP-22.03B` · `KHAHP-22.03C` |
| `22.04` | fs.suid_dumpable effective state | `KHAHP-22.04A` · `KHAHP-22.04B` · `KHAHP-22.04C` |
| `22.05` | pstore retention/disable policy | `KHAHP-22.05A` · `KHAHP-22.05B` · `KHAHP-22.05C` |
| `22.06` | EFI pstore and ERST boot controls | `KHAHP-22.06A` · `KHAHP-22.06B` · `KHAHP-22.06C` |
| `22.07` | Crash-evidence privacy versus diagnostic requirements | `KHAHP-22.07A` · `KHAHP-22.07B` · `KHAHP-22.07C` |

### 23 — Journald / Logging / Logrotate

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** Journal ownership, access, retention and time-ordering requirements were reconciled into the accepted logging baseline.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `23.01` | journald security-misc configuration | `KHAHP-23.01A` · `KHAHP-23.01B` · `KHAHP-23.01C` |
| `23.02` | Persistent versus volatile journal storage | `KHAHP-23.02A` · `KHAHP-23.02B` · `KHAHP-23.02C` |
| `23.03` | Journal file permissions and ownership | `KHAHP-23.03A` · `KHAHP-23.03B` · `KHAHP-23.03C` |
| `23.04` | Rate limiting and size/retention policy | `KHAHP-23.04A` · `KHAHP-23.04B` · `KHAHP-23.04C` |
| `23.05` | Forwarding/syslog integration state | `KHAHP-23.05A` · `KHAHP-23.05B` · `KHAHP-23.05C` |
| `23.06` | logrotate configuration and sensitive-log modes | `KHAHP-23.06A` · `KHAHP-23.06B` · `KHAHP-23.06C` |
| `23.07` | Log integrity, time coherence and reboot persistence | `KHAHP-23.07A` · `KHAHP-23.07B` · `KHAHP-23.07C` |

### 24 — Panic / Recovery / Emergency Shutdown

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** Panic, emergency shutdown and controlled recovery behavior were reconciled with owner-approved recovery requirements.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `24.01` | kernel panic-on-oops policy | `KHAHP-24.01A` · `KHAHP-24.01B` · `KHAHP-24.01C` |
| `24.02` | panic timeout and fail-closed behavior | `KHAHP-24.02A` · `KHAHP-24.02B` · `KHAHP-24.02C` |
| `24.03` | emerg-shutdown.service provenance and state | `KHAHP-24.03A` · `KHAHP-24.03B` · `KHAHP-24.03C` |
| `24.04` | rescue/emergency target restrictions | `KHAHP-24.04A` · `KHAHP-24.04B` · `KHAHP-24.04C` |
| `24.05` | rd.emergency=halt and rd.shell=0 behavior | `KHAHP-24.05A` · `KHAHP-24.05B` · `KHAHP-24.05C` |
| `24.06` | Magic SysRq and recovery-surface policy | `KHAHP-24.06A` · `KHAHP-24.06B` · `KHAHP-24.06C` |
| `24.07` | Controlled failure/recovery evidence and rollback | `KHAHP-24.07A` · `KHAHP-24.07B` · `KHAHP-24.07C` |

### 25 — RAM Wipe

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** Swap, RAM-wipe and shutdown-memory protections were reconciled with platform capability and recovery policy.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `25.01` | ram-wipe package provenance and version | `KHAHP-25.01A` · `KHAHP-25.01B` · `KHAHP-25.01C` |
| `25.02` | GRUB/package RAM-wipe source presence | `KHAHP-25.02A` · `KHAHP-25.02B` · `KHAHP-25.02C` |
| `25.03` | init_on_alloc/init_on_free live correlation | `KHAHP-25.03A` · `KHAHP-25.03B` · `KHAHP-25.03C` |
| `25.04` | Shutdown/reboot wipe hook inventory | `KHAHP-25.04A` · `KHAHP-25.04B` · `KHAHP-25.04C` |
| `25.05` | Swap/LUKS interaction during shutdown | `KHAHP-25.05A` · `KHAHP-25.05B` · `KHAHP-25.05C` |
| `25.06` | Controlled reboot/shutdown persistence test | `KHAHP-25.06A` · `KHAHP-25.06B` · `KHAHP-25.06C` |
| `25.07` | Limitations of software RAM wiping and cold-boot scope | `KHAHP-25.07A` · `KHAHP-25.07B` · `KHAHP-25.07C` |

### 26 — USBGuard / Peripheral Security

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** USBGuard policy retains authorized keyboards, mice and recovery/removable storage while controlling unapproved device classes according to owner policy.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `26.01` | usbguard daemon and DBus service state | `KHAHP-26.01A` · `KHAHP-26.01B` · `KHAHP-26.01C` |
| `26.02` | Policy files and rule provenance | `KHAHP-26.02A` · `KHAHP-26.02B` · `KHAHP-26.02C` |
| `26.03` | ImplicitPolicyTarget and device-policy settings | `KHAHP-26.03A` · `KHAHP-26.03B` · `KHAHP-26.03C` |
| `26.04` | Allowed keyboard/mouse/audio/video/storage classes | `KHAHP-26.04A` · `KHAHP-26.04B` · `KHAHP-26.04C` |
| `26.05` | Rejected HID+extra and RNDIS/network-device patterns | `KHAHP-26.05A` · `KHAHP-26.05B` · `KHAHP-26.05C` |
| `26.06` | IPC authorization/notifier behavior | `KHAHP-26.06A` · `KHAHP-26.06B` · `KHAHP-26.06C` |
| `26.07` | Hot-plug negative tests and reboot persistence | `KHAHP-26.07A` · `KHAHP-26.07B` · `KHAHP-26.07C` |

### 27 — NetworkManager / Wi-Fi / MAC / DHCP

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** Network identity and MAC/DHCP privacy controls were reconciled for the accepted operating model.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `27.01` | NetworkManager package/service state | `KHAHP-27.01A` · `KHAHP-27.01B` · `KHAHP-27.01C` |
| `27.02` | Saved Wi-Fi profile inventory and autoconnect | `KHAHP-27.02A` · `KHAHP-27.02B` · `KHAHP-27.02C` |
| `27.03` | Active-profile cloned-MAC and DHCP privacy settings | `KHAHP-27.03A` · `KHAHP-27.03B` · `KHAHP-27.03C` |
| `27.04` | Scan MAC randomization | `KHAHP-27.04A` · `KHAHP-27.04B` · `KHAHP-27.04C` |
| `27.05` | Ethernet MAC randomization policy | `KHAHP-27.05A` · `KHAHP-27.05B` · `KHAHP-27.05C` |
| `27.06` | Runtime MAC versus permanent hardware MAC | `KHAHP-27.06A` · `KHAHP-27.06B` · `KHAHP-27.06C` |
| `27.07` | DHCP client identifier and profile persistence | `KHAHP-27.07A` · `KHAHP-27.07B` · `KHAHP-27.07C` |

### 28 — IPv6 Policy

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** IPv6 policy is explicit in the hardened baseline; profile behavior and DNS interactions are treated according to the selected operating mode.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `28.01` | ipv6.disable=1 boot parameter | `KHAHP-28.01A` · `KHAHP-28.01B` · `KHAHP-28.01C` |
| `28.02` | Absence of IPv6 addresses | `KHAHP-28.02A` · `KHAHP-28.02B` · `KHAHP-28.02C` |
| `28.03` | Absence of IPv6 routes | `KHAHP-28.03A` · `KHAHP-28.03B` · `KHAHP-28.03C` |
| `28.04` | NetworkManager IPv6 method/state | `KHAHP-28.04A` · `KHAHP-28.04B` · `KHAHP-28.04C` |
| `28.05` | Resolver absence of IPv6 nameservers | `KHAHP-28.05A` · `KHAHP-28.05B` · `KHAHP-28.05C` |
| `28.06` | IPv6 TCP/UDP listener exposure | `KHAHP-28.06A` · `KHAHP-28.06B` · `KHAHP-28.06C` |
| `28.07` | Reboot persistence and DNS/HTTPS regression test | `KHAHP-28.07A` · `KHAHP-28.07B` · `KHAHP-28.07C` |

### 29 — Unbound / Local DNS Architecture

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** Unbound is the accepted local resolver path in normal USER mode, with role-specific service semantics reconciled.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `29.01` | Unbound package/service state | `KHAHP-29.01A` · `KHAHP-29.01B` · `KHAHP-29.01C` |
| `29.02` | 127.0.0.1:53 UDP/TCP listener and non-loopback absence | `KHAHP-29.02A` · `KHAHP-29.02B` · `KHAHP-29.02C` |
| `29.03` | resolv.conf local-resolver wiring | `KHAHP-29.03A` · `KHAHP-29.03B` · `KHAHP-29.03C` |
| `29.04` | NetworkManager effective DNS assignment | `KHAHP-29.04A` · `KHAHP-29.04B` · `KHAHP-29.04C` |
| `29.05` | Unbound configuration include tree validation | `KHAHP-29.05A` · `KHAHP-29.05B` · `KHAHP-29.05C` |
| `29.06` | DoT forward-zone and IPv6 source policy | `KHAHP-29.06A` · `KHAHP-29.06B` · `KHAHP-29.06C` |
| `29.07` | USER/SYSMAINT service behavior and persistence | `KHAHP-29.07A` · `KHAHP-29.07B` · `KHAHP-29.07C` |

### 30 — DNSSEC / DoT / DNS Leak Prevention

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** DNSSEC validation, authenticated DNS-over-TLS configuration, direct DNS egress policy and browser DNS behavior were reconciled into the accepted DNS architecture.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `30.01` | DNSSEC positive validation test | `KHAHP-30.01A` · `KHAHP-30.01B` · `KHAHP-30.01C` |
| `30.02` | Broken-DNSSEC negative test | `KHAHP-30.02A` · `KHAHP-30.02B` · `KHAHP-30.02C` |
| `30.03` | DoT forwarding configuration and reachability scope | `KHAHP-30.03A` · `KHAHP-30.03B` · `KHAHP-30.03C` |
| `30.04` | Plaintext external UDP/53 block | `KHAHP-30.04A` · `KHAHP-30.04B` · `KHAHP-30.04C` |
| `30.05` | Plaintext external TCP/53 block | `KHAHP-30.05A` · `KHAHP-30.05B` · `KHAHP-30.05C` |
| `30.06` | Local DNS functionality after firewall enforcement | `KHAHP-30.06A` · `KHAHP-30.06B` · `KHAHP-30.06C` |
| `30.07` | DNS leak/bypass and reboot-persistence testing | `KHAHP-30.07A` · `KHAHP-30.07B` · `KHAHP-30.07C` |

### 31 — nftables Firewall

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** nftables policy and persistence are part of the accepted firewall baseline, including the project DNS-egress restrictions.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `31.01` | nftables package/service/runtime ruleset state | `KHAHP-31.01A` · `KHAHP-31.01B` · `KHAHP-31.01C` |
| `31.02` | Dedicated inet kicksecure_hardening table | `KHAHP-31.02A` · `KHAHP-31.02B` · `KHAHP-31.02C` |
| `31.03` | Input default-drop policy | `KHAHP-31.03A` · `KHAHP-31.03B` · `KHAHP-31.03C` |
| `31.04` | Forward default-drop policy | `KHAHP-31.04A` · `KHAHP-31.04B` · `KHAHP-31.04C` |
| `31.05` | Loopback, established/related and invalid handling | `KHAHP-31.05A` · `KHAHP-31.05B` · `KHAHP-31.05C` |
| `31.06` | DHCP/ICMP and required inbound exceptions | `KHAHP-31.06A` · `KHAHP-31.06B` · `KHAHP-31.06C` |
| `31.07` | Static syntax, reload safety and reboot persistence | `KHAHP-31.07A` · `KHAHP-31.07B` · `KHAHP-31.07C` |

### 32 — LAN Discovery / Multicast / LLMNR / mDNS

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** Local discovery exposure was reviewed and reconciled against the selected privacy posture.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `32.01` | Avahi/mDNS daemon state | `KHAHP-32.01A` · `KHAHP-32.01B` · `KHAHP-32.01C` |
| `32.02` | LLMNR/resolved multicast name-resolution state | `KHAHP-32.02A` · `KHAHP-32.02B` · `KHAHP-32.02C` |
| `32.03` | wsdd/Samba discovery state | `KHAHP-32.03A` · `KHAHP-32.03B` · `KHAHP-32.03C` |
| `32.04` | rpcbind/minidlna/UPnP service state | `KHAHP-32.04A` · `KHAHP-32.04B` · `KHAHP-32.04C` |
| `32.05` | Multicast/discovery TCP+UDP listener inventory | `KHAHP-32.05A` · `KHAHP-32.05B` · `KHAHP-32.05C` |
| `32.06` | Firewall exposure of discovery ports | `KHAHP-32.06A` · `KHAHP-32.06B` · `KHAHP-32.06C` |
| `32.07` | Negative LAN discovery and reboot-persistence test | `KHAHP-32.07A` · `KHAHP-32.07B` · `KHAHP-32.07C` |

### 33 — Tor / SOCKS / DNS Isolation

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** Tor / SOCKS routing policy and intended application scope were reconciled with the project network-privacy model.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `33.01` | Tor package/service state | `KHAHP-33.01A` · `KHAHP-33.01B` · `KHAHP-33.01C` |
| `33.02` | SOCKS listener 127.0.0.1:9050 and non-loopback absence | `KHAHP-33.02A` · `KHAHP-33.02B` · `KHAHP-33.02C` |
| `33.03` | Tor configuration provenance and syntax validation | `KHAHP-33.03A` · `KHAHP-33.03B` · `KHAHP-33.03C` |
| `33.04` | Application proxy routing where intended | `KHAHP-33.04A` · `KHAHP-33.04B` · `KHAHP-33.04C` |
| `33.05` | Tor DNS isolation behavior | `KHAHP-33.05A` · `KHAHP-33.05B` · `KHAHP-33.05C` |
| `33.06` | Clearnet bypass classification for Tor-mode applications | `KHAHP-33.06A` · `KHAHP-33.06B` · `KHAHP-33.06C` |
| `33.07` | Bootstrap, circuit, restart and failure-mode behavior | `KHAHP-33.07A` · `KHAHP-33.07B` · `KHAHP-33.07C` |

### 34 — sdwdate / Secure Time / Boot Clock

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** Secure-time services and chronology behavior were reconciled into the accepted baseline.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `34.01` | sdwdate package/service state | `KHAHP-34.01A` · `KHAHP-34.01B` · `KHAHP-34.01C` |
| `34.02` | timesanitycheck execution state | `KHAHP-34.02A` · `KHAHP-34.02B` · `KHAHP-34.02C` |
| `34.03` | bootclockrandomization execution state | `KHAHP-34.03A` · `KHAHP-34.03B` · `KHAHP-34.03C` |
| `34.04` | System clock sanity metadata | `KHAHP-34.04A` · `KHAHP-34.04B` · `KHAHP-34.04C` |
| `34.05` | NTP/systemd-timesyncd conflicts | `KHAHP-34.05A` · `KHAHP-34.05B` · `KHAHP-34.05C` |
| `34.06` | USER versus SYSMAINT time-source behavior | `KHAHP-34.06A` · `KHAHP-34.06B` · `KHAHP-34.06C` |
| `34.07` | Time rollback/jump detection and log coherence | `KHAHP-34.07A` · `KHAHP-34.07B` · `KHAHP-34.07C` |

### 35 — Entropy / RNG

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** Entropy, random-seed and early-boot randomness controls were reconciled as part of the accepted cryptographic baseline.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `35.01` | Kernel RNG readiness at boot | `KHAHP-35.01A` · `KHAHP-35.01B` · `KHAHP-35.01C` |
| `35.02` | haveged package/service state | `KHAHP-35.02A` · `KHAHP-35.02B` · `KHAHP-35.02C` |
| `35.03` | jitterentropy-rngd package/service state | `KHAHP-35.03A` · `KHAHP-35.03B` · `KHAHP-35.03C` |
| `35.04` | random.trust_cpu boot policy | `KHAHP-35.04A` · `KHAHP-35.04B` · `KHAHP-35.04C` |
| `35.05` | random.trust_bootloader boot policy | `KHAHP-35.05A` · `KHAHP-35.05B` · `KHAHP-35.05C` |
| `35.06` | Entropy source and /dev/random behavior | `KHAHP-35.06A` · `KHAHP-35.06B` · `KHAHP-35.06C` |
| `35.07` | Early-boot entropy persistence and regression evidence | `KHAHP-35.07A` · `KHAHP-35.07B` · `KHAHP-35.07C` |

### 36 — Browser DoH / WebRTC / Telemetry

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** Firefox DoH, WebRTC, telemetry, prefetch and related privacy controls were reconciled and accepted for the hardened browser baseline.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `36.01` | Browser DNS-over-HTTPS/TRR setting | `KHAHP-36.01A` · `KHAHP-36.01B` · `KHAHP-36.01C` |
| `36.02` | Browser proxy DNS routing behavior | `KHAHP-36.02A` · `KHAHP-36.02B` · `KHAHP-36.02C` |
| `36.03` | WebRTC/STUN local/public IP exposure | `KHAHP-36.03A` · `KHAHP-36.03B` · `KHAHP-36.03C` |
| `36.04` | Telemetry and crash-report settings | `KHAHP-36.04A` · `KHAHP-36.04B` · `KHAHP-36.04C` |
| `36.05` | Safe browsing/prediction/background network features | `KHAHP-36.05A` · `KHAHP-36.05B` · `KHAHP-36.05C` |
| `36.06` | Extension/add-on inventory and trust | `KHAHP-36.06A` · `KHAHP-36.06B` · `KHAHP-36.06C` |
| `36.07` | Browser update, profile persistence and leak tests | `KHAHP-36.07A` · `KHAHP-36.07B` · `KHAHP-36.07C` |

### 37 — Application / File / Metadata Privacy

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** Thumbnail generation is disabled and persisted across reboot; application-history/metadata handling was reconciled into the accepted desktop privacy baseline.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `37.01` | Desktop search/indexing services | `KHAHP-37.01A` · `KHAHP-37.01B` · `KHAHP-37.01C` |
| `37.02` | Thumbnail and preview cache behavior | `KHAHP-37.02A` · `KHAHP-37.02B` · `KHAHP-37.02C` |
| `37.03` | Recent-files/history and clipboard retention | `KHAHP-37.03A` · `KHAHP-37.03B` · `KHAHP-37.03C` |
| `37.04` | Document/image metadata handling | `KHAHP-37.04A` · `KHAHP-37.04B` · `KHAHP-37.04C` |
| `37.05` | Temporary-file and application-cache exposure | `KHAHP-37.05A` · `KHAHP-37.05B` · `KHAHP-37.05C` |
| `37.06` | Sandboxed versus unsandboxed application inventory | `KHAHP-37.06A` · `KHAHP-37.06B` · `KHAHP-37.06C` |
| `37.07` | Metadata-removal workflow and regression testing | `KHAHP-37.07A` · `KHAHP-37.07B` · `KHAHP-37.07C` |

### 38 — Camera / Microphone / Power / Screen Lock

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** Camera/microphone USER denial, Bluetooth blocking, screen-lock behavior and peripheral privacy controls were reconciled under owner policy.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `38.01` | Camera hardware/device exposure | `KHAHP-38.01A` · `KHAHP-38.01B` · `KHAHP-38.01C` |
| `38.02` | Microphone hardware/device exposure | `KHAHP-38.02A` · `KHAHP-38.02B` · `KHAHP-38.02C` |
| `38.03` | Bluetooth/rfkill interaction with peripherals | `KHAHP-38.03A` · `KHAHP-38.03B` · `KHAHP-38.03C` |
| `38.04` | Screen-lock timeout and authentication | `KHAHP-38.04A` · `KHAHP-38.04B` · `KHAHP-38.04C` |
| `38.05` | Suspend/lock-on-lid and idle behavior | `KHAHP-38.05A` · `KHAHP-38.05B` · `KHAHP-38.05C` |
| `38.06` | Hibernation configuration and encrypted-swap implications | `KHAHP-38.06A` · `KHAHP-38.06B` · `KHAHP-38.06C` |
| `38.07` | Shutdown-versus-suspend operational policy | `KHAHP-38.07A` · `KHAHP-38.07B` · `KHAHP-38.07C` |

### 39 — Firmware / BIOS / Secure Boot / TPM

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** OWNER-COMPLETE / NO RETEST. BIOS/UEFI work is retained as a completed owner-controlled domain; Secure Boot evidence remains part of the project record.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `39.01` | BIOS/UEFI vendor, model and firmware version | `KHAHP-39.01A` · `KHAHP-39.01B` · `KHAHP-39.01C` |
| `39.02` | fwupd device/security-attribute inventory | `KHAHP-39.02A` · `KHAHP-39.02B` · `KHAHP-39.02C` |
| `39.03` | Secure Boot state and Setup Mode | `KHAHP-39.03A` · `KHAHP-39.03B` · `KHAHP-39.03C` |
| `39.04` | TPM presence, version and ownership state | `KHAHP-39.04A` · `KHAHP-39.04B` · `KHAHP-39.04C` |
| `39.05` | BIOS/UEFI administrator password manual check | `KHAHP-39.05A` · `KHAHP-39.05B` · `KHAHP-39.05C` |
| `39.06` | PXE/CSM/external-boot/manual boot- order policy | `KHAHP-39.06A` · `KHAHP-39.06B` · `KHAHP-39.06C` |
| `39.07` | Firmware update, DKMS/MOK and Secure-Boot readiness | `KHAHP-39.07A` · `KHAHP-39.07B` · `KHAHP-39.07C` |

### 40 — Auditd / AIDE / Integrity Monitoring

**Status:** **PROJECT ACCEPTED - COMPLETE / NO OPEN IMPLEMENTATION GAP.**

**Evidence position:** FINAL ACCEPTANCE COMPLETE. In normal USER boot, auditd is enabled/active with the KHAHP rules effectively loaded, zero lost audit records in the acceptance capture, and persistent rule compilation verified. The production AIDE scheduled service completed successfully with exit status 0 after the dotlockfile permission repair; dailyaidecheck.timer remains enabled. SYSMAINT no-rules observations were correctly identified as boot-role behavior because auditd is inactive there.

**Acceptance:** All 21 A/B/C checkpoints for this section are accepted within the KHAHP 01-40 closeout. Re-test after material change; this does not imply third-party certification.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `40.01` | auditd package/service state | `KHAHP-40.01A` · `KHAHP-40.01B` · `KHAHP-40.01C` |
| `40.02` | Audit rule inventory and immutable/finalize policy | `KHAHP-40.02A` · `KHAHP-40.02B` · `KHAHP-40.02C` |
| `40.03` | Privileged-command and identity- change audit coverage | `KHAHP-40.03A` · `KHAHP-40.03B` · `KHAHP-40.03C` |
| `40.04` | AIDE package/database/configuration state | `KHAHP-40.04A` · `KHAHP-40.04B` · `KHAHP-40.04C` |
| `40.05` | File-integrity baseline and scheduled checks | `KHAHP-40.05A` · `KHAHP-40.05B` · `KHAHP-40.05C` |
| `40.06` | Audit-log ownership, rotation and tamper resistance | `KHAHP-40.06A` · `KHAHP-40.06B` · `KHAHP-40.06C` |
| `40.07` | CIS/DISA accountability-gap analysis | `KHAHP-40.07A` · `KHAHP-40.07B` · `KHAHP-40.07C` |

### 41 — Cron / Timers / Persistence / Supply Chain

**Status:** **NEXT PHASE - RECONNAISSANCE / IMPLEMENTATION NOT YET COMPLETE.**

**Evidence position:** Persistence, scheduled activity and software supply-chain attribution form the first remaining final-assurance phase.

**Required completion:** Complete reconnaissance for this section, implement/accept applicable hardening decisions, then execute and accept its 21 A/B/C checkpoints before declaring the full 44-section program complete.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `41.01` | cron/anacron job inventory | `KHAHP-41.01A` · `KHAHP-41.01B` · `KHAHP-41.01C` |
| `41.02` | systemd timer inventory | `KHAHP-41.02A` · `KHAHP-41.02B` · `KHAHP-41.02C` |
| `41.03` | User autostart and desktop persistence inventory | `KHAHP-41.03A` · `KHAHP-41.03B` · `KHAHP-41.03C` |
| `41.04` | Package repository and signing-key provenance | `KHAHP-41.04A` · `KHAHP-41.04B` · `KHAHP-41.04C` |
| `41.05` | APT pinning/holds and update-policy review | `KHAHP-41.05A` · `KHAHP-41.05B` · `KHAHP-41.05C` |
| `41.06` | Unexpected startup scripts/services/modules | `KHAHP-41.06A` · `KHAHP-41.06B` · `KHAHP-41.06C` |
| `41.07` | Supply-chain drift and reboot- persistence evidence | `KHAHP-41.07A` · `KHAHP-41.07B` · `KHAHP-41.07C` |

### 42 — Credentials / SSH Keys / Secrets / Backup

**Status:** **NEXT PHASE - RECONNAISSANCE / IMPLEMENTATION NOT YET COMPLETE.**

**Evidence position:** Credentials, secret handling, encrypted backup and isolated recovery form the second remaining final-assurance phase.

**Required completion:** Complete reconnaissance for this section, implement/accept applicable hardening decisions, then execute and accept its 21 A/B/C checkpoints before declaring the full 44-section program complete.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `42.01` | SSH private-key inventory and permissions | `KHAHP-42.01A` · `KHAHP-42.01B` · `KHAHP-42.01C` |
| `42.02` | API/token/secret storage locations | `KHAHP-42.02A` · `KHAHP-42.02B` · `KHAHP-42.02C` |
| `42.03` | Password-manager selection and vault policy | `KHAHP-42.03A` · `KHAHP-42.03B` · `KHAHP-42.03C` |
| `42.04` | FIDO2/YubiKey readiness and hardware-backed keys | `KHAHP-42.04A` · `KHAHP-42.04B` · `KHAHP-42.04C` |
| `42.05` | Recovery-code generation and offline storage | `KHAHP-42.05A` · `KHAHP-42.05B` · `KHAHP-42.05C` |
| `42.06` | Encrypted backup creation and retention | `KHAHP-42.06A` · `KHAHP-42.06B` · `KHAHP-42.06C` |
| `42.07` | Restore test, key recovery and disaster-recovery evidence | `KHAHP-42.07A` · `KHAHP-42.07B` · `KHAHP-42.07C` |

### 43 — CIS / DISA GPOS / KSPP Mapping

**Status:** **NEXT PHASE - RECONNAISSANCE / IMPLEMENTATION NOT YET COMPLETE.**

**Evidence position:** Detailed CIS Debian 13 Level 2, DISA GPOS/SRG and KSPP applicability mapping remains to be completed without claiming external certification.

**Required completion:** Complete reconnaissance for this section, implement/accept applicable hardening decisions, then execute and accept its 21 A/B/C checkpoints before declaring the full 44-section program complete.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `43.01` | CIS Debian 13 Level 2 applicability mapping | `KHAHP-43.01A` · `KHAHP-43.01B` · `KHAHP-43.01C` |
| `43.02` | DISA GPOS/SRG objective mapping | `KHAHP-43.02A` · `KHAHP-43.02B` · `KHAHP-43.02C` |
| `43.03` | KSPP/kernel-self-protection mapping | `KHAHP-43.03A` · `KHAHP-43.03B` · `KHAHP-43.03C` |
| `43.04` | Kicksecure-native equivalent control mapping | `KHAHP-43.04A` · `KHAHP-43.04B` · `KHAHP-43.04C` |
| `43.05` | Project-extension control mapping | `KHAHP-43.05A` · `KHAHP-43.05B` · `KHAHP-43.05C` |
| `43.06` | Exception/N-A/manual-control rationale | `KHAHP-43.06A` · `KHAHP-43.06B` · `KHAHP-43.06C` |
| `43.07` | Evidence citation and no-certification disclaimer | `KHAHP-43.07A` · `KHAHP-43.07B` · `KHAHP-43.07C` |

### 44 — Final Acceptance / Evidence / Scoring

**Status:** **NEXT PHASE - RECONNAISSANCE / IMPLEMENTATION NOT YET COMPLETE.**

**Evidence position:** Whole-program regression, recovery, evidence-chain and final acceptance remain the final project phase.

**Required completion:** Complete reconnaissance for this section, implement/accept applicable hardening decisions, then execute and accept its 21 A/B/C checkpoints before declaring the full 44-section program complete.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `44.01` | Full reboot persistence acceptance | `KHAHP-44.01A` · `KHAHP-44.01B` · `KHAHP-44.01C` |
| `44.02` | USER-mode regression acceptance | `KHAHP-44.02A` · `KHAHP-44.02B` · `KHAHP-44.02C` |
| `44.03` | SYSMAINT-mode regression acceptance | `KHAHP-44.03A` · `KHAHP-44.03B` · `KHAHP-44.03C` |
| `44.04` | Network/DNS/firewall/Tor/USB negative-test acceptance | `KHAHP-44.04A` · `KHAHP-44.04B` · `KHAHP-44.04C` |
| `44.05` | Recovery/rollback/backup acceptance | `KHAHP-44.05A` · `KHAHP-44.05B` · `KHAHP-44.05C` |
| `44.06` | Evidence completeness, hashes and chain-of-custody bundle | `KHAHP-44.06A` · `KHAHP-44.06B` · `KHAHP-44.06C` |
| `44.07` | Final scorecard, residual risk and operator sign-off | `KHAHP-44.07A` · `KHAHP-44.07B` · `KHAHP-44.07C` |

## 6. Historical 01-38 action reconciliation - 63 records closed

The 63 inherited action records are retained for traceability. They are **not 63 vulnerabilities** and they are no longer an open implementation backlog. Under the 19 October 2026 project closeout they are resolved, accepted, superseded, or closed by an explicit policy/compatibility disposition within Sections 01-40.

| ID | Sec. | Historical engineering issue | v5.0 disposition |
|---|---:|---|---|
| `U01-001` | 7 | /tmp and /dev/shm noexec compatibility decision | **CLOSED / PROJECT ACCEPTED** |
| `U01-002` | 7 | /boot/efi-before-/boot fstab ordering review | **CLOSED / PROJECT ACCEPTED** |
| `U01-003` | 2 | permission-hardener package/provenance classifier | **CLOSED / PROJECT ACCEPTED** |
| `U01-004` | 5 | sync account shell classification | **CLOSED / PROJECT ACCEPTED** |
| `U01-005` | 12 | Unverified kernel tokens / CFI-KCFI claims | **CLOSED / PROJECT ACCEPTED** |
| `U01-006` | 13 | vesafb module applicability / dry-run review | **CLOSED / PROJECT ACCEPTED** |
| `U01-007` | 14 | USER versus SYSMAINT DKMS evidence reconciliation | **CLOSED / PROJECT ACCEPTED** |
| `U01-008` | 8 | Physical GRUB edit-denial test | **CLOSED / PROJECT ACCEPTED** |
| `U01-009` | 6 | LUKS key recovery and backup restore | **CLOSED / PROJECT ACCEPTED** |
| `U01-010` | 10 | Firmware/preboot DMA protection acceptance | **CLOSED / PROJECT ACCEPTED** |
| `U01-011` | 7 | Post-reboot SYSMAINT persistence evidence | **CLOSED / PROJECT ACCEPTED** |
| `U01-012` | 7 | /home, /var/tmp and noexec compatibility review | **CLOSED / PROJECT ACCEPTED** |
| `U01-013` | 14 | Signed-module negative test and update regression | **CLOSED / PROJECT ACCEPTED** |
| `U01-014` | 7 | /tmp nodev,nosuid hardening — implemented baseline | **CLOSED / PROJECT ACCEPTED** |
| `U15-001` | 15 | Strict Firefox AppArmor confinement is not established | **CLOSED / PROJECT ACCEPTED** |
| `U15-002` | 15 | AppArmor service policy and denial regression | **CLOSED / PROJECT ACCEPTED** |
| `U15-003` | 15 | USER versus SYSMAINT browser-label persistence | **CLOSED / PROJECT ACCEPTED** |
| `U15-004` | 16 | Privileged binary provenance/drift review | **CLOSED / PROJECT ACCEPTED** |
| `U15-005` | 16 | gst-ptp-helper capability policy/compatibility | **CLOSED / PROJECT ACCEPTED** |
| `U15-006` | 17 | setup-dist status-files 0777 exception monitoring | **CLOSED / PROJECT ACCEPTED** |
| `U15-007` | 17 | Sensitive directory/ACL/umask and tmpfs drift | **CLOSED / PROJECT ACCEPTED** |
| `U15-008` | 18 | faillock recovery and self-lockout policy | **CLOSED / PROJECT ACCEPTED** |
| `U15-009` | 18 | Passphrase/aging policy ownership | **CLOSED / PROJECT ACCEPTED** |
| `U15-010` | 18 | PAM USER/SYSMAINT interaction regression | **CLOSED / PROJECT ACCEPTED** |
| `U15-011` | 19 | Network SSH masking and listener persistence | **CLOSED / PROJECT ACCEPTED** |
| `U15-012` | 19 | Local SSH AF_UNIX socket and client key policy | **CLOSED / PROJECT ACCEPTED** |
| `U15-013` | 20 | Role-specific systemd service drift and listening sockets | **CLOSED / PROJECT ACCEPTED** |
| `U15-014` | 20 | Classify unexpected/unused services safely | **CLOSED / PROJECT ACCEPTED** |
| `U15-015` | 21 | Unbound systemd exposure score needs design decision | **CLOSED / PROJECT ACCEPTED** |
| `U15-016` | 21 | Service sandbox capability regression | **CLOSED / PROJECT ACCEPTED** |
| `U15-017` | 22 | Core dump/pstore suppression drift | **CLOSED / PROJECT ACCEPTED** |
| `U15-018` | 22 | Crash-forensics versus privacy trade-off | **CLOSED / PROJECT ACCEPTED** |
| `U15-019` | 23 | Journal retention, permissions and rotation policy | **CLOSED / PROJECT ACCEPTED** |
| `U15-020` | 23 | sdwdate time and journal chronology after reboot | **CLOSED / PROJECT ACCEPTED** |
| `U15-021` | 24 | Owner-approved panic/recovery policy and escape paths | **CLOSED / PROJECT ACCEPTED** |
| `U15-022` | 24 | Emergency shutdown and controlled recovery evidence | **CLOSED / PROJECT ACCEPTED** |
| `U25-001` | 26 | External USB keyboard possibly allowed | **CLOSED / PROJECT ACCEPTED** |
| `U25-002` | 26 | Composite/USB network rejection and persistence | **CLOSED / PROJECT ACCEPTED** |
| `U25-003` | 25 | Swap crypt mapping and shutdown key lifecycle | **CLOSED / PROJECT ACCEPTED** |
| `U25-004` | 25 | RAM wipe shutdown execution and hardware limits | **CLOSED / PROJECT ACCEPTED** |
| `U25-005` | 27 | Actual Wi-Fi MAC identity | **CLOSED / PROJECT ACCEPTED** |
| `U25-006` | 27 | DHCP identity rotation | **CLOSED / PROJECT ACCEPTED** |
| `U25-007` | 28 | Alternate IPv6 network profiles | **CLOSED / PROJECT ACCEPTED** |
| `U25-008` | 29 | Unbound response to DHCP renew/network loss | **CLOSED / PROJECT ACCEPTED** |
| `U25-009` | 30 | Unbound-owned authenticated DoT | **CLOSED / PROJECT ACCEPTED** |
| `U25-010` | 30 | Direct UDP/TCP 53 egress | **CLOSED / PROJECT ACCEPTED** |
| `U25-011` | 30 | Active browser DNS/DoH preferences | **CLOSED / PROJECT ACCEPTED** |
| `U25-012` | 31 | Effective firewall output chain | **CLOSED / PROJECT ACCEPTED** |
| `U25-013` | 31 | Exact loaded-ruleset persistence | **CLOSED / PROJECT ACCEPTED** |
| `U25-014` | 32 | Peer-side discovery proof | **CLOSED / PROJECT ACCEPTED** |
| `U25-015` | 33 | Tor Browser routing/DNS/fail-close | **CLOSED / PROJECT ACCEPTED** |
| `U25-016` | 34 | Secure-time unit chronology | **CLOSED / PROJECT ACCEPTED** |
| `U25-017` | 25 | Original implementation provenance | **CLOSED / PROJECT ACCEPTED** |
| `U25-018` | 26 | USB boot media usability versus detection | **CLOSED / PROJECT ACCEPTED** |
| `U25-019` | 28 | IPv6 goal mismatch / explicit policy | **CLOSED / PROJECT ACCEPTED** |
| `U25-020` | 29 | USER/SYSMAINT service role semantics | **CLOSED / PROJECT ACCEPTED** |
| `U25-021` | 30 | DNSSEC positive/negative evidence signoff | **CLOSED / PROJECT ACCEPTED** |
| `U25-022` | 32 | Actual scope of local discovery services | **CLOSED / PROJECT ACCEPTED** |
| `U25-023` | 34 | Production clock rollback exception | **CLOSED / PROJECT ACCEPTED** |
| `U35-001` | 35 | Early-boot entropy and random-seed lifecycle | **CLOSED / PROJECT ACCEPTED** |
| `U35-002` | 36 | Firefox effective DoH, WebRTC and telemetry behavior | **CLOSED / PROJECT ACCEPTED** |
| `U35-003` | 37 | Application history, thumbnails, metadata and confinement regression | **CLOSED / PROJECT ACCEPTED** |
| `U35-004` | 38 | Camera/microphone hotplug and real lock/lid-resume enforcement | **CLOSED / PROJECT ACCEPTED** |

## 7. Commercial image engineering and supply-chain acceptance

The proposed KHAHP premium hardened OS remains a separate **release-engineering** workstream from the completed 01-40 laptop baseline. Any distributable ISO/USB, QCOW2/KVM or OVA image must be built cleanly and must not clone development-machine secrets, SSH material, random seeds or unique machine identities.

### Clean-image common requirements

| Release area | Required release proof |
|---|---|
| Reproducible source / package provenance | Rebuildable source chain, package-origin verification and isolated build process |
| Identity / credential sanitation | Unique machine identity, host keys and zero copied development credentials |
| Network / DNS / firewall defaults | Safe first-boot policy with documented recovery and customer configuration path |
| Kernel / MAC / audit / AIDE | Release-specific regression, not merely reuse of laptop evidence |
| Update / backup / restore | Supported update path, rollback and recovery validation |
| Release signing / documentation | Signed artifacts, hashes, licensing and operator guidance |

### Distribution-specific acceptance

- **Physical ISO / USB:** UEFI boot, fresh encrypted installation, recovery, Secure Boot, storage/device safety and two-device comparison.
- **KVM / QCOW2:** clean import/boot, unique clone identity, virtual firmware/TPM, snapshot restore, networking and sanitized release image.
- **VirtualBox / OVA:** clean import, identity regeneration, clipboard/shared-folder/USB/network policy, restore and host-version support.

## 8. Planned completion of Sections 41-44

| Section | Remaining work | Checkpoints |
|---|---|---:|
| **41 - Persistence / supply chain** | Cron/timers/autostart classification, package/signing provenance and drift | **21** |
| **42 - Credentials / backup / recovery** | Secret inventory, custody policy, encrypted backups and isolated restore | **21** |
| **43 - CIS / DISA / KSPP mapping** | Evidence-linked applicability and extension mapping; no certification inflation | **21** |
| **44 - Final acceptance / evidence / scoring** | Whole-program regression, recovery, chain of custody and final sign-off | **21** |
| **Total remaining** |  | **84** |

## 9. Compliance, controlled change and public disclosure

**Execution roles:** normal USER activity remains separate from privileged SYSMAINT maintenance. Privileged work must preserve role boundaries and recovery paths.

**Change discipline:** evidence -> root cause -> minimal approved change -> backup/rollback -> postflight -> bounded negative test -> relevant persistence/recovery -> acceptance.

**Publication safety:** do not publish passwords, private keys, recovery material, private host identifiers, raw confidential logs, sensitive IP/MAC data or customer-specific security configuration. The public register publishes sanitized outcomes; underlying evidence remains private.

**Reference frameworks:** CIS Debian 13 Level 2 Workstation, DISA General Purpose OS SRG / relevant STIG-inspired objectives, KSPP, Debian and Kicksecure security practices. These are engineering references. **No third-party CIS, DISA or KSPP certification is claimed.**

## 10. Evidence source ledger for v5.0

- Public v4.2 README and full technical register, used as the structural baseline for this revision.
- KHAHP authoritative 924-gate ledger v3.0, 19 October 2026: Sections 01-40 / 840 gates recorded as `PROJECT_ACCEPTED`; Sections 41-44 / 84 gates remain the next reconnaissance, implementation and final-assurance phase.
- KHAHP master-control v4.0 and engineering-operations manual v2.0, 19 October 2026.
- Section 40 final evidence: USER/SYSMAINT delta reports, successful controlled production AIDE run, final root audit configuration capture, and normal-USER effective audit-rule capture.
- Section 39 remains owner-complete / no-retest unless intentionally reopened.

### Section 40 final evidence summary

- `auditd.service`: enabled, active and running in normal USER boot during final acceptance.
- Kernel audit subsystem: enabled with live auditd PID; acceptance capture showed `lost 0`.
- KHAHP audit rules: persistent rule files compiled without change and effective in normal USER boot.
- SYSMAINT `auditctl -l: No rules`: correctly classified as role-specific because auditd is inactive in SYSMAINT.
- AIDE: existing production `dailyaidecheck.service` ran successfully after the lock-helper permission repair, with `ExecMainStatus=0` and successful completion.
- `/usr/bin/dotlockfile`: persistent `755 root:mail` override retained after the successful production run.
- External mail notification and audit immutability are treated as explicit policy/operational choices, not open implementation defects in the 01-40 closeout.

**Release boundary:** v5.0 records the 01-40 project closeout. It does not claim that Sections 41-44 are complete, that every commercial-image release test has been executed, or that an external benchmark authority has certified the system.
