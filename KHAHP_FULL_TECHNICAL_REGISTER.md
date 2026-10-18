# KHAHP — Full Technical Evidence & Engineering Register

**Public Consolidated Release v4.1 · 19 October 2026 (editorial update)**  
**Elite Cybersecurity Specialist · Malaysia**  
**200+ hours of owner-reported engineering · 44 sections · 308 control families · 924 A/B/C assurance checkpoints**  
**Technical observations and outstanding decisions: through 18 October 2026**

> **Engineering mission:** Go beyond a conventional baseline-only hardening exercise. Extend Kicksecure's existing defenses by identifying security configuration weaknesses, evaluating additional protective controls, reducing unnecessary attack surface and producing repeatable evidence of enforcement, persistence and recovery — whether or not a specific weakness has been exploited.

## 1. Executive engineering position and integrity statement

KHAHP is a high-assurance defensive hardening and verification program for a Kicksecure / Debian 13 laptop. It is not a vulnerability-scanner scorecard. Its core objective is to **maximize practical defensive strength and operating-system resilience**, while respecting vendor safeguards, USER/SYSMAINT privilege separation and physical recovery.

### 1.1. What "beyond CIS Level 2" means in this project

The engineering program takes **applicable CIS Debian Linux 13 Level 2 Workstation** recommendations as a reference point and investigates further isolation, kernel and boot controls, network and DNS path validation, device/privacy boundaries, supply-chain assurance, recovery and evidence-driven negative testing. **DISA General Purpose Operating System SRG / applicable STIG-inspired objectives**, **KSPP**, and Kicksecure-native safeguards are additional design references.

The term *beyond a conventional benchmark-only baseline* describes the **breadth and intended depth of the engineering program**, not a third-party-certified ranking against every bank or operating-system deployment. A complete control-by-control comparison of applicable CIS/DISA requirements, native equivalents and project extensions is the explicit work of Section 43; this release does not invent a benchmark score or official certification.

A **security weakness does not need a working exploit** to merit correction. Overly permissive isolation, unnecessary accessible services, weak privacy defaults, missing detection capability or untested failure recovery can represent practical weaknesses, and hardening can deliberately exceed the minimum required by a checklist. Conversely, a planned check or optional feature alone is not proof that stock Kicksecure is defective.

### 1.2. Scope and significance of the 924 checkpoints

| Program measure | Number | Engineering significance |
|---|---:|---|
| Hardening sections | **44** | Defense domains, including boot, kernel, filesystem, network, devices, monitoring and recovery |
| Technical control families | **308** | Seven specific control families per section (`01.01` to `44.07`) |
| A/B/C assurance checkpoints | **924** | Per-family provenance (A), runtime enforcement (B), persistence/recovery (C) |
| Historical mixed backlog entries | **69** | Mixed review, manual, exception and implementation records, not 69 confirmed vulnerabilities |
| Historical 01–38 action records | **63** | Tracked follow-up decisions, not automatically 63 pending patches |
| Distinct supported change events | **At least 3** | Traceable corrective/hardening examples in Section 3, not a complete lifetime fix count |
| Reviewer-signed A/B/C gates | **0** in the supplied 18 Oct ledger | Historical formal signature record awaiting evidence reconciliation; not 924 failed controls |
| Planned commercial-image tests | **60** | Future clean-image, ISO, KVM/QCOW2 and OVA release tests |

The **924 entries are meaningful security assurance checkpoints**: each can reveal a configuration problem, confirm an existing safeguard, evaluate a defense-in-depth enhancement, or prove compatibility and survival through system lifecycle events. They **must not be flattened into either 924 discovered exploits or 924 meaningless paperwork entries**.

### 1.3. Demonstrated defensive engineering and improvement opportunities

| Domain | Supported engineering position | Deeper assurance / improvement being pursued |
|---|---|---|
| USER / SYSMAINT separation | Distinct roles and privileged maintenance workflow demonstrated | Complete linked role and recovery acceptance without enabling USER sudo |
| Kernel and memory | Observed restricted ptrace, kernel pointers, dmesg, BPF, ASLR and protected-file controls | Link configuration provenance to kernel build, effective coverage and update regression |
| Storage / filesystem | LUKS root observed; `/tmp` hardened with `nodev,nosuid`; boot partition mount ordering corrected and immediately validated | Recovery, boot persistence and compatibility verification |
| Software confinement | AppArmor broadly enabled and browser subprocess seccomp observed | Firefox vendor placeholder remains `unconfined`: a concrete candidate for safer restrictive confinement design/testing |
| Resolver / network | Local Unbound and DNSSEC negative/positive behavior tested; configured DoT, nftables and Tor observed | Negative proof of encrypted upstream trust, resolver bypass prevention, firewall packet verdicts and application routing |
| Peripheral / privacy | USBGuard device rules, USER camera/microphone open denial, Bluetooth block and thumbnail restrictions observed | Physical, hotplug and power/lid persistence tests under authorized owner policy |
| Audit / integrity | AIDE daily timer observed | Section 40 audit event collection, rules and AIDE alert lifecycle still require end-to-end validation |

**Provenance matters:** Existing vendor protections are credited as Kicksecure/Debian capabilities where supported; *project-specific changes* are identified separately. Configuration evidence can be technically meaningful before formal acceptance, but a proposed mitigation is not described as applied unless supported by a dated change/result.

### 1.4. Security finding categories and acceptance boundaries

| Classification | Operational meaning |
|---|---|
| **Observed protection** | Installed/configured or tested safeguard, with its actual observed scope explicitly recorded |
| **Confirmed security weakness / defect** | Demonstrated undesirable behavior or misconfiguration against an applicable approved security requirement |
| **Hardening enhancement opportunity** | An additional reduction in exposure or improvement in isolation/visibility/resilience, including when an exploit has not been reproduced |
| **Policy/compatibility decision** | Intentional choice, exception, N/A, or restriction with potential functional/recovery trade-offs |
| **Evidence pending / review** | Provenance, runtime behavior, negative test or persistence not yet sufficiently evidenced for the intended claim |
| **Formally accepted** | Approved A/B/C outcome linked to evidence, date and authorized reviewer or recorded exception |

Do not equate **not exploitable** with **not worth hardening**. Do not equate **not yet tested** with **confirmed insecure**. The same controls may have proven individual aspects and still await full A/B/C review.

### 1.5. Project status at this editorial release

- **Active engineering milestone:** Sections 01–40 are within the owner-reported implementation/investigation workstream. This does not mean all their acceptance gates are signed.
- **Section 39:** BIOS/firmware is owner-declared complete and expressly excluded from retesting; respect the decision and do not fabricate independent signatures.
- **Section 40:** Auditd/AIDE end-to-end event coverage, alert lifecycle, rule enforcement and retention are active completion tasks.
- **Sections 41–44:** Planned final assurance, recovery, standards mapping and formal acceptance phases.
- **Evidence ledger:** The supplied 18 October CSV records 0/924 formal reviewer signatures. Earlier successful observations and changes remain valid within their stated test scope; all 924 gates have not been demonstrated as security failures.
- **Revision boundary:** v4.1 updates explanatory language, organization and presentation only. It adds **no newly executed machine tests, remediations or certification results** beyond the cited October 18 records.

## 2. Evidence rules and status vocabulary

| Gate | Minimum evidence | Failure to prove does not imply |
|---|---|---|
| **A — provenance** | Package / configuration owner, original and changed value, intended policy, approved diff | No security feature exists |
| **B — effective enforcement** | Exact role, real-world allowed behavior, bounded denied behavior and observed outcomes | A test was passed merely because a unit was active |
| **C — persistence and recovery** | Relevant reboot, reconnect, update or isolated recovery plus rollback where required | A freshly observed setting will persist indefinitely |

Statuses used in this public release: `OBSERVED`, `TEST-PASS`, `OWNER-COMPLETE`, `FIXED-IMMEDIATE-VERIFIED`, `REVIEW`, `MANUAL-REQUIRED`, `EXCEPTION`, `NOT-TESTED`, and `FORMALLY-ACCEPTED`. A source finding may be sound without being formally accepted. Do not treat `REVIEW` as `CONFIRMED-VULNERABILITY`. Formal acceptance requires an authorized reviewer, date and linked A/B/C proof.

The supplied CSV contained 924 `OPEN` gates. This edition **preserves that historical signature state** rather than counterfeiting signatures from command output. The private updated master supplies newer evidence candidates for owner/reviewer reconciliation.

## 3. Configuration changes, corrective actions and durable results

| ID | Section | Change and observed result | Remaining boundary |
|---|---|---|---|
| CHG-07-01 | 07 | `/tmp`: `nodev,nosuid` applied; prior USER reboot persistence observed | `noexec` intentionally excluded for compatibility; other mounts require own decisions |
| CHG-37-01 | 37 | GNOME thumbnail generation disabled (`false` → `true`); later synthetic/reboot and PCManFM-Qt checks observed | Other applications, deletion policy and format-specific viewers require separate review |
| KHAHP-20261018-FSTAB-ORDER | 07 | `/boot` entry moved before `/boot/efi`; root `findmnt --verify --verbose`: no errors/warnings; backup retained | Validate after next operator-controlled reboot; change is not evidence of previous exploit |

### Not changed on purpose

- No blanket `/tmp` `noexec`; application and installer compatibility are explicit considerations.
- No sudden USER privilege escalation or weakening of SYSMAINT separation for testing convenience.
- No unreviewed global firewall/DNS policy cutover, Tor stop, network manager teardown or blanket USBGuard deny-all.
- No AIDE database reinitialization or invasive camera/microphone capture.
- Section 39 firmware/BIOS policy remains **owner-completed and excluded from retesting**.

## 4. High-value verification observations and limitations

| Domain | Later dated technical evidence | Interpretation |
|---|---|---|
| OS/platform | Debian 13 trixie; Linux 6.12.111+deb13-amd64; zero failed systemd units in collected runs | Observed role- and time-scoped baseline |
| Kernel | `kptr_restrict=2`, `dmesg_restrict=1`, `ptrace_scope=3`, unprivileged BPF restricted, ASLR and protected file knobs observed | Effective values for inspected controls, not all kernel options proven |
| Secure Boot / modules | Secure Boot enabled in SYSMAINT snapshot; signed Tirdad build provenance observed | Signed-module rejection and future update behavior not yet signed off |
| Network resolver | Unbound listening on loopback, active, enabled and `unbound-checkconf` clean | Local resolver availability does not rule out app-specific DNS bypass |
| DNSSEC | Positive AD response and broken-DNSSEC SERVFAIL confirmed | DNS answer authenticity in bounded test; no transport confidentiality inference |
| DNS-over-TLS | Upstream Quad9 forwarding configuration, authenticated-name and TLS port 853 observations previously recorded | Negative certificate-path validation and all egress routes require independent test |
| nftables | Active rules; input/forward default-drop; OUTPUT policy accepts with explicit external direct DNS drops | Rules present, external UDP/TCP53 packet verdicts not fully signed |
| Tor | Tor active; SOCKS loopback listener present | Which apps are Tor-scoped and fail-closed not established by service activity |
| USBGuard | Device-specific authorized mouse and approved recovery/storage; no destructive policy changes | Keyboards/mice/storage allowed by owner policy; actual input and composite behavior require physical proof |
| Camera / mic | USER open() denied for two video nodes and one microphone capture node; no recording | Current nonprivileged direct-node test only, no guarantee against all privileged/hardware paths |
| Bluetooth | rfkill soft blocks on both adapters and inactive service | Current block state observed |
| Browser | Firefox 158 active; `network.trr.mode=5`, WebRTC/prefetch restrictions and seccomp-filtered subprocesses observed | `/etc/apparmor.d/firefox` intentionally unconfined; no strict MAC claim |
| Desktop privacy | Thumbnail disabling retained; synthetic test and reboot persistence recorded; `swaylock` lock/unlock worked | Five-minute and lid/resume tests not passed by short lock test |
| Audit/AIDE | `dailyaidecheck.timer` enabled/active. SYSMAINT `auditctl -s`: audit enabled, PID 0; `auditctl -l`: no rules | Do not declare full audit-event or integrity alert lifecycle accepted |

## 5. Implementation review by all 44 sections

Each section below records the **strongest supported later observation**, an improvement or acceptance boundary, and seven control families with exact A/B/C identifiers. Together these 308 families form the **security configuration and high-assurance evidence surface** of the project. They include inherited protections, applied project hardening, candidate security improvements and outstanding tests. The listed gate IDs identify acceptance requirements; their existence does not alone indicate a flaw or a completed signature.

### 01 — Platform / OS / Hardware Baseline

**Observed implementation/evidence:** Debian 13 (trixie), kernel 6.12.111+deb13-amd64 and zero failed systemd units were observed in the October 18 USER/SYSMAINT snapshots.

**Acceptance boundary / next proof:** Reconcile full hardware inventory and post-upgrade provenance to formal A/B/C acceptance.

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

**Observed implementation/evidence:** The latest `dpkg --audit` returned no pending package-database problems. Provenance must be derived from real owning packages, not package-name guesses.

**Acceptance boundary / next proof:** Attribute outstanding permission-hardener policy and package-origin discrepancies.

**Historical action references:** `U01-003`.

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

**Observed implementation/evidence:** The intended USER/SYSMAINT privilege separation was retained during testing; privileged maintenance ran as UID 0 in a separate maintenance context.

**Acceptance boundary / next proof:** Cross-reference authoritative boot-role markers and regression checks; no USER sudo enablement.

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

**Observed implementation/evidence:** SYSMAINT evidence was collected in a privileged maintenance session; normal USER boot retained ordinary browser and network functionality.

**Acceptance boundary / next proof:** Tie protected role markers, role-specific units and provenance to current release acceptance.

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

**Observed implementation/evidence:** Restricted USER account and service-account inventory were reviewed; no arbitrary account changes were justified.

**Acceptance boundary / next proof:** Document the `sync` service-account classification and identity persistence.

**Historical action references:** `U01-004`.

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

**Observed implementation/evidence:** LUKS-encrypted root block mapping was observed; the removable installation/recovery disk was kept separate from system storage.

**Acceptance boundary / next proof:** Private key/header backup, encrypted backup and isolated restore demonstration remain separate acceptance requirements.

**Historical action references:** `U01-009`.

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

**Observed implementation/evidence:** A controlled earlier change set `/tmp` to `nodev,nosuid`. On October 18 the `/boot` entry was placed before `/boot/efi`; privileged `findmnt --verify --verbose` reported no warnings or errors, with a timestamped backup. `noexec` remains deliberately excluded.

**Acceptance boundary / next proof:** Capture next approved post-reboot mount-order persistence and application compatibility; do not apply global noexec merely to match a benchmark.

**Historical action references:** `U01-001`, `U01-002`, `U01-011`, `U01-012`, `U01-014`.

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

**Observed implementation/evidence:** GRUB protection directives were observed in the historical technical review.

**Acceptance boundary / next proof:** Physical unauthorized edit-denial and protected recovery proof have not been supplied; no secret disclosure.

**Historical action references:** `U01-008`.

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

**Observed implementation/evidence:** Spectre-class, SMT and memory-mitigation kernel options were observed; boot parameters alone are not proof of every mitigation.

**Acceptance boundary / next proof:** Correlate kernel capability, microcode and runtime vulnerabilities rather than counting cmdline tokens.

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

**Observed implementation/evidence:** The SYSMAINT evidence reported 17 IOMMU groups and enabled Secure Boot.

**Acceptance boundary / next proof:** Firmware/preboot DMA applicability remains a separate hardware/recovery question; owner BIOS work is not reopened.

**Historical action references:** `U01-010`.

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

**Observed implementation/evidence:** `kernel.kptr_restrict=2`, `dmesg_restrict=1`, `ptrace_scope=3`, unprivileged BPF restrictions and protected file operations were observed.

**Acceptance boundary / next proof:** Verify package precedence and post-upgrade persistence where material.

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

**Observed implementation/evidence:** Memory and allocator hardening boot flags were observed in the effective command line.

**Acceptance boundary / next proof:** Do not promote CFI/KCFI command-line tokens into confirmed kernel enforcement without build/runtime proof.

**Historical action references:** `U01-005`.

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

**Observed implementation/evidence:** Kernel/module policy inventories exist from earlier paired-role observations.

**Acceptance boundary / next proof:** Resolve built-in versus loadable module applicability without loading prohibited test modules.

**Historical action references:** `U01-006`.

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

**Observed implementation/evidence:** Privileged evidence identified signed Tirdad DKMS builds; Secure Boot was enabled in the October 18 SYSMAINT check.

**Acceptance boundary / next proof:** Signed-module rejection, future kernel-update regression and key-provenance acceptance require controlled proof.

**Historical action references:** `U01-007`, `U01-013`.

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

**Observed implementation/evidence:** AppArmor is enabled with many loaded profiles; Firefox 158 uses a vendor-owned `flags=(unconfined)` placeholder, and USER browser processes were observed `firefox (unconfined)`. Selected Firefox processes did have seccomp filters.

**Acceptance boundary / next proof:** Full restrictive Firefox confinement is not implemented: prepare an isolated compatible profile and test complain/enforce transitions with rollback; do not `aa-enforce` the placeholder.

**Historical action references:** `U15-001`, `U15-002`, `U15-003`.

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

**Observed implementation/evidence:** SUID/SGID and capabilities were inventoried. No evidence justifies blanket removal of package-owned helper capabilities.

**Acceptance boundary / next proof:** Resolve privileged-binary drift and capability-specific exception decisions.

**Historical action references:** `U15-004`, `U15-005`.

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

**Observed implementation/evidence:** Restrictive file- and temporary-directory controls were observed. A vendor writable-status exception is documented.

**Acceptance boundary / next proof:** Accept or reject vendor-permission exceptions on evidence; test post-update drift.

**Historical action references:** `U15-006`, `U15-007`.

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

**Observed implementation/evidence:** Yescrypt/PAM hardening was observed. The SYSMAINT review found `faillock deny=50` and `unlock_time=never`.

**Acceptance boundary / next proof:** Document safe lockout recovery and approved password/aging choices without deliberate account lockout.

**Historical action references:** `U15-008`, `U15-009`, `U15-010`.

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

**Observed implementation/evidence:** The latest USER snapshot showed the SSH server inactive and no TCP SSH listener; local client and socket uses are classified separately.

**Acceptance boundary / next proof:** Confirm listener/role persistence after update without enabling a network SSH daemon.

**Historical action references:** `U15-011`, `U15-012`.

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

**Observed implementation/evidence:** Two October 18 health checks found zero failed systemd units.

**Acceptance boundary / next proof:** Attribute expected services per USER/SYSMAINT role; monitor post-upgrade changes rather than disable vendor units indiscriminately.

**Historical action references:** `U15-013`, `U15-014`.

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

**Observed implementation/evidence:** Existing systemd sandboxing is present; exposure scores are not themselves exploitable vulnerabilities.

**Acceptance boundary / next proof:** Evaluate any optional resolver restrictions in a test build with DNS and boot-role regression.

**Historical action references:** `U15-015`, `U15-016`.

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

**Observed implementation/evidence:** Crash-dump/pstore suppression controls and associated privacy-versus-forensics tradeoffs were documented.

**Acceptance boundary / next proof:** Record exception rationale and observe package/kernel update drift; do not generate a production kernel panic.

**Historical action references:** `U15-017`, `U15-018`.

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

**Observed implementation/evidence:** Journald/secure-time baseline checks exist. Logging integrity is not equivalent to complete audit rule coverage.

**Acceptance boundary / next proof:** Approve retention and forwarding rules, ensure time coherence and protect evidence custody.

**Historical action references:** `U15-019`, `U15-020`.

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

**Observed implementation/evidence:** Emergency/recovery restrictions and shutdown service behavior were inventoried.

**Acceptance boundary / next proof:** Use disposable media/VM for fault injection; do not trigger an unexpected live-system panic.

**Historical action references:** `U15-021`, `U15-022`.

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

**Observed implementation/evidence:** Kernel memory initialization controls and encrypted storage mapping are observed.

**Acceptance boundary / next proof:** Verify wipe-hook lifecycle and swap/crypt ancestry without claiming immunity to cold-boot attacks.

**Historical action references:** `U25-003`, `U25-004`, `U25-017`.

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

**Observed implementation/evidence:** USBGuard was active and enabled; its policy authorized a recognized ZOWIE mouse and SanDisk removable medium. Approved USB mice, keyboards and recovery storage are allowed; a webcam was USB-authorized but its USER video device nodes denied direct access.

**Acceptance boundary / next proof:** Second mouse, external-keyboard functional acceptance, phone/network composite negative testing and policy precedence still need controlled proof.

**Historical action references:** `U25-001`, `U25-002`, `U25-018`.

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

**Observed implementation/evidence:** NetworkManager uses a Wi-Fi connection and randomized identity controls were historically configured.

**Acceptance boundary / next proof:** Over-the-air MAC and DHCP identity comparison on an owned router remains a dedicated test.

**Historical action references:** `U25-005`, `U25-006`.

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

**Observed implementation/evidence:** The inspected kernel boot used `ipv6.disable=1`, and the USER network snapshot showed no IPv6 route.

**Acceptance boundary / next proof:** Explicitly decide whether to retain disabled IPv6 or move to a separately reviewed dual-stack privacy architecture.

**Historical action references:** `U25-007`, `U25-019`.

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

**Observed implementation/evidence:** Unbound is active and configured, and the USER snapshot showed a `127.0.0.1:53` listener; local DNS resolution was functional.

**Acceptance boundary / next proof:** Distinguish effective system resolver wiring from application bypass during network transitions.

**Historical action references:** `U25-008`, `U25-020`.

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

**Observed implementation/evidence:** A DNSSEC-valid response set the AD flag; a deliberately invalid DNSSEC domain returned SERVFAIL. Unbound DoT forwarding and a port-853 process observation were previously reported.

**Acceptance boundary / next proof:** Certificate-negative transport validation and bounded external UDP/TCP 53 bypass verdicts are not yet signed off.

**Historical action references:** `U25-009`, `U25-010`, `U25-011`, `U25-021`.

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

**Observed implementation/evidence:** nftables is active; privileged rules show input and forward default-drop policies, but the OUTPUT base policy permits traffic with explicit direct-DNS restrictions.

**Acceptance boundary / next proof:** Correlate final effective OUTPUT rule order and UDP/TCP DNS verdicts at an authorized endpoint; verify normalized reboot persistence.

**Historical action references:** `U25-012`, `U25-013`.

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

**Observed implementation/evidence:** LAN discovery service and listener inventory was collected.

**Acceptance boundary / next proof:** Peer-origin mDNS, LLMNR and SSDP reply-negative tests remain inconclusive without an owned LAN peer.

**Historical action references:** `U25-014`, `U25-022`.

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

**Observed implementation/evidence:** Tor was active, with a loopback SOCKS listener observed on port 9050.

**Acceptance boundary / next proof:** Prove routing and fail-closed behavior for only the applications intended to use Tor; do not stop system-wide services casually.

**Historical action references:** `U25-015`.

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

**Observed implementation/evidence:** sdwdate, boot-time and secure-time components were observed in the historical baseline.

**Acceptance boundary / next proof:** Use time/log chronology and disposable-VM rollback tests rather than altering the live system clock.

**Historical action references:** `U25-016`, `U25-023`.

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

**Observed implementation/evidence:** The later USER evidence showed entropy availability and strong kernel randomization settings; RNG services were enabled in the system baseline.

**Acceptance boundary / next proof:** Cloned-image seed uniqueness is a future release test and not a claim about a released product.

**Historical action references:** `U35-001`.

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

**Observed implementation/evidence:** The active Firefox `default-release` configuration was observed with DoH/TRR mode 5, WebRTC disabled and relevant prefetch settings disabled. Enabled extension inventory was empty.

**Acceptance boundary / next proof:** An effective browser-to-network DNS/DoH bypass test using an authorized endpoint remains distinct from preference-file inspection.

**Historical action references:** `U35-002`.

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

**Observed implementation/evidence:** `org.gnome.desktop.thumbnailers disable-all` changed from false to true, and later USER evidence still read true. PCManFM-Qt thumbnail disabling, a synthetic image test and reboot persistence were observed.

**Acceptance boundary / next proof:** Third-party application history/thumbnail backends and privacy tradeoffs require explicit acceptance. The earlier apply/verify archive self-hash defect is packaging-only.

**Historical action references:** `U35-003`.

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

**Observed implementation/evidence:** Normal USER opening `/dev/video0`, `/dev/video1` and `/dev/snd/pcmC0D0c` was denied without capture. Bluetooth was rfkill-soft-blocked with inactive service. `swaylock` successfully locked the desktop in a shorter manual test.

**Acceptance boundary / next proof:** Five-minute unattended lock persistence, lid/resume authentication (if policy requires it), keyboard/mouse hotplug and hibernation decision remain distinct tests.

**Historical action references:** `U35-004`.

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

**Observed implementation/evidence:** **OWNER COMPLETED / EXCLUDED FROM RETEST.** BIOS/UEFI checks have already been passed according to the owner. Other evidence also reported Secure Boot enabled; no further BIOS testing is requested.

**Acceptance boundary / next proof:** Preserve the owner completion declaration and dated record. It is not an independent auditor certification or 21 signed A/B/C gates.

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

**Observed implementation/evidence:** The `dailyaidecheck.timer` was enabled and active. In a SYSMAINT snapshot, audit was enabled but `auditctl -s` showed `pid 0` and `auditctl -l` reported no active rules.

**Acceptance boundary / next proof:** The owner targets 01–40 completion, but a benign audit event and existing AIDE baseline alert lifecycle were not supplied. Do not claim final Section 40 enforcement acceptance yet.

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

**Observed implementation/evidence:** Scheduled jobs, startup entries and software supply-chain attribution are in the planned final assurance phase.

**Acceptance boundary / next proof:** Map provenance, signatures and cross-reboot persistence; future work.

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

**Observed implementation/evidence:** Credentials and backup planning are documented; a private production-grade isolated restore has not been shown.

**Acceptance boundary / next proof:** Approve encrypted backups, retention, custody and isolated restoration.

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

**Observed implementation/evidence:** CIS Debian 13 Level 2, DISA GPOS/SRG and KSPP have been identified as comparison frameworks. The project also identifies native Kicksecure protections and extra engineering requirements that may extend conventional baseline scope.

**Acceptance boundary / next proof:** Build a control-by-control mapping of each applicable benchmark requirement, observed inherited safeguard, project extension and justified exception. The comparison must be evidence-backed before claiming measured superiority over a specific bank baseline, CIS score or official certification.

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

**Observed implementation/evidence:** A/B/C acceptance methodology is defined for 308 families and 924 gates.

**Acceptance boundary / next proof:** Final owner/reviewer signoff, negative testing, recoverability and evidence completeness.

| Family | Exact technical scope | A/B/C evidence IDs |
|---|---|---|
| `44.01` | Full reboot persistence acceptance | `KHAHP-44.01A` · `KHAHP-44.01B` · `KHAHP-44.01C` |
| `44.02` | USER-mode regression acceptance | `KHAHP-44.02A` · `KHAHP-44.02B` · `KHAHP-44.02C` |
| `44.03` | SYSMAINT-mode regression acceptance | `KHAHP-44.03A` · `KHAHP-44.03B` · `KHAHP-44.03C` |
| `44.04` | Network/DNS/firewall/Tor/USB negative-test acceptance | `KHAHP-44.04A` · `KHAHP-44.04B` · `KHAHP-44.04C` |
| `44.05` | Recovery/rollback/backup acceptance | `KHAHP-44.05A` · `KHAHP-44.05B` · `KHAHP-44.05C` |
| `44.06` | Evidence completeness, hashes and chain-of-custody bundle | `KHAHP-44.06A` · `KHAHP-44.06B` · `KHAHP-44.06C` |
| `44.07` | Final scorecard, residual risk and operator sign-off | `KHAHP-44.07A` · `KHAHP-44.07B` · `KHAHP-44.07C` |

## 6. Historical 01–38 action reconciliation — all 63 IDs

These 63 inherited action records are carried forward to preserve **hardening opportunities, configuration concerns, owner decisions and evidence gaps** that can materially improve security. They are part of the 69-item mixed historical backlog, not a claim of 63 independently proven exploits. Later successful demonstrations are retained as engineering results; remaining requirements are explicitly shown and **do not become signed acceptance without review**. Section 39 BIOS is not retested.

| ID | Sec. | Engineering issue | Evidence disposition as of 18 Oct 2026 |
|---|---:|---|---|
| `U01-001` | 7 | /tmp and /dev/shm noexec compatibility decision | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U01-002` | 7 | /boot/efi-before-/boot fstab ordering review | CONFIGURATION FIX VERIFIED (18 OCT); NEXT-BOOT PERSISTENCE NOT YET ATTESTED |
| `U01-003` | 2 | permission-hardener package/provenance classifier | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U01-004` | 5 | sync account shell classification | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U01-005` | 12 | Unverified kernel tokens / CFI-KCFI claims | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U01-006` | 13 | vesafb module applicability / dry-run review | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U01-007` | 14 | USER versus SYSMAINT DKMS evidence reconciliation | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U01-008` | 8 | Physical GRUB edit-denial test | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U01-009` | 6 | LUKS key recovery and backup restore | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U01-010` | 10 | Firmware/preboot DMA protection acceptance | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U01-011` | 7 | Post-reboot SYSMAINT persistence evidence | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U01-012` | 7 | /home, /var/tmp and noexec compatibility review | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U01-013` | 14 | Signed-module negative test and update regression | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U01-014` | 7 | /tmp nodev,nosuid hardening — implemented baseline | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U15-001` | 15 | Strict Firefox AppArmor confinement is not established | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U15-002` | 15 | AppArmor service policy and denial regression | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U15-003` | 15 | USER versus SYSMAINT browser-label persistence | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U15-004` | 16 | Privileged binary provenance/drift review | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U15-005` | 16 | gst-ptp-helper capability policy/compatibility | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U15-006` | 17 | setup-dist status-files 0777 exception monitoring | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U15-007` | 17 | Sensitive directory/ACL/umask and tmpfs drift | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U15-008` | 18 | faillock recovery and self-lockout policy | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U15-009` | 18 | Passphrase/aging policy ownership | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U15-010` | 18 | PAM USER/SYSMAINT interaction regression | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U15-011` | 19 | Network SSH masking and listener persistence | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U15-012` | 19 | Local SSH AF_UNIX socket and client key policy | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U15-013` | 20 | Role-specific systemd service drift and listening sockets | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U15-014` | 20 | Classify unexpected/unused services safely | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U15-015` | 21 | Unbound systemd exposure score needs design decision | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U15-016` | 21 | Service sandbox capability regression | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U15-017` | 22 | Core dump/pstore suppression drift | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U15-018` | 22 | Crash-forensics versus privacy trade-off | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U15-019` | 23 | Journal retention, permissions and rotation policy | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U15-020` | 23 | sdwdate time and journal chronology after reboot | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U15-021` | 24 | Owner-approved panic/recovery policy and escape paths | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U15-022` | 24 | Emergency shutdown and controlled recovery evidence | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U25-001` | 26 | External USB keyboard possibly allowed | POLICY CORRECTED: EXTERNAL KEYBOARDS ALLOWED; FUNCTIONAL TEST TO RECONCILE |
| `U25-002` | 26 | Composite/USB network rejection and persistence | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U25-003` | 25 | Swap crypt mapping and shutdown key lifecycle | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U25-004` | 25 | RAM wipe shutdown execution and hardware limits | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U25-005` | 27 | Actual Wi-Fi MAC identity | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U25-006` | 27 | DHCP identity rotation | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U25-007` | 28 | Alternate IPv6 network profiles | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U25-008` | 29 | Unbound response to DHCP renew/network loss | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U25-009` | 30 | Unbound-owned authenticated DoT | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U25-010` | 30 | Direct UDP/TCP 53 egress | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U25-011` | 30 | Active browser DNS/DoH preferences | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U25-012` | 31 | Effective firewall output chain | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U25-013` | 31 | Exact loaded-ruleset persistence | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U25-014` | 32 | Peer-side discovery proof | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U25-015` | 33 | Tor Browser routing/DNS/fail-close | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U25-016` | 34 | Secure-time unit chronology | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U25-017` | 25 | Original implementation provenance | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U25-018` | 26 | USB boot media usability versus detection | RECOVERY MEDIA USB AUTHORIZED/DETECTED; ACCESSIBILITY/INSTALL MODE SEPARATE |
| `U25-019` | 28 | IPv6 goal mismatch / explicit policy | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U25-020` | 29 | USER/SYSMAINT service role semantics | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U25-021` | 30 | DNSSEC positive/negative evidence signoff | DNSSEC POSITIVE/NEGATIVE OBSERVED; FORMAL CLAIM REVIEW OPEN |
| `U25-022` | 32 | Actual scope of local discovery services | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U25-023` | 34 | Production clock rollback exception | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U35-001` | 35 | Early-boot entropy and random-seed lifecycle | REVIEW / PROOF OR OWNER DECISION NOT YET SIGNED |
| `U35-002` | 36 | Firefox effective DoH, WebRTC and telemetry behavior | FIREFOX SETTINGS VERIFIED; EXTERNAL BROWSER PATH NEGATIVE STILL OPEN |
| `U35-003` | 37 | Application history, thumbnails, metadata and confinement regression | THUMBNAILS AND REBOOT TEST VERIFIED; OTHER APP BEHAVIOR NOT FULLY SIGNED |
| `U35-004` | 38 | Camera/microphone hotplug and real lock/lid-resume enforcement | CAMERA/MIC USER DENIAL + BT BLOCK + SHORT LOCK PASS; 5-MIN/LID OPEN |

### Essential reconciliation decisions

1. **Owner device policy prevails:** external keyboards, two approved mice and USB removable/recovery storage are allowed. Older testing notes requesting keyboard rejection are superseded.
2. **Confirmed changes are not identical to confirmed exploit findings.** Track pre-state, root cause, authorization, exact delta, positive and negative post-state before classifying a true fixed weakness.
3. **Section 07 boot ordering:** immediate root verification passed after correction; avoid reapplying the edit. Preserve backup and collect persistence only when a normal owner reboot occurs.
4. **Section 15 Firefox:** the vendor unconfined placeholder remains an explicitly open MAC enhancement, even though Firefox subprocess seccomp filters exist.
5. **Section 40 audit events:** a working AIDE timer does not prove event coverage. The latest SYSMAINT run observed no active audit rules and PID 0; troubleshoot before a full assurance claim.
6. **Section 39 BIOS:** prior owner completion is accepted as the project process decision and excluded from future retesting; it does not forge formal independent sign-off.

## 7. Commercial image engineering and supply-chain acceptance

Proposed KHAHP Premium Hardened OS target price: **USD $1,250**; intended distributions are physical ISO/USB, KVM/QCOW2, and VirtualBox/OVA. No public downloadable commercial image or certification is asserted. A clean build must never clone the personal development machine, SSH secrets, random seeds or machine identity.

### Clean-image common requirements

| Planned release ID | Required demonstration | Current program state |
|---|---|---|
| `KHAHP-REL-COM-01` | Reproducible upstream source | PROPOSED · NOT TESTED |
| `KHAHP-REL-COM-02` | Package provenance | PROPOSED · NOT TESTED |
| `KHAHP-REL-COM-03` | Build isolation | PROPOSED · NOT TESTED |
| `KHAHP-REL-COM-04` | Credential exclusion | PROPOSED · NOT TESTED |
| `KHAHP-REL-COM-05` | Unique machine identity | PROPOSED · NOT TESTED |
| `KHAHP-REL-COM-06` | Unique SSH host keys | PROPOSED · NOT TESTED |
| `KHAHP-REL-COM-07` | SSH access policy | PROPOSED · NOT TESTED |
| `KHAHP-REL-COM-08` | Privileges and boot-role separation | PROPOSED · NOT TESTED |
| `KHAHP-REL-COM-09` | Default firewall | PROPOSED · NOT TESTED |
| `KHAHP-REL-COM-10` | DNS resolver protection | PROPOSED · NOT TESTED |
| `KHAHP-REL-COM-11` | Network privacy behavior | PROPOSED · NOT TESTED |
| `KHAHP-REL-COM-12` | MAC and device privacy | PROPOSED · NOT TESTED |
| `KHAHP-REL-COM-13` | Mandatory access controls | PROPOSED · NOT TESTED |
| `KHAHP-REL-COM-14` | Kernel hardening | PROPOSED · NOT TESTED |
| `KHAHP-REL-COM-15` | Audit visibility | PROPOSED · NOT TESTED |
| `KHAHP-REL-COM-16` | File integrity monitoring | PROPOSED · NOT TESTED |
| `KHAHP-REL-COM-17` | Upgrade safety | PROPOSED · NOT TESTED |
| `KHAHP-REL-COM-18` | Backup and restoration | PROPOSED · NOT TESTED |
| `KHAHP-REL-COM-19` | Release signing | PROPOSED · NOT TESTED |
| `KHAHP-REL-COM-20` | Customer documentation and licensing | PROPOSED · NOT TESTED |

### Physical ISO / USB requirements

| Planned release ID | Required demonstration | Current program state |
|---|---|---|
| `KHAHP-REL-ISO-01` | UEFI USB boot | PROPOSED · NOT TESTED |
| `KHAHP-REL-ISO-02` | Installer storage detection | PROPOSED · NOT TESTED |
| `KHAHP-REL-ISO-03` | Fresh encrypted installation | PROPOSED · NOT TESTED |
| `KHAHP-REL-ISO-04` | Encryption recovery | PROPOSED · NOT TESTED |
| `KHAHP-REL-ISO-05` | Secure Boot enrollment | PROPOSED · NOT TESTED |
| `KHAHP-REL-ISO-06` | Firmware Setup Mode | PROPOSED · NOT TESTED |
| `KHAHP-REL-ISO-07` | TPM optional path | PROPOSED · NOT TESTED |
| `KHAHP-REL-ISO-08` | Intel and AMD support | PROPOSED · NOT TESTED |
| `KHAHP-REL-ISO-09` | Graphics and desktop | PROPOSED · NOT TESTED |
| `KHAHP-REL-ISO-10` | Wireless networking | PROPOSED · NOT TESTED |
| `KHAHP-REL-ISO-11` | Ethernet and hotplug | PROPOSED · NOT TESTED |
| `KHAHP-REL-ISO-12` | USBGuard defaults | PROPOSED · NOT TESTED |
| `KHAHP-REL-ISO-13` | Installer device safety | PROPOSED · NOT TESTED |
| `KHAHP-REL-ISO-14` | DMA/IOMMU capabilities | PROPOSED · NOT TESTED |
| `KHAHP-REL-ISO-15` | Signed module lifecycle | PROPOSED · NOT TESTED |
| `KHAHP-REL-ISO-16` | Physical webcam/microphone | PROPOSED · NOT TESTED |
| `KHAHP-REL-ISO-17` | Power and RAM-wipe process | PROPOSED · NOT TESTED |
| `KHAHP-REL-ISO-18` | BIOS recovery restrictions | PROPOSED · NOT TESTED |
| `KHAHP-REL-ISO-19` | Multi-boot/firmware resilience | PROPOSED · NOT TESTED |
| `KHAHP-REL-ISO-20` | Fresh-install two-device comparison | PROPOSED · NOT TESTED |

### KVM / QCOW2 requirements

| Planned release ID | Required demonstration | Current program state |
|---|---|---|
| `KHAHP-REL-KVM-01` | QCOW2 import and boot | PROPOSED · NOT TESTED |
| `KHAHP-REL-KVM-02` | Fresh clone identity | PROPOSED · NOT TESTED |
| `KHAHP-REL-KVM-03` | Virtual firmware choice | PROPOSED · NOT TESTED |
| `KHAHP-REL-KVM-04` | Virtual TPM support | PROPOSED · NOT TESTED |
| `KHAHP-REL-KVM-05` | Host-guest firewall isolation | PROPOSED · NOT TESTED |
| `KHAHP-REL-KVM-06` | Guest disk encryption | PROPOSED · NOT TESTED |
| `KHAHP-REL-KVM-07` | Virtio device support | PROPOSED · NOT TESTED |
| `KHAHP-REL-KVM-08` | KVM snapshot and restore | PROPOSED · NOT TESTED |
| `KHAHP-REL-KVM-09` | KVM version regression | PROPOSED · NOT TESTED |
| `KHAHP-REL-KVM-10` | QCOW2 sanitized release | PROPOSED · NOT TESTED |

### VirtualBox / OVA requirements

| Planned release ID | Required demonstration | Current program state |
|---|---|---|
| `KHAHP-REL-OVA-01` | OVA packaging and import | PROPOSED · NOT TESTED |
| `KHAHP-REL-OVA-02` | Unique identity on import | PROPOSED · NOT TESTED |
| `KHAHP-REL-OVA-03` | Clipboard and drag-drop | PROPOSED · NOT TESTED |
| `KHAHP-REL-OVA-04` | Shared-folder isolation | PROPOSED · NOT TESTED |
| `KHAHP-REL-OVA-05` | USB passthrough restriction | PROPOSED · NOT TESTED |
| `KHAHP-REL-OVA-06` | VirtualBox networking | PROPOSED · NOT TESTED |
| `KHAHP-REL-OVA-07` | Guest addition safety | PROPOSED · NOT TESTED |
| `KHAHP-REL-OVA-08` | Virtual disk recovery | PROPOSED · NOT TESTED |
| `KHAHP-REL-OVA-09` | Supported host matrix | PROPOSED · NOT TESTED |
| `KHAHP-REL-OVA-10` | OVA clean release gate | PROPOSED · NOT TESTED |

## 8. Planned completion of Sections 41–44

| Section | Required work | Release proof |
|---|---|---|
| 41 — Persistence / supply chain | Cron/timer/autostart classification, signing and package origin, two-boot drift | Attributed, bounded and stable scheduled activity |
| 42 — Credentials / backup / recovery | Secret inventory without disclosure; owner-approved encrypted backups; isolated restore | Successful recovery and sample hash comparison; custody controls |
| 43 — CIS/DISA/KSPP applicability | Map every relevant requirement, native equivalent and justified N/A | Evidence-linked applicability map; no official certification claim |
| 44 — Final A/B/C sign-off | Independent review, complete negative/regression and rollback proof, dated acceptance | 308 families × A/B/C accepted with documented risk exceptions |

## 9. Compliance, controlled change and public disclosure

**Execution roles:** USER runs normal browser and read-only checks without sudo. SYSMAINT is a separate privileged boot, with independently verified source digests and a root-owned copy for execution. Privileged scripts are never executed in place from a USER-writable transport path.

**Change gate:** evidence → verified root cause → minimal diff → backup/recovery → owner approval → apply → immediate postflight → bounded negative test → relevant reboot/update persistence → dated A/B/C acceptance.

**Publication safety:** No hostnames, private identifiers, IP/MAC addresses, raw firewall and browser history, SSH material, real encryption IDs/keys, authentication secrets or raw confidential reports. This register publishes redacted outcomes; underlying logs remain in private custody. Historical Section 37 self-hashing manifest errors must be identified rather than presenting those archives as fully hash-valid.

**Reference frameworks:** CIS Debian 13 Level 2 Workstation, DISA General Purpose OS SRG and relevant STIG-inspired objectives, KSPP, Debian and Kicksecure security practices. They guide an intentionally deeper hardening and assurance program; Section 43 will document applicable controls, project extensions and measured gaps. They are not third-party compliance certifications.

**Public challenge submissions:** provide machine-independent provenance, threat model, safely reproducible tests, intended/observed outcomes, minimized changes, rollback proof, and limitations. Do not perform unauthorized external testing or disclose user-specific security details.

## 10. Evidence source ledger for this revision

**v4.1 editorial lineage:** Built directly from the owner-uploaded public v4.0 technical register and October 18 evidence ledger. All 44 named sections, 308 numbered families, 924 gate IDs, 63 historical action records and 60 proposed release tests are retained. No device scan or post-October-18 control implementation is implied.


- Pre-existing public register v3.0 (17 October 2026), 308 technical family labels and 60 planned release tests.
- Private KHAHP master v2.0 and 924-gate proof-claims CSV dated 18 October 2026 (all historical signatures OPEN).
- KHAHP compliance standard v3.0, field manual v2.0 and 63-item historical 01–38 closeout list.
- USER 01–38 read-only observations of 18 October 2026; SYSMAINT 65-check archive with validated hashes and zero changes.
- Later USER direct camera/mic open-denial, USBGuard inventory, Firefox process-label/prefs, DNSSEC, AIDE timer and manual short-lock observations.
- Operator-shared SYSMAINT terminal evidence of `/etc/fstab` boot-order correction and clean `findmnt --verify --verbose` validation.
- Section 39 BIOS status: owner declaration, no new test requested.

**Evidence limitation:** No complete Section 40 audit-event/AIDE alert lifecycle report or formally signed 924-gate acceptance register was supplied in the cited October 18 evidence. This editorial update emphasizes security engineering depth and hardening opportunities without inventing test passes, certification, or more recent machine evidence.
