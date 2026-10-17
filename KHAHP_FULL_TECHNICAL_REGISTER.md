# KHAHP — Open Cybersecurity Hardening Challenge
## Public Technical Evidence, Remediation & Product Roadmap

**ELITE CYBERSECURITY SPECIALIST · Malaysia**
**Kicksecure High-Assurance Hardening Project (KHAHP)**
**Public Consolidated Release v3.0 · 17 October 2026 · Work in progress**

> **Open challenge:** Can another cybersecurity specialist demonstrate a stronger defensive operating-system hardening result using traceable evidence, controlled negative tests, compatibility analysis, reproducible builds and independently reviewable acceptance criteria?

> **PUBLICATION STATUS — PROVISIONAL:** Sections **01–34** have completed documentation baselines and historical security observations, **not 714 accepted security checks**. Sections **35–44 are being completed**. This document records what is supported, what remains to be demonstrated, and where a genuine fix *might* be needed. It does not certify the OS, expose private laptop evidence, or represent a shipping commercial image.

**Public repository:** https://github.com/elite-cybersecurity-specialist/hardening-challenge

---

## Contents

1. Executive scope and public challenge
2. Commercial roadmap — KHAHP Premium Hardened OS (USD $1,250)
3. Evidence standard, vocabulary, and publication safety
4. Documentation release reconciliation — Sections 01–44
5. Proven implementation and historical observations — Sections 01–34
6. Public evidence-to-action register — outstanding fixes and proof
7. Complete 44-section evidence orientation
8. Master technical control register — all 308 families and 924 gates
9. Future implementation and evidence publication process
10. Proposed commercial-image release test suite — all 60 tests
11. Open challenge: independent review criteria
12. Source bibliography, limits and revision policy

---

## 1. Executive scope and public challenge

KHAHP is an evidence-driven, high-assurance defensive-security engineering project built on Kicksecure, a Debian-derived operating system. It uses a separated **USER** daily-operation context and **SYSMAINT** administrative context and evaluates privileges, encryption, kernel hardening, networking, service isolation, auditing, privacy and disaster recovery in the correct role.

The challenge is not to claim perfect security. It is to demonstrate **which controls exist, what they actually do, whether they survive reboots or updates, and what defects or exceptions remain**. Appropriate participants include defensive-security engineers, operating-system specialists, red/blue teams, academic researchers, and authorized security reviewers. Potential uses include government/law-enforcement work, investigative journalism and source protection, finance, critical infrastructure, executive security and other sensitive deployments, subject to each organization’s own rules and assessments.

| Defined scope | Quantity | Meaning |
|---|---:|---|
| Security sections | **44** | Seven families per section |
| Control families | **308** | Stable identifiers 01.01 through 44.07 |
| A/B/C acceptance gates | **924** | Source/provenance, runtime enforcement, persistence/negative/recovery |
| Proposed product release tests | **60** | Clean build, physical media, KVM and VirtualBox |
| Combined planned verification scope | **984** | **Not** 984 exploited vulnerabilities or 984 completed patches |

The original challenge recorded **over 120 engineering hours** in its October 2026 publication; this was a dated historical statement, not a current live hour counter. New evidence has been added since that initial publication.

## 2. Commercial roadmap — KHAHP Premium Hardened OS

### Proposed price: **USD $1,250**

**The proposed KHAHP Premium Hardened OS price remains USD $1,250.** This is a development-stage commercial proposition—not an available, fully certified product or a guarantee of security, anonymity, hardware compatibility or availability. The planned product must pass the release gates and documented owner acceptance before shipping.

| Planned edition | Target format | Primary acceptance concerns |
|---|---|---|
| **Physical** | Bootable ISO / USB pendrive | Fresh encrypted installation, Secure Boot, firmware limits, peripheral safety, recovery |
| **KVM** | QCOW2 / QEMU-KVM | Host/guest isolation, fresh cloned identities, virtual TPM, snapshots, network policy |
| **VirtualBox** | OVA virtual appliance | Unique identity on import, disabled risky integrations, virtual network/USB handling, restore |

Commercial release must use a **clean reproducible image build**, never a direct clone of the development laptop. Every customer instance needs unique credentials/host keys and independently demonstrated recovery behavior. The 60 proposed tests are preserved in Section 10.

## 3. Evidence standard, vocabulary, and publication safety

| Gate | Acceptance meaning | Evidence required |
|---|---|---|
| **A — Source** | Package ownership, configuration provenance, intended security policy | Approved source/config delta and supporting references |
| **B — Runtime** | Live implementation works as intended | Correct-role observations plus appropriate authorized negative tests |
| **C — Persistence** | Protection survives expected lifecycle and safe recovery | Controlled reboot, service restart, network change, patch update, or approved exception |

**Status vocabulary**: `DOCUMENTED` means an independently authored dossier exists; `OBSERVED` means a narrowly defined test recorded a fact; `REVIEW` means insufficient interpretation or an unexpected observation; `NOT_TESTED` means no appropriate test was performed; `EXC` means an exception requiring rationale; `CHG` means a documented actual change. None means a complete A/B/C family pass. All **924** formal gate approvals remain **OPEN / NOT SIGNED OFF** in this public baseline; evidence for individual gates can nevertheless be useful.

**Public/private division:** This release deliberately excludes raw log lines, hostnames, usernames, private/local IP addresses, MAC addresses, device serials, machine UUIDs, real recovery identifiers, secrets, SSH keys, full firewall rules, browser history, uploaded private reports and sensitive system-specific configuration paths. Sanitized summaries describe test outcomes and required next evidence. Private, timestamped, checksummed reports remain in restricted project custody.

**Risk handling:** A missing demonstration is not a vulnerability. A package-owned exception is not automatically a defect. A negative finding is escalated to a patch only after authorized reproduction, source ownership, impact analysis, tested rollback and explicit owner approval. Unsupported absolute claims such as "unhackable," "fully anonymous," or "DISA-certified" are not used.

**Reference frameworks:** CIS Debian Linux 13 Level 2 Workstation, applicable DISA GPOS SRG objectives, historical STIG-oriented guidance and KSPP self-protection principles are mapping aids, not certification or proof of full compliance.

## 4. Documentation release reconciliation — Sections 01–44

| Tranche | Sections | Families | Gates | What is actually complete | What remains |
|---|---:|---:|---:|---|---|
| A | 01–14 | 98 | 294 | Technical dossier v1.0; source reviews; one targeted /tmp improvement with USER reboot evidence | Remaining controlled negative/recovery tests and final A/B/C approvals |
| B | 15–24 | 70 | 210 | Technical dossier v1.0; source reconciliation; 22 categorized follow-up records | Formal gate review, manual/policy exceptions and authorized post-change regressions |
| C | 25–34 | 70 | 210 | Technical documentation v1.0; 520 indexed historical observations and newer v6.1 target runs | 23 outstanding issues including effective USB/DNS/Tor/LAN enforcement and provenance |
| D | 35–44 | 70 | 210 | Historical evidence review; read-only verifier source passed offline QA | Actual target-run verification, evidence reconciliation, real backup/restore and Section 44 sign-off |
| **Total** | **01–44** | **308** | **924** | **34 sections documented; final assurance ongoing** | **All formal gates remain open until review** |

**Critical source limitation:** The Sections 15–24 documentation archive indexes original evidence filenames/hashes but does not contain every underlying report body. The Sections 35–44 review documents historical findings but its latest grand verifier has not been shown running on the production laptop; no executed Section 44 report is present. These source limitations must not be filled with assumptions.

## 5. Proven implementation and historical observations — Sections 01–34

The following high-level observations are supported by the privately held engineering dossiers. Their publication does **not** reveal exact per-host rules or identifiers and does **not** close any unreviewed acceptance gates.

| Scope | Observed/documented implementation evidence | Boundary of proof |
|---|---|---|
| 01–05 | Kicksecure/OS inventory, USER/SYSMAINT privilege restrictions, account and package-provenance reviews | Device-specific and post-upgrade properties require dated verification |
| 06–08 | Encrypted root and swap ancestry, bootloader policy; temporary-filesystem hardening applied and observed after ordinary USER reboot | Recovery, physical boot bypass and SYSMAINT post-reboot evidence pending |
| 09–14 | CPU mitigations, IOMMU, sysctl and module policy; later Secure Boot and signed DKMS observations | Kernel build truth, firmware protection and lifecycle regressions still open |
| 15–19 | AppArmor active for selected services, privilege executable inventory, PAM hardening, restricted network SSH | Firefox confinement, vendor permission exception, policy and negative tests remain |
| 20–24 | Role-aware services, existing sandboxing, core-dump suppression, journal integrity and guarded recovery state | Service drift, retention design and safe recovery tests remain |
| 25–29 | Memory-initialization flags, USBGuard policy inventory, randomized Wi-Fi setting, IPv6-disable observation, local Unbound | Physical enforcement, over-air identity and DNS transition behavior require proof |
| 30–34 | DNSSEC positive/negative results, configured DoT forwarding, firewall base-chain policy, active Tor and secure-time services | Authenticated DoT, DNS egress verdicts, LAN peer tests, selective Tor and time chronology remain unproven |

### Historical correction examples

- **CHG-07-01:** A real targeted /tmp mount hardening change was documented, with a backup, immediate runtime result and subsequent ordinary USER reboot evidence. This is not a blanket acceptance of every filesystem policy.
- **Secure Boot / DKMS:** An older disabled Secure Boot snapshot was superseded by later enabled-state and signed-module evidence. Old and new observations have different dates and are not mutually contradictory.
- **Vendor AppArmor and permissions:** Firefox confinement and a package-maintained writable status cache are known design/compatibility reviews, not instructions to overwrite vendor-owned files blindly.
- **USB recovery medium:** An owned removable Kicksecure installation medium was authorized and detected as a block device. Its installer-format filesystem not being auto-mounted is not proof USBGuard malfunctioned.

## 6. Public evidence-to-action register — what still needs fixing or proving

**Reading rule:** Each line is an engineering evidence gap or a documented exception. Words such as **needs work** mean remediation *or further evidence*, not necessarily an exploitable defect. Every record is unapproved for automatic patching.

### 6A. Sections 01–14: source-derived change and review ledger

| ID | Area | Type | Public evidence | What is needed before acceptance or patch |
|---|---|---|---|---|
| CHG-07-01 | 07 | Verified improvement | The temporary filesystem gained restrictive mount flags and the change was observed after an ordinary USER reboot. | Preserve the approved backup and confirm SYSMAINT reboot and application compatibility; no automatic reapply. |
| EXC-07-01 | 07 | Compatibility exception | Executing files from shared temporary filesystems remains a documented compatibility trade-off. | Review applications before considering a noexec change; do not force a global restriction. |
| EXC-07-02 | 07 | Unresolved review | A broader fstab check reported an ordering concern unrelated to the verified temporary-filesystem change. | Review boot ordering separately and test only with a recovery procedure. |
| REV-02-01 | 02 | Provenance discrepancy | The presence of a package-managed hardening policy differed from a simplistic package-name probe. | Attribute the actual files to installed packages before labeling a missing tool or recommending installation. |
| REV-05-01 | 05 | Classification review | A low-privilege system account and its locked authentication state needed context-sensitive interpretation. | Verify account purpose and acceptable shell behavior without changing accounts blindly. |
| REV-09-12 | 09 | Unverified mitigation claim | Some historical kernel command-line tokens were not enough to prove the intended hardening mechanisms activated. | Confirm kernel build support and effective runtime behavior before claiming CFI/KCFI or equivalent. |
| REV-13-01 | 13 | Applicability review | Module inspection had ambiguity between built-in and dynamically loadable components. | Resolve module applicability without actually loading a disallowed module. |
| REV-14-01 | 14 | Role-specific reconciliation | An earlier restricted-user DKMS warning conflicted with more authoritative privileged evidence of signed installed builds. | Retain both timestamps; verify signing and kernel-update regression without re-enrolling keys for an old warning. |
| MAN-08 | 08 | Manual test pending | Bootloader protection was observed by source inspection, not by a supervised physical edit-denial test. | Require an approved supervised recovery-capable physical test. |
| MAN-06 | 06 | Manual test pending | Encrypted root and on-disk swap ancestry have evidence, but secret recovery and restore were not demonstrated. | Perform isolated authorized recovery exercises; never publish recovery material. |
| MAN-10 | 10 | Manual test pending | DMA mitigation observations do not establish all preboot hardware behavior. | Evaluate firmware/IOMMU applicability in an owned safe test environment. |
| MAN-01-14 | 01–14 | Acceptance gap | A USER reboot verified a narrow change; the complete two-role multi-control signoff remains unfinished. | Complete per-family A/B/C evidence review, compatibility tests, and role-matched persistence verification. |

### 6B. Sections 15–24: all 22 tracked evidence, exception and policy items

| Tracking ID | Section | Concern | Evidence-backed finding (sanitized) | Required work |
|---|---:|---|---|---|
| I15-001 | 15 | Strict Firefox AppArmor confinement is not established | Firefox was observed without strict AppArmor confinement in the historical USER snapshot; package profile semantics need review. | Design complete browser profile in isolated test build; verify compat before enforce; do not aa-enforce the placeholder. |
| I15-002 | 15 | AppArmor service policy and denial regression | Key system services appeared under enforced AppArmor profiles, but comprehensive deny/compatibility regressions are incomplete. | Gather role-matched current labels and sanitized denial counts; validate intentional exception handling. |
| I15-003 | 15 | USER versus SYSMAINT browser-label persistence | Browser confinement evidence exists in USER, not SYSMAINT; a role-specific persistence comparison is missing. | Confirm expected role separation after approved boot/browser update. |
| I15-004 | 16 | Privileged binary provenance/drift review | Privileged executable inventories were package-attributed; drift after upgrades remains to be reviewed. | Compare later package-owned SUID/SGID inventory to baseline; investigate only new paths. |
| I15-005 | 16 | gst-ptp-helper capability policy/compatibility | A package-provided multimedia helper carried capabilities; compatibility and least-privilege exceptions need review. | Record package version, capability purpose and risk acceptance; no blind setcap/strip. |
| I15-006 | 17 | setup-dist status-files 0777 exception monitoring | A vendor-maintained status directory is deliberately world-writable; blanket chmod would conflict with package behavior. | Verify package origin/upgrade behavior, threat acceptance and app compatibility before any proposed restriction. |
| I15-007 | 17 | Sensitive directory/ACL/umask and tmpfs drift | Restrictive umask and the documented temporary-filesystem protection were observed; broader permission and ACL drift needs monitoring. | Test effective modes, ACLs and /tmp semantics after package upgrades/reboot; do not recreate Section 01–14 patch. |
| I15-008 | 18 | faillock recovery and self-lockout policy | A restrictive faillock lockout policy was observed; self-lockout recovery and safety requirements need approval. | Define documented emergency recovery and owner-approved threshold change criteria without password guessing. |
| I15-009 | 18 | Passphrase/aging policy ownership | Yescrypt was observed; independent minimum passphrase and aging policy decisions remain outstanding. | Decide policy on minimum passphrase length, compromise reset and password aging; never collect passwords. |
| I15-010 | 18 | PAM USER/SYSMAINT interaction regression | Privileged USER/SYSMAINT authentication boundaries were observed; approved login-regression evidence remains limited. | Record authorized login/su/polkit behavior by boot role after package updates; avoid intentional lockouts. |
| I15-011 | 19 | Network SSH masking and listener persistence | Network-facing SSH listener was absent and SSH services masked in the inspected state; future updates need role-aware persistence checks. | Check paired-role listener and masking after reboot/update without enabling SSH. |
| I15-012 | 19 | Local SSH AF_UNIX socket and client key policy | A local-only SSH socket exception and SSH client key-handling requirements need explicit ongoing review. | Preserve socket; review known-hosts, private-key permissions and crypto policy locally without exporting secrets. |
| I15-013 | 20 | Role-specific systemd service drift and listening sockets | The two boot roles have different expected services; isolated snapshots cannot certify service persistence after updates. | Capture expected-role service activation and listener ownership after approved reboot/upgrade. |
| I15-014 | 20 | Classify unexpected/unused services safely | Required vendor services must be attributed before suggesting removal or disablement. | Make owner-approved exception/disable plan only after attribution and compatibility analysis. |
| I15-015 | 21 | Unbound systemd exposure score needs design decision | A systemd exposure score for the local DNS resolver does not itself demonstrate exploitable exposure; sandbox changes need lab testing. | Design optional hardening in test environment with DNS resolution and boot-role regression. |
| I15-016 | 21 | Service sandbox capability regression | Services have existing hardening settings; further capability restrictions require per-service regression. | Check package unit changes and test service behavior before any additional restrictions. |
| I15-017 | 22 | Core dump/pstore suppression drift | Crash-dump suppression controls were observed; repeatable drift verification is needed after kernel and package updates. | Verify effective sources and runtime after kernel upgrade/reboot; never generate a core or panic as part of audit. |
| I15-018 | 22 | Crash-forensics versus privacy trade-off | Reducing retained crash artifacts improves privacy but limits forensics; the trade-off remains a documented policy decision. | Document privacy/forensics exception and non-sensitive alternatives for incident response. |
| I15-019 | 23 | Journal retention, permissions and rotation policy | Journal integrity passed in an inspected context; retention, storage budgets and access policy still need owner review. | Approve retention bounds, storage budget, forwarding scope and log access without disabling journald. |
| I15-020 | 23 | sdwdate time and journal chronology after reboot | Secure-time usage is documented, but reboot-to-journal chronology needs a role-aware check. | Record role-matched service chronology and post-boot time/log consistency safely. |
| I15-021 | 24 | Owner-approved panic/recovery policy and escape paths | Emergency shell restrictions and vendor panic policy were observed; availability-versus-integrity trade-offs require approval. | Decide availability versus integrity policy and written recovery procedure without injecting panic/failed boot. |
| I15-022 | 24 | Emergency shutdown and controlled recovery evidence | Emergency shutdown was observed; destructive failure-mode testing has not been performed on the production laptop. | Use authorized isolated recovery scenario, boot media and rollback evidence only after explicit safety approval. |

**Interpretation:** The private 15–24 dossier describes its ten sections as technically *reconciled/closed*, not the 210 A/B/C acceptance gates as signed. Several findings are vendor exceptions or policy questions, not discovered vulnerabilities. The tracker contains **zero approved patch changes**.

### 6C. Sections 25–34: all 23 follow-up records

| ID | Section | Priority | Evidence-backed concern | Needed verification / controlled action |
|---|---:|---|---|---|
| I-001 | 26 | HIGH | Operator typed “allowed” in USB guide; functional keystroke confirmation and matching logs unavailable. | Verify physical typing and first matching authorized rule locally; do not reload policy. |
| I-002 | 26 | MEDIUM | 6 allow/26 reject rule verbs seen; device precedence and phone/Ethernet adapter untested. | Controlled per-device hotplug, current rule precedence and post-reboot results. |
| I-003 | 25 | MEDIUM | SYSMAINT one active swap file; B1 reported LUKS backing; role/time differences. | Private mapping of underlying crypto parent + key lifecycle, no sensitive key export. |
| I-004 | 25 | MEDIUM | Kernel alloc/free flags active; hook execution and cold-boot scope unresolved. | Inspect package hook/normal shutdown chronology; record risk exception. |
| I-005 | 27 | MEDIUM | Profile random configured; runtime/permanent comparison unknown. | Supervised local comparison and radio/peer observation. |
| I-006 | 27 | MEDIUM | DHCP client-ID unspecified; emitted identifier not inspected. | Controlled reconnection on owned network without uploading identifiers. |
| I-007 | 28 | LOW | Kernel disabled across USER reboot, but other profiles and AF_INET6 sockets not independently validated. | Review alternate profile/listeners and browser regression; confirm policy remains disablement. |
| I-008 | 29 | MEDIUM | Service and localhost resolver observed; transition behavior missing. | Controlled network-change and resolver fallback check with console recovery. |
| I-009 | 30 | HIGH | TLS forward-zone declared; socket sightings cannot prove process-bound authenticated certificate checking. | Correlate Unbound-owned session, trusted name and chain with approved upstream diagnostics. |
| I-010 | 30 | HIGH | Authorized external resolver absent; outbound nft rules appear to target port 53 but verdict unknown. | Construct approved owned controlled responder and test UDP and TCP separately; counters required. |
| I-011 | 30 | MEDIUM | One Firefox pref file mode 5; active profile and Tor Browser behavior not independently confirmed. | USER browser runtime and profile-specific DNS inspection. |
| I-012 | 31 | HIGH | Output policy accept, 2 candidate port53 drop/reject rules; actual packet verdict unobserved. | Review nft rule order/protocol selectors and authorized packet/counter correlation; preserve rollback. |
| I-013 | 31 | MEDIUM | B2 supports service active across reboot, not identical ruleset. | Compare normalized loaded nft state across approved USER boots. |
| I-014 | 32 | MEDIUM | Four protocol outcomes all inconclusive in LAN guide. | Capture or observe protocol-specific replies from owned peer with protocol labels. |
| I-015 | 33 | MEDIUM | Tor active; no designated browser-specific enforcement check completed. | Define scoped applications and test Tor Browser proxy/DNS safely; no global Tor stop. |
| I-016 | 34 | MEDIUM | sdwdate/time sanity/boot randomization active with zero error keywords; actual one-shot steps unclear. | Review unit type/journals across boot/resume; VM-only jump simulation. |
| I-017 | 25 | MEDIUM | Most uploaded code is verifier logic; original applying script/commit unavailable. | Gather original change artifacts, package metadata and redacted configuration diffs before claiming reproducibility. |
| I-018 | 26 | LOW | ISO9660 Kicksecure installation medium allowed/detected but not auto-mounted. | No fix unless normal removable data storage is a requirement; preserve installation/recovery USB. |
| I-019 | 28 | MEDIUM | Past plans contemplated advanced IPv6 privacy, current system uses ipv6.disable=1. | Make a written decision on disabled vs dual-stack policy before any future implementation. |
| I-020 | 29 | MEDIUM | Unbound active in USER, intentionally may differ in SYSMAINT. | Record explicit service-role matrix; prevent cross-role false failures. |
| I-021 | 30 | MEDIUM | Repeated B3.1 DNSSEC response statuses observed; no assertion review signed. | Review source IDs and negative-test methodology before acceptance. |
| I-022 | 32 | LOW | Static service inventory does not establish multicast behavior. | Map per-service listeners and observed peer traffic. |
| I-023 | 34 | LOW | Clock rollback or secure-time attack simulation inappropriate on current laptop. | Reserve disposable VM and document expected outcome / residual risk. |

**Latest v6.1 interpretation:** USER and SYSMAINT diagnostic runs completed with checksummed summaries, but they did not fully execute every A/B/C gate. The supervised LAN guide recorded *inconclusive* peer observations. A spare USB keyboard was operator-reported "allowed" despite an intended deny rule; functionality was not independently proven, so this remains a **potential** policy deviation. The USB installation medium was detected and authorized as intended. No external DNS egress test was run without a controlled authorized endpoint.

### 6D. Sections 35–44: provisional acceptance and future work plan

| Section | Historical evidence available | Required future evidence, action or decision | Current disposition |
|---|---|---|---|
| 35 — Entropy / RNG | Historical entropy/rng evidence and seed-management policy reviewed; target-side current run unavailable. | Record early-boot quality, seed handling, package choices and role-matched persistence. | PROVISIONAL — TARGET TEST / SIGN-OFF PENDING |
| 36 — Browser DoH / WebRTC / Telemetry | Historical browser preference source restrictions; effective runtime prefs were not conclusively established. | Run USER browser checks for DNS-over-HTTPS, WebRTC leakage, telemetry and upgrades. | PROVISIONAL — TARGET TEST / SIGN-OFF PENDING |
| 37 — Application / File / Metadata Privacy | Historical metadata/indexing and synthetic sanitization observations reported. | Revisit app caches, thumbnails, history retention and runtime confinement. | PROVISIONAL — TARGET TEST / SIGN-OFF PENDING |
| 38 — Camera / Microphone / Power / Screen Lock | Historical USER camera/mic access denial, screen-lock configuration noted. | Prove actual idle lock, lid/suspend/resume authentication and hotplug behavior. | PROVISIONAL — TARGET TEST / SIGN-OFF PENDING |
| 39 — Firmware / BIOS / Secure Boot / TPM | Historical Secure Boot/MOK and TPM observations; fwupd HSI:1! needs interpretation. | Owner-controlled firmware/DMA/boot policy inspection; no blind MOK re-enrollment. | PROVISIONAL — TARGET TEST / SIGN-OFF PENDING |
| 40 — Auditd / AIDE / Integrity Monitoring | Five USER audit rule keys and existing AIDE evidence described historically. | Verify permitted audit event retrieval, AIDE alert lifecycle and retention; do not reinitialize AIDE. | PROVISIONAL — TARGET TEST / SIGN-OFF PENDING |
| 41 — Cron / Timers / Persistence / Supply Chain | Historical timer/cron and dpkg provenance checks exist. | Establish desktop autostart provenance, signing sources and two-boot drift. | PROVISIONAL — TARGET TEST / SIGN-OFF PENDING |
| 42 — Credentials / SSH Keys / Secrets / Backup | SSH restricted, disposable backup/crypto fixture documented; production restore not shown. | Complete actual encrypted backup, isolated restore and release-secret exclusion. | PROVISIONAL — TARGET TEST / SIGN-OFF PENDING |
| 43 — CIS / DISA GPOS / KSPP Mapping | Preliminary CIS/DISA/KSPP mapping undertaken; many entries need evidence review. | Confirm applicability and source mapping one by one; no certification claim. | PROVISIONAL — TARGET TEST / SIGN-OFF PENDING |
| 44 — Final Acceptance / Evidence / Scoring | No completed archived Section 44 execution report. | Complete two-role/two-boot regressions, negative tests, recovery and final owner sign-off. | PROVISIONAL — TARGET TEST / SIGN-OFF PENDING |

**Historical caution:** The old Section 39 MOK-warning classification and Section 40 AIDE argument error were resolved or reinterpreted by later evidence. Do not invent new key enrollment or initialize a fresh integrity baseline solely to clear those old diagnostic warnings. Section 43 historical "evidence review" recommendations are not a tally of proven vulnerabilities. Section 44 remains a formal acceptance gate, not a performed security assessment.

## 7. Complete 44-section evidence orientation

The following section summaries indicate which implementation evidence exists and the exact *kind of proof still required*. This makes the register useful for external reviewers without releasing private target logs.

### 01 — Platform / OS / Hardware Baseline

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** Platform and OS baseline documented in 01–14 technical dossier.

**What still needs evidence or action:** Refresh actual hardware/OS scope before translating source-only observations into accepted controls.

**Seven registered families:** `01.01` Operating-system identity and Debian/Kicksecure release baseline; `01.02` Kernel release, architecture and build identity; `01.03` CPU model, topology and virtualization capability; `01.04` Physical memory and swap capacity baseline; `01.05` Storage controller, disk and filesystem topology; `01.06` UEFI/bare-metal/virtualization platform state; `01.07` Failed-unit, uptime, boot-time and baseline health state.

---

### 02 — Kicksecure Package Provenance

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** Kicksecure package provenance recorded; a package-classifier discrepancy was documented.

**What still needs evidence or action:** Reconcile exact package ownership and versions; do not prescribe installing absent packages based on heuristic names.

**Seven registered families:** `02.01` Core Kicksecure package installation and exact versions; `02.02` Supporting security-package installation and exact versions; `02.03` APT source files and repository configuration; `02.04` APT policy and repository origin attribution; `02.05` Package ownership of security-critical configuration files; `02.06` Package holds, partial installs and dpkg database health; `02.07` Local modifications versus package-owned baseline.

---

### 03 — USER / SYSMAINT Privilege Architecture

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** Privilege separation and USER execution restrictions observed.

**What still needs evidence or action:** Verify boot-role and upgrade regressions without weakening SYSMAINT boundaries.

**Seven registered families:** `03.01` USER, SYSMAINT and root account separation; `03.02` Distinct UID/GID and home-directory boundaries; `03.03` user-sysmaint-split package and owned policy files; `03.04` sudo binary ownership, mode and SYSMAINT-only execution; `03.05` sudoers syntax and user-sysmaint- split policy; `03.06` USER negative sudo/root acquisition probe; `03.07` Login-shell and boot-role separation behavior.

---

### 04 — SYSMAINT Boot Role

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** Dedicated administrative boot markers and expected unit separation documented.

**What still needs evidence or action:** Validate appropriate services in each boot role and persistence following updates.

**Seven registered families:** `04.01` boot-role=sysmaint kernel marker; `04.02` systemd.unit=sysmaint-boot.target marker; `04.03` sysmaint-boot.target package provenance and unit content; `04.04` Required SYSMAINT dependencies and wanted units; `04.05` Intentionally omitted USER-only or incompatible hardeners; `04.06` Conflicting USER/graphical boot-role negative checks; `04.07` Failed units and SYSMAINT boot health.

---

### 05 — Accounts / UID / GID / Local Identity

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** Account inventory and root-lock evidence documented.

**What still needs evidence or action:** Resolve role/service-account classification and verify policy compatibility.

**Seven registered families:** `05.01` root, USER and SYSMAINT account identity; `05.02` Duplicate UID and duplicate GID detection; `05.03` UID 0 exclusivity and privileged- account review; `05.04` Low-UID service-account shell classification; `05.05` Home-directory ownership and permissions; `05.06` shadow/gshadow/passwd/group ownership and modes; `05.07` NSS identity source configuration and root lock state.

---

### 06 — LUKS / Disk / Swap Encryption

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** LUKS2 encrypted root with encrypted-root-backed swap was documented.

**What still needs evidence or action:** Validate key-recovery and restore evidence privately; do not publish secrets.

**Seven registered families:** `06.01` Root filesystem source and dm-crypt mapping; `06.02` LUKS2 backing partition and cryptsetup status; `06.03` LUKS header metadata without key- material disclosure; `06.04` Root encryption chain from block device to mountpoint; `06.05` Active swap inventory and encrypted placement; `06.06` swapfile ownership, mode and containing filesystem; `06.07` crypttab/fstab encryption persistence and boot mapping.

---

### 07 — Filesystem / Mount Security

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** A targeted temporary-filesystem mount hardening change was applied and verified after USER reboot.

**What still needs evidence or action:** Resolve separate boot-mount ordering and compatibility exceptions; SYSMAINT corroboration remains.

**Seven registered families:** `07.01` Effective mount table and filesystem inventory; `07.02` Root mount source, filesystem and options; `07.03` /boot and /boot/efi separation, ownership and exposure; `07.04` /tmp tmpfs, sticky bit and mount- option review; `07.05` /var/tmp sticky-bit and separate- mount review; `07.06` /home containment, ownership and inherited options; `07.07` Writable mountpoints, fstab and remount-secure review.

---

### 08 — GRUB / Bootloader Protection

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** GRUB protection directives were present in historical source review.

**What still needs evidence or action:** Physical boot-edit negative test and tested recovery remain pending.

**Seven registered families:** `08.01` GRUB package baseline and generated grub.cfg; `08.02` grub.cfg ownership, permissions and menu entries; `08.03` GRUB password_pbkdf2 and superusers directives; `08.04` Kicksecure CPU/kernel/ram-wipe/remount/signed -module fragments; `08.05` Quiet-boot and recovery-restriction fragments; `08.06` Effective boot command-line correlation; `08.07` /boot and EFI exposure versus cryptographic integrity limits.

---

### 09 — CPU Vulnerability Mitigations

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** SMT and CPU vulnerability mitigations were inspected; some kernel flags were not fully attributable.

**What still needs evidence or action:** Confirm effective kernel features before making CFI/KCFI claims.

**Seven registered families:** `09.01` CPU identity, vendor and mitigation- capability baseline; `09.02` SMT/Hyper-Threading disablement and topology; `09.03` Runtime microcode revision and package baseline; `09.04` Kernel vulnerability-interface enumeration; `09.05` Spectre/Meltdown/L1TF/MDS/ Retbleed/BHI/SSB/TAA/GDS mitigations; `09.06` Mitigation-related kernel command- line parameters; `09.07` CPU mitigation flags and kernel-log confirmation.

---

### 10 — IOMMU / DMA Protection

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** IOMMU, strict invalidation and interrupt remapping were observed historically.

**What still needs evidence or action:** Confirm preboot DMA and firmware applicability with safe manual tests.

**Seven registered families:** `10.01` CPU virtualization/VT-d capability baseline; `10.02` IOMMU kernel parameters and passthrough policy; `10.03` DMAR/IOMMU runtime enablement; `10.04` Translated default domain and strict invalidation; `10.05` IRQ/interrupt remapping; `10.06` IOMMU group topology and full PCI membership; `10.07` Early PCI DMA restriction and firmware WSMT evidence.

---

### 11 — Kernel Sysctl Hardening

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** Restrictive kernel and network sysctls were observed.

**What still needs evidence or action:** Map package-owned precedence and persist expected values after upgrades.

**Seven registered families:** `11.01` Sysctl source-tree inventory and precedence; `11.02` Kicksecure security-misc sysctl source files; `11.03` Kernel information-leak restrictions; `11.04` ASLR, mmap, kexec and privileged- coredump controls; `11.05` BPF, ptrace, perf and TTY line- discipline restrictions; `11.06` Protected links/FIFOs/regular-file controls; `11.07` Network-stack sysctl hardening observations.

---

### 12 — Kernel Boot / Memory Hardening

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** Memory initialization/kernel boot flags were inspected in source and runtime.

**What still needs evidence or action:** Separate effective kernel capability from mere presence of boot tokens.

**Seven registered families:** `12.01` Slab allocator hardening and slab_nomerge; `12.02` init_on_alloc and init_on_free memory initialization; `12.03` page allocator shuffle and stack randomization; `12.04` vsyscall, vdso32 and 32-bit compatibility restrictions; `12.05` debugfs, KFENCE and kernel debug- surface controls; `12.06` CFI/KCFI and boot-time control acceptance; `12.07` pstore/ERST/proc_mem/entropy trust boot parameters.

---

### 13 — Kernel Module Restrictions

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** Module restrictions and exceptions were inspected.

**What still needs evidence or action:** Resolve built-in versus loadable module behavior and compatibility.

**Seven registered families:** `13.01` security-misc module blacklist configuration; `13.02` Hard-disable install rules for risky modules; `13.03` Loaded-module inventory versus policy; `13.04` Legacy filesystem module restrictions; `13.05` Legacy network/protocol module restrictions; `13.06` USB/storage/media module restriction exceptions; `13.07` Module-load negative tests and compatibility exceptions.

---

### 14 — Kernel Module Signing / DKMS

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** Later privileged evidence observed signed DKMS builds and enabled Secure Boot.

**What still needs evidence or action:** Validate signer chain and upgrade behavior without re-enrolling keys unnecessarily.

**Seven registered families:** `14.01` Loaded-module signer inventory; `14.02` DKMS package and built-module inventory; `14.03` tirdad DKMS build, signer and runtime state; `14.04` NVIDIA/other third-party module signer state; `14.05` Kernel module signature enforcement capability; `14.06` MOK/enrolled certificate readiness; `14.07` Secure-Boot compatibility and unsigned-module exceptions.

---

### 15 — AppArmor / Mandatory Access Control

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** AppArmor active; selected services enforced; strict Firefox confinement not established.

**What still needs evidence or action:** Plan compatible browser confinement in a test environment before any package-profile changes.

**Linked follow-ups:** `I15-001`, `I15-002`, `I15-003`.

**Seven registered families:** `15.01` AppArmor kernel/module enablement; `15.02` Profile inventory and parser status; `15.03` Enforce/complain/unconfined process counts; `15.04` Tor and network-service profile enforcement; `15.05` Browser/application profile coverage; `15.06` Denied-event review and false-positive handling; `15.07` USER versus SYSMAINT AppArmor behavior.

---

### 16 — SUID / SGID / File Capabilities

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** Privileged binaries/capabilities were inventoried and package-attributed.

**What still needs evidence or action:** Review drift and package capabilities without blind permission changes.

**Linked follow-ups:** `I15-004`, `I15-005`.

**Seven registered families:** `16.01` Complete SUID file inventory; `16.02` Complete SGID file inventory; `16.03` Package ownership of privileged binaries; `16.04` permission-hardener expected mode validation; `16.05` File-capability inventory and package attribution; `16.06` Unexpected privileged executable detection; `16.07` Privilege-binary negative/compatibility review.

---

### 17 — Permissions / ACL / Umask

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** Restrictive permissions/umask observed; one package-owned world-writable status cache documented.

**What still needs evidence or action:** Classify intended vendor exception and monitor unexpected permission drift.

**Linked follow-ups:** `I15-006`, `I15-007`.

**Seven registered families:** `17.01` System file ownership baseline; `17.02` World-writable system path inventory; `17.03` Unexpected group-writable sensitive paths; `17.04` ACL inventory on sensitive configuration; `17.05` Root and user umask policy; `17.06` Home and evidence-directory permissions; `17.07` Sticky-bit and shared-directory permission policy.

---

### 18 — PAM / Login / Faillock

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** Yescrypt and faillock observed; root locked and USER/SYSMAINT split preserved.

**What still needs evidence or action:** Prove safe recovery from lockout and decide local passphrase/aging requirements.

**Linked follow-ups:** `I15-008`, `I15-009`, `I15-010`.

**Seven registered families:** `18.01` PAM stack package provenance; `18.02` password quality and hashing policy; `18.03` faillock/brute-force lockout policy; `18.04` login delay and retry controls; `18.05` su/sudo/polkit PAM interaction; `18.06` account aging and inactive-account policy; `18.07` USER/SYSMAINT login regression tests.

---

### 19 — SSH Client / Server Security

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** Network SSH service masked with no ordinary TCP listener in inspected state.

**What still needs evidence or action:** Preserve local exception and validate state after upgrades and recovery.

**Linked follow-ups:** `I15-011`, `I15-012`.

**Seven registered families:** `19.01` Local SSH server service/socket state; `19.02` sshd listener and inbound port absence; `19.03` sshd_config security-misc policy if installed; `19.04` SSH client configuration and host-key verification; `19.05` Private-key ownership and permission baseline; `19.06` Password-authentication and root-login policy for future server use; `19.07` Known-hosts/key algorithm and crypto-policy review.

---

### 20 — Enabled / Running Service Audit

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** Services and sockets inventoried independently across roles.

**What still needs evidence or action:** Classify dependencies and verify expected-role persistence; do not disable blindly.

**Linked follow-ups:** `I15-013`, `I15-014`.

**Seven registered families:** `20.01` Enabled systemd service inventory; `20.02` Running systemd service inventory; `20.03` Socket/path/timer activated service inventory; `20.04` Kicksecure-required service attribution; `20.05` Unexpected or unnecessary service classification; `20.06` Listener-to-service ownership correlation; `20.07` Reboot persistence and failed-service review.

---

### 21 — systemd Service Sandboxing

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** Service sandboxing present; local resolver systemd score documented as context-dependent.

**What still needs evidence or action:** Rehearse proposed additional sandbox restrictions without breaking DNS.

**Linked follow-ups:** `I15-015`, `I15-016`.

**Seven registered families:** `21.01` systemd-analyze security baseline; `21.02` NoNewPrivileges adoption; `21.03` ProtectSystem/ProtectHome restrictions; `21.04` PrivateTmp/PrivateDevices isolation; `21.05` CapabilityBoundingSet and ambient capabilities; `21.06` RestrictNamespaces/SystemCallFilter/address-family controls; `21.07` Service-specific compatibility exceptions and regressions.

---

### 22 — System.map / Core Dumps / PStore

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** Core-dump/pstore suppression observed.

**What still needs evidence or action:** Confirm ongoing enforcement after updates; record forensic trade-offs.

**Linked follow-ups:** `I15-017`, `I15-018`.

**Seven registered families:** `22.01` System.map exposure and removal policy; `22.02` systemd-coredump configuration; `22.03` kernel.core_pattern effective state; `22.04` fs.suid_dumpable effective state; `22.05` pstore retention/disable policy; `22.06` EFI pstore and ERST boot controls; `22.07` Crash-evidence privacy versus diagnostic requirements.

---

### 23 — Journald / Logging / Logrotate

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** Journal integrity verified in historical privileged context.

**What still needs evidence or action:** Approve retention/rotation/access policy and time continuity evidence.

**Linked follow-ups:** `I15-019`, `I15-020`.

**Seven registered families:** `23.01` journald security-misc configuration; `23.02` Persistent versus volatile journal storage; `23.03` Journal file permissions and ownership; `23.04` Rate limiting and size/retention policy; `23.05` Forwarding/syslog integration state; `23.06` logrotate configuration and sensitive-log modes; `23.07` Log integrity, time coherence and reboot persistence.

---

### 24 — Panic / Recovery / Emergency Shutdown

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** Recovery restrictions and emergency-shutdown component observed.

**What still needs evidence or action:** Rehearse safe recovery offline; no destructive production panic tests.

**Linked follow-ups:** `I15-021`, `I15-022`.

**Seven registered families:** `24.01` kernel panic-on-oops policy; `24.02` panic timeout and fail-closed behavior; `24.03` emerg-shutdown.service provenance and state; `24.04` rescue/emergency target restrictions; `24.05` rd.emergency=halt and rd.shell=0 behavior; `24.06` Magic SysRq and recovery-surface policy; `24.07` Controlled failure/recovery evidence and rollback.

---

### 25 — RAM Wipe

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** Kernel memory initialization flags observed; encrypted root/swap ancestry partly supported.

**What still needs evidence or action:** Confirm shutdown hooks, swap crypto path and residual cold-boot risk.

**Linked follow-ups:** `I-003`, `I-004`, `I-017`.

**Seven registered families:** `25.01` ram-wipe package provenance and version; `25.02` GRUB/package RAM-wipe source presence; `25.03` init_on_alloc/init_on_free live correlation; `25.04` Shutdown/reboot wipe hook inventory; `25.05` Swap/LUKS interaction during shutdown; `25.06` Controlled reboot/shutdown persistence test; `25.07` Limitations of software RAM wiping and cold-boot scope.

---

### 26 — USBGuard / Peripheral Security

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** USBGuard loaded rule inventory; owned mouse and recovery USB appeared authorized.

**What still needs evidence or action:** Verify keyboard rejection through real keystroke test and first-match logs; test composite and network devices.

**Linked follow-ups:** `I-001`, `I-002`, `I-018`.

**Seven registered families:** `26.01` usbguard daemon and DBus service state; `26.02` Policy files and rule provenance; `26.03` ImplicitPolicyTarget and device-policy settings; `26.04` Allowed keyboard/mouse/audio/video/storage classes; `26.05` Rejected HID+extra and RNDIS/network-device patterns; `26.06` IPC authorization/notifier behavior; `26.07` Hot-plug negative tests and reboot persistence.

---

### 27 — NetworkManager / Wi-Fi / MAC / DHCP

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** Active Wi-Fi profile configured for randomized MAC.

**What still needs evidence or action:** Correlate over-air identity and DHCP identifier on owned network; persist after reconnect.

**Linked follow-ups:** `I-005`, `I-006`.

**Seven registered families:** `27.01` NetworkManager package/service state; `27.02` Saved Wi-Fi profile inventory and autoconnect; `27.03` Active-profile cloned-MAC and DHCP privacy settings; `27.04` Scan MAC randomization; `27.05` Ethernet MAC randomization policy; `27.06` Runtime MAC versus permanent hardware MAC; `27.07` DHCP client identifier and profile persistence.

---

### 28 — IPv6 Policy

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** IPv6 appeared disabled across inspected USER boots.

**What still needs evidence or action:** Resolve intentional disablement versus future advanced dual-stack privacy policy before changes.

**Linked follow-ups:** `I-007`, `I-019`.

**Seven registered families:** `28.01` ipv6.disable=1 boot parameter; `28.02` Absence of IPv6 addresses; `28.03` Absence of IPv6 routes; `28.04` NetworkManager IPv6 method/state; `28.05` Resolver absence of IPv6 nameservers; `28.06` IPv6 TCP/UDP listener exposure; `28.07` Reboot persistence and DNS/HTTPS regression test.

---

### 29 — Unbound / Local DNS Architecture

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** Local Unbound listener/service recorded in USER; different SYSMAINT role semantics expected.

**What still needs evidence or action:** Confirm DHCP transition and resolver fail-safe without inadvertently breaking browsing.

**Linked follow-ups:** `I-008`, `I-020`.

**Seven registered families:** `29.01` Unbound package/service state; `29.02` loopback DNS listener UDP/TCP listener and non-loopback absence; `29.03` resolv.conf local-resolver wiring; `29.04` NetworkManager effective DNS assignment; `29.05` Unbound configuration include tree validation; `29.06` DoT forward-zone and IPv6 source policy; `29.07` USER/SYSMAINT service behavior and persistence.

---

### 30 — DNSSEC / DoT / DNS Leak Prevention

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** DNSSEC success and deliberate bogus-domain failure observed; DoT forwarding configured.

**What still needs evidence or action:** Demonstrate Unbound-owned authenticated TLS; prove UDP/TCP direct DNS egress policy with owned peer.

**Linked follow-ups:** `I-009`, `I-010`, `I-011`, `I-021`.

**Seven registered families:** `30.01` DNSSEC positive validation test; `30.02` Broken-DNSSEC negative test; `30.03` DoT forwarding configuration and reachability scope; `30.04` Plaintext external UDP/53 block; `30.05` Plaintext external TCP/53 block; `30.06` Local DNS functionality after firewall enforcement; `30.07` DNS leak/bypass and reboot-persistence testing.

---

### 31 — nftables Firewall

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** Structured firewall inspection observed inbound/forward protections and candidate outbound DNS rules.

**What still needs evidence or action:** Prove effective outbound packet verdict and exact loaded-ruleset persistence.

**Linked follow-ups:** `I-012`, `I-013`.

**Seven registered families:** `31.01` nftables package/service/runtime ruleset state; `31.02` Dedicated inet kicksecure_hardening table; `31.03` Input default-drop policy; `31.04` Forward default-drop policy; `31.05` Loopback, established/related and invalid handling; `31.06` DHCP/ICMP and required inbound exceptions; `31.07` Static syntax, reload safety and reboot persistence.

---

### 32 — LAN Discovery / Multicast / LLMNR / mDNS

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** Static LAN service inventory available, but four owned-peer guide outcomes inconclusive.

**What still needs evidence or action:** Collect protocol-specific peer mDNS/LLMNR/SSDP evidence; do not infer from unicast scans.

**Linked follow-ups:** `I-014`, `I-022`.

**Seven registered families:** `32.01` Avahi/mDNS daemon state; `32.02` LLMNR/resolved multicast name-resolution state; `32.03` wsdd/Samba discovery state; `32.04` rpcbind/minidlna/UPnP service state; `32.05` Multicast/discovery TCP+UDP listener inventory; `32.06` Firewall exposure of discovery ports; `32.07` Negative LAN discovery and reboot-persistence test.

---

### 33 — Tor / SOCKS / DNS Isolation

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** Tor service was active in the inspected USER context.

**What still needs evidence or action:** Test Tor Browser-specific proxy/DNS routing and safe fail-close without a disruptive global service stop.

**Linked follow-ups:** `I-015`.

**Seven registered families:** `33.01` Tor package/service state; `33.02` SOCKS listener loopback Tor SOCKS listener and non-loopback absence; `33.03` Tor configuration provenance and syntax validation; `33.04` Application proxy routing where intended; `33.05` Tor DNS isolation behavior; `33.06` Clearnet bypass classification for Tor-mode applications; `33.07` Bootstrap, circuit, restart and failure-mode behavior.

---

### 34 — sdwdate / Secure Time / Boot Clock

**Disposition:** DOCUMENTATION BASELINE COMPLETE; FORMAL A/B/C REVIEW OPEN.

**Documented/observed:** Secure-time components active, no error keywords in bounded log view.

**What still needs evidence or action:** Review execution chronology and controlled VM-only clock rollback.

**Linked follow-ups:** `I-016`, `I-023`.

**Seven registered families:** `34.01` sdwdate package/service state; `34.02` timesanitycheck execution state; `34.03` bootclockrandomization execution state; `34.04` System clock sanity metadata; `34.05` NTP/systemd-timesyncd conflicts; `34.06` USER versus SYSMAINT time-source behavior; `34.07` Time rollback/jump detection and log coherence.

---

### 35 — Entropy / RNG

**Disposition:** PROVISIONAL HISTORICAL REVIEW; TARGET VERIFICATION PENDING.

**Documented/observed:** Historical entropy/rng evidence and seed-management policy reviewed; target-side current run unavailable.

**What still needs evidence or action:** Record early-boot quality, seed handling, package choices and role-matched persistence.

**Seven registered families:** `35.01` Kernel RNG readiness at boot; `35.02` haveged package/service state; `35.03` jitterentropy-rngd package/service state; `35.04` random.trust_cpu boot policy; `35.05` random.trust_bootloader boot policy; `35.06` Entropy source and /dev/random behavior; `35.07` Early-boot entropy persistence and regression evidence.

---

### 36 — Browser DoH / WebRTC / Telemetry

**Disposition:** PROVISIONAL HISTORICAL REVIEW; TARGET VERIFICATION PENDING.

**Documented/observed:** Historical browser preference source restrictions; effective runtime prefs were not conclusively established.

**What still needs evidence or action:** Run USER browser checks for DNS-over-HTTPS, WebRTC leakage, telemetry and upgrades.

**Seven registered families:** `36.01` Browser DNS-over-HTTPS/TRR setting; `36.02` Browser proxy DNS routing behavior; `36.03` WebRTC/STUN local/public IP exposure; `36.04` Telemetry and crash-report settings; `36.05` Safe browsing/prediction/background network features; `36.06` Extension/add-on inventory and trust; `36.07` Browser update, profile persistence and leak tests.

---

### 37 — Application / File / Metadata Privacy

**Disposition:** PROVISIONAL HISTORICAL REVIEW; TARGET VERIFICATION PENDING.

**Documented/observed:** Historical metadata/indexing and synthetic sanitization observations reported.

**What still needs evidence or action:** Revisit app caches, thumbnails, history retention and runtime confinement.

**Seven registered families:** `37.01` Desktop search/indexing services; `37.02` Thumbnail and preview cache behavior; `37.03` Recent-files/history and clipboard retention; `37.04` Document/image metadata handling; `37.05` Temporary-file and application-cache exposure; `37.06` Sandboxed versus unsandboxed application inventory; `37.07` Metadata-removal workflow and regression testing.

---

### 38 — Camera / Microphone / Power / Screen Lock

**Disposition:** PROVISIONAL HISTORICAL REVIEW; TARGET VERIFICATION PENDING.

**Documented/observed:** Historical USER camera/mic access denial, screen-lock configuration noted.

**What still needs evidence or action:** Prove actual idle lock, lid/suspend/resume authentication and hotplug behavior.

**Seven registered families:** `38.01` Camera hardware/device exposure; `38.02` Microphone hardware/device exposure; `38.03` Bluetooth/rfkill interaction with peripherals; `38.04` Screen-lock timeout and authentication; `38.05` Suspend/lock-on-lid and idle behavior; `38.06` Hibernation configuration and encrypted-swap implications; `38.07` Shutdown-versus-suspend operational policy.

---

### 39 — Firmware / BIOS / Secure Boot / TPM

**Disposition:** PROVISIONAL HISTORICAL REVIEW; TARGET VERIFICATION PENDING.

**Documented/observed:** Historical Secure Boot/MOK and TPM observations; fwupd HSI:1! needs interpretation.

**What still needs evidence or action:** Owner-controlled firmware/DMA/boot policy inspection; no blind MOK re-enrollment.

**Seven registered families:** `39.01` BIOS/UEFI vendor, model and firmware version; `39.02` fwupd device/security-attribute inventory; `39.03` Secure Boot state and Setup Mode; `39.04` TPM presence, version and ownership state; `39.05` BIOS/UEFI administrator password manual check; `39.06` PXE/CSM/external-boot/manual boot- order policy; `39.07` Firmware update, DKMS/MOK and Secure-Boot readiness.

---

### 40 — Auditd / AIDE / Integrity Monitoring

**Disposition:** PROVISIONAL HISTORICAL REVIEW; TARGET VERIFICATION PENDING.

**Documented/observed:** Five USER audit rule keys and existing AIDE evidence described historically.

**What still needs evidence or action:** Verify permitted audit event retrieval, AIDE alert lifecycle and retention; do not reinitialize AIDE.

**Seven registered families:** `40.01` auditd package/service state; `40.02` Audit rule inventory and immutable/finalize policy; `40.03` Privileged-command and identity- change audit coverage; `40.04` AIDE package/database/configuration state; `40.05` File-integrity baseline and scheduled checks; `40.06` Audit-log ownership, rotation and tamper resistance; `40.07` CIS/DISA accountability-gap analysis.

---

### 41 — Cron / Timers / Persistence / Supply Chain

**Disposition:** PROVISIONAL HISTORICAL REVIEW; TARGET VERIFICATION PENDING.

**Documented/observed:** Historical timer/cron and dpkg provenance checks exist.

**What still needs evidence or action:** Establish desktop autostart provenance, signing sources and two-boot drift.

**Seven registered families:** `41.01` cron/anacron job inventory; `41.02` systemd timer inventory; `41.03` User autostart and desktop persistence inventory; `41.04` Package repository and signing-key provenance; `41.05` APT pinning/holds and update-policy review; `41.06` Unexpected startup scripts/services/modules; `41.07` Supply-chain drift and reboot- persistence evidence.

---

### 42 — Credentials / SSH Keys / Secrets / Backup

**Disposition:** PROVISIONAL HISTORICAL REVIEW; TARGET VERIFICATION PENDING.

**Documented/observed:** SSH restricted, disposable backup/crypto fixture documented; production restore not shown.

**What still needs evidence or action:** Complete actual encrypted backup, isolated restore and release-secret exclusion.

**Seven registered families:** `42.01` SSH private-key inventory and permissions; `42.02` API/token/secret storage locations; `42.03` Password-manager selection and vault policy; `42.04` FIDO2/YubiKey readiness and hardware-backed keys; `42.05` Recovery-code generation and offline storage; `42.06` Encrypted backup creation and retention; `42.07` Restore test, key recovery and disaster-recovery evidence.

---

### 43 — CIS / DISA GPOS / KSPP Mapping

**Disposition:** PROVISIONAL HISTORICAL REVIEW; TARGET VERIFICATION PENDING.

**Documented/observed:** Preliminary CIS/DISA/KSPP mapping undertaken; many entries need evidence review.

**What still needs evidence or action:** Confirm applicability and source mapping one by one; no certification claim.

**Seven registered families:** `43.01` CIS Debian 13 Level 2 applicability mapping; `43.02` DISA GPOS/SRG objective mapping; `43.03` KSPP/kernel-self-protection mapping; `43.04` Kicksecure-native equivalent control mapping; `43.05` Project-extension control mapping; `43.06` Exception/N-A/manual-control rationale; `43.07` Evidence citation and no-certification disclaimer.

---

### 44 — Final Acceptance / Evidence / Scoring

**Disposition:** PROVISIONAL HISTORICAL REVIEW; TARGET VERIFICATION PENDING.

**Documented/observed:** No completed archived Section 44 execution report.

**What still needs evidence or action:** Complete two-role/two-boot regressions, negative tests, recovery and final owner sign-off.

**Seven registered families:** `44.01` Full reboot persistence acceptance; `44.02` USER-mode regression acceptance; `44.03` SYSMAINT-mode regression acceptance; `44.04` Network/DNS/firewall/Tor/USB negative-test acceptance; `44.05` Recovery/rollback/backup acceptance; `44.06` Evidence completeness, hashes and chain-of-custody bundle; `44.07` Final scorecard, residual risk and operator sign-off.

---

## 8. Master technical control register — 308 families / 924 gates

Every official family appears below. These are **public acceptance requirements**, not confidential configuration dumps. All A/B/C sign-offs are **OPEN** pending authorized evidence review. Section-specific implementation status is established in Sections 5–7 above and the associated technical dossiers.

**How to use this register:** For A, inspect dated package/config provenance and approved change history. For B, obtain correct-role runtime and authorized negative testing. For C, perform controlled reboot/update/reconnect/recovery or record justified nonapplicability. For each family, review the section-specific evidence gap before ordering a modification.

### Section 01: Platform / OS / Hardware Baseline

#### 01.01 — Operating-system identity and Debian/Kicksecure release baseline

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of operating-system identity and debian/kicksecure release baseline; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Refresh actual hardware/OS scope before translating source-only observations into accepted controls.
- **Acceptance IDs:** `KHAHP-01.01A`, `KHAHP-01.01B`, `KHAHP-01.01C` — **OPEN / NOT SIGNED OFF**.

#### 01.02 — Kernel release, architecture and build identity

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of kernel release, architecture and build identity; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Refresh actual hardware/OS scope before translating source-only observations into accepted controls.
- **Acceptance IDs:** `KHAHP-01.02A`, `KHAHP-01.02B`, `KHAHP-01.02C` — **OPEN / NOT SIGNED OFF**.

#### 01.03 — CPU model, topology and virtualization capability

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of cpu model, topology and virtualization capability; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Refresh actual hardware/OS scope before translating source-only observations into accepted controls.
- **Acceptance IDs:** `KHAHP-01.03A`, `KHAHP-01.03B`, `KHAHP-01.03C` — **OPEN / NOT SIGNED OFF**.

#### 01.04 — Physical memory and swap capacity baseline

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of physical memory and swap capacity baseline; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Refresh actual hardware/OS scope before translating source-only observations into accepted controls.
- **Acceptance IDs:** `KHAHP-01.04A`, `KHAHP-01.04B`, `KHAHP-01.04C` — **OPEN / NOT SIGNED OFF**.

#### 01.05 — Storage controller, disk and filesystem topology

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of storage controller, disk and filesystem topology; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Refresh actual hardware/OS scope before translating source-only observations into accepted controls.
- **Acceptance IDs:** `KHAHP-01.05A`, `KHAHP-01.05B`, `KHAHP-01.05C` — **OPEN / NOT SIGNED OFF**.

#### 01.06 — UEFI/bare-metal/virtualization platform state

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of uefi/bare-metal/virtualization platform state; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Refresh actual hardware/OS scope before translating source-only observations into accepted controls.
- **Acceptance IDs:** `KHAHP-01.06A`, `KHAHP-01.06B`, `KHAHP-01.06C` — **OPEN / NOT SIGNED OFF**.

#### 01.07 — Failed-unit, uptime, boot-time and baseline health state

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of failed-unit, uptime, boot-time and baseline health state; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Refresh actual hardware/OS scope before translating source-only observations into accepted controls.
- **Acceptance IDs:** `KHAHP-01.07A`, `KHAHP-01.07B`, `KHAHP-01.07C` — **OPEN / NOT SIGNED OFF**.


### Section 02: Kicksecure Package Provenance

#### 02.01 — Core Kicksecure package installation and exact versions

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of core kicksecure package installation and exact versions; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Reconcile exact package ownership and versions; do not prescribe installing absent packages based on heuristic names.
- **Acceptance IDs:** `KHAHP-02.01A`, `KHAHP-02.01B`, `KHAHP-02.01C` — **OPEN / NOT SIGNED OFF**.

#### 02.02 — Supporting security-package installation and exact versions

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of supporting security-package installation and exact versions; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Reconcile exact package ownership and versions; do not prescribe installing absent packages based on heuristic names.
- **Acceptance IDs:** `KHAHP-02.02A`, `KHAHP-02.02B`, `KHAHP-02.02C` — **OPEN / NOT SIGNED OFF**.

#### 02.03 — APT source files and repository configuration

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of apt source files and repository configuration; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Reconcile exact package ownership and versions; do not prescribe installing absent packages based on heuristic names.
- **Acceptance IDs:** `KHAHP-02.03A`, `KHAHP-02.03B`, `KHAHP-02.03C` — **OPEN / NOT SIGNED OFF**.

#### 02.04 — APT policy and repository origin attribution

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of apt policy and repository origin attribution; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Reconcile exact package ownership and versions; do not prescribe installing absent packages based on heuristic names.
- **Acceptance IDs:** `KHAHP-02.04A`, `KHAHP-02.04B`, `KHAHP-02.04C` — **OPEN / NOT SIGNED OFF**.

#### 02.05 — Package ownership of security-critical configuration files

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of package ownership of security-critical configuration files; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Reconcile exact package ownership and versions; do not prescribe installing absent packages based on heuristic names.
- **Acceptance IDs:** `KHAHP-02.05A`, `KHAHP-02.05B`, `KHAHP-02.05C` — **OPEN / NOT SIGNED OFF**.

#### 02.06 — Package holds, partial installs and dpkg database health

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of package holds, partial installs and dpkg database health; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Reconcile exact package ownership and versions; do not prescribe installing absent packages based on heuristic names.
- **Acceptance IDs:** `KHAHP-02.06A`, `KHAHP-02.06B`, `KHAHP-02.06C` — **OPEN / NOT SIGNED OFF**.

#### 02.07 — Local modifications versus package-owned baseline

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of local modifications versus package-owned baseline; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Reconcile exact package ownership and versions; do not prescribe installing absent packages based on heuristic names.
- **Acceptance IDs:** `KHAHP-02.07A`, `KHAHP-02.07B`, `KHAHP-02.07C` — **OPEN / NOT SIGNED OFF**.


### Section 03: USER / SYSMAINT Privilege Architecture

#### 03.01 — USER, SYSMAINT and root account separation

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of user, sysmaint and root account separation; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Verify boot-role and upgrade regressions without weakening SYSMAINT boundaries.
- **Acceptance IDs:** `KHAHP-03.01A`, `KHAHP-03.01B`, `KHAHP-03.01C` — **OPEN / NOT SIGNED OFF**.

#### 03.02 — Distinct UID/GID and home-directory boundaries

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of distinct uid/gid and home-directory boundaries; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Verify boot-role and upgrade regressions without weakening SYSMAINT boundaries.
- **Acceptance IDs:** `KHAHP-03.02A`, `KHAHP-03.02B`, `KHAHP-03.02C` — **OPEN / NOT SIGNED OFF**.

#### 03.03 — user-sysmaint-split package and owned policy files

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of user-sysmaint-split package and owned policy files; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Verify boot-role and upgrade regressions without weakening SYSMAINT boundaries.
- **Acceptance IDs:** `KHAHP-03.03A`, `KHAHP-03.03B`, `KHAHP-03.03C` — **OPEN / NOT SIGNED OFF**.

#### 03.04 — sudo binary ownership, mode and SYSMAINT-only execution

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of sudo binary ownership, mode and sysmaint-only execution; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Verify boot-role and upgrade regressions without weakening SYSMAINT boundaries.
- **Acceptance IDs:** `KHAHP-03.04A`, `KHAHP-03.04B`, `KHAHP-03.04C` — **OPEN / NOT SIGNED OFF**.

#### 03.05 — sudoers syntax and user-sysmaint- split policy

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of sudoers syntax and user-sysmaint- split policy; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Verify boot-role and upgrade regressions without weakening SYSMAINT boundaries.
- **Acceptance IDs:** `KHAHP-03.05A`, `KHAHP-03.05B`, `KHAHP-03.05C` — **OPEN / NOT SIGNED OFF**.

#### 03.06 — USER negative sudo/root acquisition probe

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of user negative sudo/root acquisition probe; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Verify boot-role and upgrade regressions without weakening SYSMAINT boundaries.
- **Acceptance IDs:** `KHAHP-03.06A`, `KHAHP-03.06B`, `KHAHP-03.06C` — **OPEN / NOT SIGNED OFF**.

#### 03.07 — Login-shell and boot-role separation behavior

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of login-shell and boot-role separation behavior; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Verify boot-role and upgrade regressions without weakening SYSMAINT boundaries.
- **Acceptance IDs:** `KHAHP-03.07A`, `KHAHP-03.07B`, `KHAHP-03.07C` — **OPEN / NOT SIGNED OFF**.


### Section 04: SYSMAINT Boot Role

#### 04.01 — boot-role=sysmaint kernel marker

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of boot-role=sysmaint kernel marker; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Validate appropriate services in each boot role and persistence following updates.
- **Acceptance IDs:** `KHAHP-04.01A`, `KHAHP-04.01B`, `KHAHP-04.01C` — **OPEN / NOT SIGNED OFF**.

#### 04.02 — systemd.unit=sysmaint-boot.target marker

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of systemd.unit=sysmaint-boot.target marker; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Validate appropriate services in each boot role and persistence following updates.
- **Acceptance IDs:** `KHAHP-04.02A`, `KHAHP-04.02B`, `KHAHP-04.02C` — **OPEN / NOT SIGNED OFF**.

#### 04.03 — sysmaint-boot.target package provenance and unit content

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of sysmaint-boot.target package provenance and unit content; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Validate appropriate services in each boot role and persistence following updates.
- **Acceptance IDs:** `KHAHP-04.03A`, `KHAHP-04.03B`, `KHAHP-04.03C` — **OPEN / NOT SIGNED OFF**.

#### 04.04 — Required SYSMAINT dependencies and wanted units

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of required sysmaint dependencies and wanted units; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Validate appropriate services in each boot role and persistence following updates.
- **Acceptance IDs:** `KHAHP-04.04A`, `KHAHP-04.04B`, `KHAHP-04.04C` — **OPEN / NOT SIGNED OFF**.

#### 04.05 — Intentionally omitted USER-only or incompatible hardeners

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of intentionally omitted user-only or incompatible hardeners; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Validate appropriate services in each boot role and persistence following updates.
- **Acceptance IDs:** `KHAHP-04.05A`, `KHAHP-04.05B`, `KHAHP-04.05C` — **OPEN / NOT SIGNED OFF**.

#### 04.06 — Conflicting USER/graphical boot-role negative checks

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of conflicting user/graphical boot-role negative checks; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Validate appropriate services in each boot role and persistence following updates.
- **Acceptance IDs:** `KHAHP-04.06A`, `KHAHP-04.06B`, `KHAHP-04.06C` — **OPEN / NOT SIGNED OFF**.

#### 04.07 — Failed units and SYSMAINT boot health

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of failed units and sysmaint boot health; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Validate appropriate services in each boot role and persistence following updates.
- **Acceptance IDs:** `KHAHP-04.07A`, `KHAHP-04.07B`, `KHAHP-04.07C` — **OPEN / NOT SIGNED OFF**.


### Section 05: Accounts / UID / GID / Local Identity

#### 05.01 — root, USER and SYSMAINT account identity

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of root, user and sysmaint account identity; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Resolve role/service-account classification and verify policy compatibility.
- **Acceptance IDs:** `KHAHP-05.01A`, `KHAHP-05.01B`, `KHAHP-05.01C` — **OPEN / NOT SIGNED OFF**.

#### 05.02 — Duplicate UID and duplicate GID detection

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of duplicate uid and duplicate gid detection; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Resolve role/service-account classification and verify policy compatibility.
- **Acceptance IDs:** `KHAHP-05.02A`, `KHAHP-05.02B`, `KHAHP-05.02C` — **OPEN / NOT SIGNED OFF**.

#### 05.03 — UID 0 exclusivity and privileged- account review

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of uid 0 exclusivity and privileged- account review; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Resolve role/service-account classification and verify policy compatibility.
- **Acceptance IDs:** `KHAHP-05.03A`, `KHAHP-05.03B`, `KHAHP-05.03C` — **OPEN / NOT SIGNED OFF**.

#### 05.04 — Low-UID service-account shell classification

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of low-uid service-account shell classification; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Resolve role/service-account classification and verify policy compatibility.
- **Acceptance IDs:** `KHAHP-05.04A`, `KHAHP-05.04B`, `KHAHP-05.04C` — **OPEN / NOT SIGNED OFF**.

#### 05.05 — Home-directory ownership and permissions

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of home-directory ownership and permissions; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Resolve role/service-account classification and verify policy compatibility.
- **Acceptance IDs:** `KHAHP-05.05A`, `KHAHP-05.05B`, `KHAHP-05.05C` — **OPEN / NOT SIGNED OFF**.

#### 05.06 — shadow/gshadow/passwd/group ownership and modes

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of shadow/gshadow/passwd/group ownership and modes; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Resolve role/service-account classification and verify policy compatibility.
- **Acceptance IDs:** `KHAHP-05.06A`, `KHAHP-05.06B`, `KHAHP-05.06C` — **OPEN / NOT SIGNED OFF**.

#### 05.07 — NSS identity source configuration and root lock state

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of nss identity source configuration and root lock state; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Resolve role/service-account classification and verify policy compatibility.
- **Acceptance IDs:** `KHAHP-05.07A`, `KHAHP-05.07B`, `KHAHP-05.07C` — **OPEN / NOT SIGNED OFF**.


### Section 06: LUKS / Disk / Swap Encryption

#### 06.01 — Root filesystem source and dm-crypt mapping

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of root filesystem source and dm-crypt mapping; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Validate key-recovery and restore evidence privately; do not publish secrets.
- **Acceptance IDs:** `KHAHP-06.01A`, `KHAHP-06.01B`, `KHAHP-06.01C` — **OPEN / NOT SIGNED OFF**.

#### 06.02 — LUKS2 backing partition and cryptsetup status

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of luks2 backing partition and cryptsetup status; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Validate key-recovery and restore evidence privately; do not publish secrets.
- **Acceptance IDs:** `KHAHP-06.02A`, `KHAHP-06.02B`, `KHAHP-06.02C` — **OPEN / NOT SIGNED OFF**.

#### 06.03 — LUKS header metadata without key- material disclosure

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of luks header metadata without key- material disclosure; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Validate key-recovery and restore evidence privately; do not publish secrets.
- **Acceptance IDs:** `KHAHP-06.03A`, `KHAHP-06.03B`, `KHAHP-06.03C` — **OPEN / NOT SIGNED OFF**.

#### 06.04 — Root encryption chain from block device to mountpoint

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of root encryption chain from block device to mountpoint; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Validate key-recovery and restore evidence privately; do not publish secrets.
- **Acceptance IDs:** `KHAHP-06.04A`, `KHAHP-06.04B`, `KHAHP-06.04C` — **OPEN / NOT SIGNED OFF**.

#### 06.05 — Active swap inventory and encrypted placement

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of active swap inventory and encrypted placement; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Validate key-recovery and restore evidence privately; do not publish secrets.
- **Acceptance IDs:** `KHAHP-06.05A`, `KHAHP-06.05B`, `KHAHP-06.05C` — **OPEN / NOT SIGNED OFF**.

#### 06.06 — swapfile ownership, mode and containing filesystem

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of swapfile ownership, mode and containing filesystem; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Validate key-recovery and restore evidence privately; do not publish secrets.
- **Acceptance IDs:** `KHAHP-06.06A`, `KHAHP-06.06B`, `KHAHP-06.06C` — **OPEN / NOT SIGNED OFF**.

#### 06.07 — crypttab/fstab encryption persistence and boot mapping

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of crypttab/fstab encryption persistence and boot mapping; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Validate key-recovery and restore evidence privately; do not publish secrets.
- **Acceptance IDs:** `KHAHP-06.07A`, `KHAHP-06.07B`, `KHAHP-06.07C` — **OPEN / NOT SIGNED OFF**.


### Section 07: Filesystem / Mount Security

#### 07.01 — Effective mount table and filesystem inventory

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of effective mount table and filesystem inventory; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Resolve separate boot-mount ordering and compatibility exceptions; SYSMAINT corroboration remains.
- **Acceptance IDs:** `KHAHP-07.01A`, `KHAHP-07.01B`, `KHAHP-07.01C` — **OPEN / NOT SIGNED OFF**.

#### 07.02 — Root mount source, filesystem and options

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of root mount source, filesystem and options; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Resolve separate boot-mount ordering and compatibility exceptions; SYSMAINT corroboration remains.
- **Acceptance IDs:** `KHAHP-07.02A`, `KHAHP-07.02B`, `KHAHP-07.02C` — **OPEN / NOT SIGNED OFF**.

#### 07.03 — /boot and /boot/efi separation, ownership and exposure

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of /boot and /boot/efi separation, ownership and exposure; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Resolve separate boot-mount ordering and compatibility exceptions; SYSMAINT corroboration remains.
- **Acceptance IDs:** `KHAHP-07.03A`, `KHAHP-07.03B`, `KHAHP-07.03C` — **OPEN / NOT SIGNED OFF**.

#### 07.04 — /tmp tmpfs, sticky bit and mount- option review

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of /tmp tmpfs, sticky bit and mount- option review; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Resolve separate boot-mount ordering and compatibility exceptions; SYSMAINT corroboration remains.
- **Acceptance IDs:** `KHAHP-07.04A`, `KHAHP-07.04B`, `KHAHP-07.04C` — **OPEN / NOT SIGNED OFF**.

#### 07.05 — /var/tmp sticky-bit and separate- mount review

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of /var/tmp sticky-bit and separate- mount review; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Resolve separate boot-mount ordering and compatibility exceptions; SYSMAINT corroboration remains.
- **Acceptance IDs:** `KHAHP-07.05A`, `KHAHP-07.05B`, `KHAHP-07.05C` — **OPEN / NOT SIGNED OFF**.

#### 07.06 — /home containment, ownership and inherited options

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of /home containment, ownership and inherited options; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Resolve separate boot-mount ordering and compatibility exceptions; SYSMAINT corroboration remains.
- **Acceptance IDs:** `KHAHP-07.06A`, `KHAHP-07.06B`, `KHAHP-07.06C` — **OPEN / NOT SIGNED OFF**.

#### 07.07 — Writable mountpoints, fstab and remount-secure review

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of writable mountpoints, fstab and remount-secure review; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Resolve separate boot-mount ordering and compatibility exceptions; SYSMAINT corroboration remains.
- **Acceptance IDs:** `KHAHP-07.07A`, `KHAHP-07.07B`, `KHAHP-07.07C` — **OPEN / NOT SIGNED OFF**.


### Section 08: GRUB / Bootloader Protection

#### 08.01 — GRUB package baseline and generated grub.cfg

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of grub package baseline and generated grub.cfg; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Physical boot-edit negative test and tested recovery remain pending.
- **Acceptance IDs:** `KHAHP-08.01A`, `KHAHP-08.01B`, `KHAHP-08.01C` — **OPEN / NOT SIGNED OFF**.

#### 08.02 — grub.cfg ownership, permissions and menu entries

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of grub.cfg ownership, permissions and menu entries; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Physical boot-edit negative test and tested recovery remain pending.
- **Acceptance IDs:** `KHAHP-08.02A`, `KHAHP-08.02B`, `KHAHP-08.02C` — **OPEN / NOT SIGNED OFF**.

#### 08.03 — GRUB password_pbkdf2 and superusers directives

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of grub password_pbkdf2 and superusers directives; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Physical boot-edit negative test and tested recovery remain pending.
- **Acceptance IDs:** `KHAHP-08.03A`, `KHAHP-08.03B`, `KHAHP-08.03C` — **OPEN / NOT SIGNED OFF**.

#### 08.04 — Kicksecure CPU/kernel/ram-wipe/remount/signed -module fragments

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of kicksecure cpu/kernel/ram-wipe/remount/signed -module fragments; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Physical boot-edit negative test and tested recovery remain pending.
- **Acceptance IDs:** `KHAHP-08.04A`, `KHAHP-08.04B`, `KHAHP-08.04C` — **OPEN / NOT SIGNED OFF**.

#### 08.05 — Quiet-boot and recovery-restriction fragments

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of quiet-boot and recovery-restriction fragments; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Physical boot-edit negative test and tested recovery remain pending.
- **Acceptance IDs:** `KHAHP-08.05A`, `KHAHP-08.05B`, `KHAHP-08.05C` — **OPEN / NOT SIGNED OFF**.

#### 08.06 — Effective boot command-line correlation

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of effective boot command-line correlation; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Physical boot-edit negative test and tested recovery remain pending.
- **Acceptance IDs:** `KHAHP-08.06A`, `KHAHP-08.06B`, `KHAHP-08.06C` — **OPEN / NOT SIGNED OFF**.

#### 08.07 — /boot and EFI exposure versus cryptographic integrity limits

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of /boot and efi exposure versus cryptographic integrity limits; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Physical boot-edit negative test and tested recovery remain pending.
- **Acceptance IDs:** `KHAHP-08.07A`, `KHAHP-08.07B`, `KHAHP-08.07C` — **OPEN / NOT SIGNED OFF**.


### Section 09: CPU Vulnerability Mitigations

#### 09.01 — CPU identity, vendor and mitigation- capability baseline

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of cpu identity, vendor and mitigation- capability baseline; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm effective kernel features before making CFI/KCFI claims.
- **Acceptance IDs:** `KHAHP-09.01A`, `KHAHP-09.01B`, `KHAHP-09.01C` — **OPEN / NOT SIGNED OFF**.

#### 09.02 — SMT/Hyper-Threading disablement and topology

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of smt/hyper-threading disablement and topology; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm effective kernel features before making CFI/KCFI claims.
- **Acceptance IDs:** `KHAHP-09.02A`, `KHAHP-09.02B`, `KHAHP-09.02C` — **OPEN / NOT SIGNED OFF**.

#### 09.03 — Runtime microcode revision and package baseline

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of runtime microcode revision and package baseline; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm effective kernel features before making CFI/KCFI claims.
- **Acceptance IDs:** `KHAHP-09.03A`, `KHAHP-09.03B`, `KHAHP-09.03C` — **OPEN / NOT SIGNED OFF**.

#### 09.04 — Kernel vulnerability-interface enumeration

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of kernel vulnerability-interface enumeration; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm effective kernel features before making CFI/KCFI claims.
- **Acceptance IDs:** `KHAHP-09.04A`, `KHAHP-09.04B`, `KHAHP-09.04C` — **OPEN / NOT SIGNED OFF**.

#### 09.05 — Spectre/Meltdown/L1TF/MDS/ Retbleed/BHI/SSB/TAA/GDS mitigations

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of spectre/meltdown/l1tf/mds/ retbleed/bhi/ssb/taa/gds mitigations; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm effective kernel features before making CFI/KCFI claims.
- **Acceptance IDs:** `KHAHP-09.05A`, `KHAHP-09.05B`, `KHAHP-09.05C` — **OPEN / NOT SIGNED OFF**.

#### 09.06 — Mitigation-related kernel command- line parameters

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of mitigation-related kernel command- line parameters; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm effective kernel features before making CFI/KCFI claims.
- **Acceptance IDs:** `KHAHP-09.06A`, `KHAHP-09.06B`, `KHAHP-09.06C` — **OPEN / NOT SIGNED OFF**.

#### 09.07 — CPU mitigation flags and kernel-log confirmation

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of cpu mitigation flags and kernel-log confirmation; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm effective kernel features before making CFI/KCFI claims.
- **Acceptance IDs:** `KHAHP-09.07A`, `KHAHP-09.07B`, `KHAHP-09.07C` — **OPEN / NOT SIGNED OFF**.


### Section 10: IOMMU / DMA Protection

#### 10.01 — CPU virtualization/VT-d capability baseline

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of cpu virtualization/vt-d capability baseline; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm preboot DMA and firmware applicability with safe manual tests.
- **Acceptance IDs:** `KHAHP-10.01A`, `KHAHP-10.01B`, `KHAHP-10.01C` — **OPEN / NOT SIGNED OFF**.

#### 10.02 — IOMMU kernel parameters and passthrough policy

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of iommu kernel parameters and passthrough policy; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm preboot DMA and firmware applicability with safe manual tests.
- **Acceptance IDs:** `KHAHP-10.02A`, `KHAHP-10.02B`, `KHAHP-10.02C` — **OPEN / NOT SIGNED OFF**.

#### 10.03 — DMAR/IOMMU runtime enablement

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of dmar/iommu runtime enablement; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm preboot DMA and firmware applicability with safe manual tests.
- **Acceptance IDs:** `KHAHP-10.03A`, `KHAHP-10.03B`, `KHAHP-10.03C` — **OPEN / NOT SIGNED OFF**.

#### 10.04 — Translated default domain and strict invalidation

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of translated default domain and strict invalidation; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm preboot DMA and firmware applicability with safe manual tests.
- **Acceptance IDs:** `KHAHP-10.04A`, `KHAHP-10.04B`, `KHAHP-10.04C` — **OPEN / NOT SIGNED OFF**.

#### 10.05 — IRQ/interrupt remapping

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of irq/interrupt remapping; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm preboot DMA and firmware applicability with safe manual tests.
- **Acceptance IDs:** `KHAHP-10.05A`, `KHAHP-10.05B`, `KHAHP-10.05C` — **OPEN / NOT SIGNED OFF**.

#### 10.06 — IOMMU group topology and full PCI membership

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of iommu group topology and full pci membership; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm preboot DMA and firmware applicability with safe manual tests.
- **Acceptance IDs:** `KHAHP-10.06A`, `KHAHP-10.06B`, `KHAHP-10.06C` — **OPEN / NOT SIGNED OFF**.

#### 10.07 — Early PCI DMA restriction and firmware WSMT evidence

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of early pci dma restriction and firmware wsmt evidence; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm preboot DMA and firmware applicability with safe manual tests.
- **Acceptance IDs:** `KHAHP-10.07A`, `KHAHP-10.07B`, `KHAHP-10.07C` — **OPEN / NOT SIGNED OFF**.


### Section 11: Kernel Sysctl Hardening

#### 11.01 — Sysctl source-tree inventory and precedence

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of sysctl source-tree inventory and precedence; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Map package-owned precedence and persist expected values after upgrades.
- **Acceptance IDs:** `KHAHP-11.01A`, `KHAHP-11.01B`, `KHAHP-11.01C` — **OPEN / NOT SIGNED OFF**.

#### 11.02 — Kicksecure security-misc sysctl source files

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of kicksecure security-misc sysctl source files; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Map package-owned precedence and persist expected values after upgrades.
- **Acceptance IDs:** `KHAHP-11.02A`, `KHAHP-11.02B`, `KHAHP-11.02C` — **OPEN / NOT SIGNED OFF**.

#### 11.03 — Kernel information-leak restrictions

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of kernel information-leak restrictions; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Map package-owned precedence and persist expected values after upgrades.
- **Acceptance IDs:** `KHAHP-11.03A`, `KHAHP-11.03B`, `KHAHP-11.03C` — **OPEN / NOT SIGNED OFF**.

#### 11.04 — ASLR, mmap, kexec and privileged- coredump controls

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of aslr, mmap, kexec and privileged- coredump controls; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Map package-owned precedence and persist expected values after upgrades.
- **Acceptance IDs:** `KHAHP-11.04A`, `KHAHP-11.04B`, `KHAHP-11.04C` — **OPEN / NOT SIGNED OFF**.

#### 11.05 — BPF, ptrace, perf and TTY line- discipline restrictions

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of bpf, ptrace, perf and tty line- discipline restrictions; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Map package-owned precedence and persist expected values after upgrades.
- **Acceptance IDs:** `KHAHP-11.05A`, `KHAHP-11.05B`, `KHAHP-11.05C` — **OPEN / NOT SIGNED OFF**.

#### 11.06 — Protected links/FIFOs/regular-file controls

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of protected links/fifos/regular-file controls; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Map package-owned precedence and persist expected values after upgrades.
- **Acceptance IDs:** `KHAHP-11.06A`, `KHAHP-11.06B`, `KHAHP-11.06C` — **OPEN / NOT SIGNED OFF**.

#### 11.07 — Network-stack sysctl hardening observations

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of network-stack sysctl hardening observations; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Map package-owned precedence and persist expected values after upgrades.
- **Acceptance IDs:** `KHAHP-11.07A`, `KHAHP-11.07B`, `KHAHP-11.07C` — **OPEN / NOT SIGNED OFF**.


### Section 12: Kernel Boot / Memory Hardening

#### 12.01 — Slab allocator hardening and slab_nomerge

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of slab allocator hardening and slab_nomerge; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Separate effective kernel capability from mere presence of boot tokens.
- **Acceptance IDs:** `KHAHP-12.01A`, `KHAHP-12.01B`, `KHAHP-12.01C` — **OPEN / NOT SIGNED OFF**.

#### 12.02 — init_on_alloc and init_on_free memory initialization

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of init_on_alloc and init_on_free memory initialization; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Separate effective kernel capability from mere presence of boot tokens.
- **Acceptance IDs:** `KHAHP-12.02A`, `KHAHP-12.02B`, `KHAHP-12.02C` — **OPEN / NOT SIGNED OFF**.

#### 12.03 — page allocator shuffle and stack randomization

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of page allocator shuffle and stack randomization; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Separate effective kernel capability from mere presence of boot tokens.
- **Acceptance IDs:** `KHAHP-12.03A`, `KHAHP-12.03B`, `KHAHP-12.03C` — **OPEN / NOT SIGNED OFF**.

#### 12.04 — vsyscall, vdso32 and 32-bit compatibility restrictions

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of vsyscall, vdso32 and 32-bit compatibility restrictions; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Separate effective kernel capability from mere presence of boot tokens.
- **Acceptance IDs:** `KHAHP-12.04A`, `KHAHP-12.04B`, `KHAHP-12.04C` — **OPEN / NOT SIGNED OFF**.

#### 12.05 — debugfs, KFENCE and kernel debug- surface controls

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of debugfs, kfence and kernel debug- surface controls; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Separate effective kernel capability from mere presence of boot tokens.
- **Acceptance IDs:** `KHAHP-12.05A`, `KHAHP-12.05B`, `KHAHP-12.05C` — **OPEN / NOT SIGNED OFF**.

#### 12.06 — CFI/KCFI and boot-time control acceptance

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of cfi/kcfi and boot-time control acceptance; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Separate effective kernel capability from mere presence of boot tokens.
- **Acceptance IDs:** `KHAHP-12.06A`, `KHAHP-12.06B`, `KHAHP-12.06C` — **OPEN / NOT SIGNED OFF**.

#### 12.07 — pstore/ERST/proc_mem/entropy trust boot parameters

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of pstore/erst/proc_mem/entropy trust boot parameters; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Separate effective kernel capability from mere presence of boot tokens.
- **Acceptance IDs:** `KHAHP-12.07A`, `KHAHP-12.07B`, `KHAHP-12.07C` — **OPEN / NOT SIGNED OFF**.


### Section 13: Kernel Module Restrictions

#### 13.01 — security-misc module blacklist configuration

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of security-misc module blacklist configuration; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Resolve built-in versus loadable module behavior and compatibility.
- **Acceptance IDs:** `KHAHP-13.01A`, `KHAHP-13.01B`, `KHAHP-13.01C` — **OPEN / NOT SIGNED OFF**.

#### 13.02 — Hard-disable install rules for risky modules

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of hard-disable install rules for risky modules; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Resolve built-in versus loadable module behavior and compatibility.
- **Acceptance IDs:** `KHAHP-13.02A`, `KHAHP-13.02B`, `KHAHP-13.02C` — **OPEN / NOT SIGNED OFF**.

#### 13.03 — Loaded-module inventory versus policy

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of loaded-module inventory versus policy; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Resolve built-in versus loadable module behavior and compatibility.
- **Acceptance IDs:** `KHAHP-13.03A`, `KHAHP-13.03B`, `KHAHP-13.03C` — **OPEN / NOT SIGNED OFF**.

#### 13.04 — Legacy filesystem module restrictions

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of legacy filesystem module restrictions; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Resolve built-in versus loadable module behavior and compatibility.
- **Acceptance IDs:** `KHAHP-13.04A`, `KHAHP-13.04B`, `KHAHP-13.04C` — **OPEN / NOT SIGNED OFF**.

#### 13.05 — Legacy network/protocol module restrictions

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of legacy network/protocol module restrictions; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Resolve built-in versus loadable module behavior and compatibility.
- **Acceptance IDs:** `KHAHP-13.05A`, `KHAHP-13.05B`, `KHAHP-13.05C` — **OPEN / NOT SIGNED OFF**.

#### 13.06 — USB/storage/media module restriction exceptions

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of usb/storage/media module restriction exceptions; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Resolve built-in versus loadable module behavior and compatibility.
- **Acceptance IDs:** `KHAHP-13.06A`, `KHAHP-13.06B`, `KHAHP-13.06C` — **OPEN / NOT SIGNED OFF**.

#### 13.07 — Module-load negative tests and compatibility exceptions

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of module-load negative tests and compatibility exceptions; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Resolve built-in versus loadable module behavior and compatibility.
- **Acceptance IDs:** `KHAHP-13.07A`, `KHAHP-13.07B`, `KHAHP-13.07C` — **OPEN / NOT SIGNED OFF**.


### Section 14: Kernel Module Signing / DKMS

#### 14.01 — Loaded-module signer inventory

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of loaded-module signer inventory; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Validate signer chain and upgrade behavior without re-enrolling keys unnecessarily.
- **Acceptance IDs:** `KHAHP-14.01A`, `KHAHP-14.01B`, `KHAHP-14.01C` — **OPEN / NOT SIGNED OFF**.

#### 14.02 — DKMS package and built-module inventory

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of dkms package and built-module inventory; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Validate signer chain and upgrade behavior without re-enrolling keys unnecessarily.
- **Acceptance IDs:** `KHAHP-14.02A`, `KHAHP-14.02B`, `KHAHP-14.02C` — **OPEN / NOT SIGNED OFF**.

#### 14.03 — tirdad DKMS build, signer and runtime state

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of tirdad dkms build, signer and runtime state; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Validate signer chain and upgrade behavior without re-enrolling keys unnecessarily.
- **Acceptance IDs:** `KHAHP-14.03A`, `KHAHP-14.03B`, `KHAHP-14.03C` — **OPEN / NOT SIGNED OFF**.

#### 14.04 — NVIDIA/other third-party module signer state

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of nvidia/other third-party module signer state; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Validate signer chain and upgrade behavior without re-enrolling keys unnecessarily.
- **Acceptance IDs:** `KHAHP-14.04A`, `KHAHP-14.04B`, `KHAHP-14.04C` — **OPEN / NOT SIGNED OFF**.

#### 14.05 — Kernel module signature enforcement capability

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of kernel module signature enforcement capability; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Validate signer chain and upgrade behavior without re-enrolling keys unnecessarily.
- **Acceptance IDs:** `KHAHP-14.05A`, `KHAHP-14.05B`, `KHAHP-14.05C` — **OPEN / NOT SIGNED OFF**.

#### 14.06 — MOK/enrolled certificate readiness

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of mok/enrolled certificate readiness; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Validate signer chain and upgrade behavior without re-enrolling keys unnecessarily.
- **Acceptance IDs:** `KHAHP-14.06A`, `KHAHP-14.06B`, `KHAHP-14.06C` — **OPEN / NOT SIGNED OFF**.

#### 14.07 — Secure-Boot compatibility and unsigned-module exceptions

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of secure-boot compatibility and unsigned-module exceptions; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Validate signer chain and upgrade behavior without re-enrolling keys unnecessarily.
- **Acceptance IDs:** `KHAHP-14.07A`, `KHAHP-14.07B`, `KHAHP-14.07C` — **OPEN / NOT SIGNED OFF**.


### Section 15: AppArmor / Mandatory Access Control

#### 15.01 — AppArmor kernel/module enablement

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-002`.
- **Required A/B/C evidence:** Provenance of apparmor kernel/module enablement; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Plan compatible browser confinement in a test environment before any package-profile changes.
- **Acceptance IDs:** `KHAHP-15.01A`, `KHAHP-15.01B`, `KHAHP-15.01C` — **OPEN / NOT SIGNED OFF**.

#### 15.02 — Profile inventory and parser status

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-002`.
- **Required A/B/C evidence:** Provenance of profile inventory and parser status; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Plan compatible browser confinement in a test environment before any package-profile changes.
- **Acceptance IDs:** `KHAHP-15.02A`, `KHAHP-15.02B`, `KHAHP-15.02C` — **OPEN / NOT SIGNED OFF**.

#### 15.03 — Enforce/complain/unconfined process counts

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-001`, `I15-003`.
- **Required A/B/C evidence:** Provenance of enforce/complain/unconfined process counts; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Plan compatible browser confinement in a test environment before any package-profile changes.
- **Acceptance IDs:** `KHAHP-15.03A`, `KHAHP-15.03B`, `KHAHP-15.03C` — **OPEN / NOT SIGNED OFF**.

#### 15.04 — Tor and network-service profile enforcement

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-002`.
- **Required A/B/C evidence:** Provenance of tor and network-service profile enforcement; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Plan compatible browser confinement in a test environment before any package-profile changes.
- **Acceptance IDs:** `KHAHP-15.04A`, `KHAHP-15.04B`, `KHAHP-15.04C` — **OPEN / NOT SIGNED OFF**.

#### 15.05 — Browser/application profile coverage

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-001`.
- **Required A/B/C evidence:** Provenance of browser/application profile coverage; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Plan compatible browser confinement in a test environment before any package-profile changes.
- **Acceptance IDs:** `KHAHP-15.05A`, `KHAHP-15.05B`, `KHAHP-15.05C` — **OPEN / NOT SIGNED OFF**.

#### 15.06 — Denied-event review and false-positive handling

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-002`.
- **Required A/B/C evidence:** Provenance of denied-event review and false-positive handling; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Plan compatible browser confinement in a test environment before any package-profile changes.
- **Acceptance IDs:** `KHAHP-15.06A`, `KHAHP-15.06B`, `KHAHP-15.06C` — **OPEN / NOT SIGNED OFF**.

#### 15.07 — USER versus SYSMAINT AppArmor behavior

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-001`, `I15-003`.
- **Required A/B/C evidence:** Provenance of user versus sysmaint apparmor behavior; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Plan compatible browser confinement in a test environment before any package-profile changes.
- **Acceptance IDs:** `KHAHP-15.07A`, `KHAHP-15.07B`, `KHAHP-15.07C` — **OPEN / NOT SIGNED OFF**.


### Section 16: SUID / SGID / File Capabilities

#### 16.01 — Complete SUID file inventory

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-004`.
- **Required A/B/C evidence:** Provenance of complete suid file inventory; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Review drift and package capabilities without blind permission changes.
- **Acceptance IDs:** `KHAHP-16.01A`, `KHAHP-16.01B`, `KHAHP-16.01C` — **OPEN / NOT SIGNED OFF**.

#### 16.02 — Complete SGID file inventory

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-004`.
- **Required A/B/C evidence:** Provenance of complete sgid file inventory; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Review drift and package capabilities without blind permission changes.
- **Acceptance IDs:** `KHAHP-16.02A`, `KHAHP-16.02B`, `KHAHP-16.02C` — **OPEN / NOT SIGNED OFF**.

#### 16.03 — Package ownership of privileged binaries

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-004`.
- **Required A/B/C evidence:** Provenance of package ownership of privileged binaries; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Review drift and package capabilities without blind permission changes.
- **Acceptance IDs:** `KHAHP-16.03A`, `KHAHP-16.03B`, `KHAHP-16.03C` — **OPEN / NOT SIGNED OFF**.

#### 16.04 — permission-hardener expected mode validation

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of permission-hardener expected mode validation; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Review drift and package capabilities without blind permission changes.
- **Acceptance IDs:** `KHAHP-16.04A`, `KHAHP-16.04B`, `KHAHP-16.04C` — **OPEN / NOT SIGNED OFF**.

#### 16.05 — File-capability inventory and package attribution

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-005`.
- **Required A/B/C evidence:** Provenance of file-capability inventory and package attribution; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Review drift and package capabilities without blind permission changes.
- **Acceptance IDs:** `KHAHP-16.05A`, `KHAHP-16.05B`, `KHAHP-16.05C` — **OPEN / NOT SIGNED OFF**.

#### 16.06 — Unexpected privileged executable detection

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-004`.
- **Required A/B/C evidence:** Provenance of unexpected privileged executable detection; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Review drift and package capabilities without blind permission changes.
- **Acceptance IDs:** `KHAHP-16.06A`, `KHAHP-16.06B`, `KHAHP-16.06C` — **OPEN / NOT SIGNED OFF**.

#### 16.07 — Privilege-binary negative/compatibility review

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-005`.
- **Required A/B/C evidence:** Provenance of privilege-binary negative/compatibility review; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Review drift and package capabilities without blind permission changes.
- **Acceptance IDs:** `KHAHP-16.07A`, `KHAHP-16.07B`, `KHAHP-16.07C` — **OPEN / NOT SIGNED OFF**.


### Section 17: Permissions / ACL / Umask

#### 17.01 — System file ownership baseline

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-006`.
- **Required A/B/C evidence:** Provenance of system file ownership baseline; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Classify intended vendor exception and monitor unexpected permission drift.
- **Acceptance IDs:** `KHAHP-17.01A`, `KHAHP-17.01B`, `KHAHP-17.01C` — **OPEN / NOT SIGNED OFF**.

#### 17.02 — World-writable system path inventory

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-006`.
- **Required A/B/C evidence:** Provenance of world-writable system path inventory; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Classify intended vendor exception and monitor unexpected permission drift.
- **Acceptance IDs:** `KHAHP-17.02A`, `KHAHP-17.02B`, `KHAHP-17.02C` — **OPEN / NOT SIGNED OFF**.

#### 17.03 — Unexpected group-writable sensitive paths

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-007`.
- **Required A/B/C evidence:** Provenance of unexpected group-writable sensitive paths; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Classify intended vendor exception and monitor unexpected permission drift.
- **Acceptance IDs:** `KHAHP-17.03A`, `KHAHP-17.03B`, `KHAHP-17.03C` — **OPEN / NOT SIGNED OFF**.

#### 17.04 — ACL inventory on sensitive configuration

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-007`.
- **Required A/B/C evidence:** Provenance of acl inventory on sensitive configuration; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Classify intended vendor exception and monitor unexpected permission drift.
- **Acceptance IDs:** `KHAHP-17.04A`, `KHAHP-17.04B`, `KHAHP-17.04C` — **OPEN / NOT SIGNED OFF**.

#### 17.05 — Root and user umask policy

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-007`.
- **Required A/B/C evidence:** Provenance of root and user umask policy; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Classify intended vendor exception and monitor unexpected permission drift.
- **Acceptance IDs:** `KHAHP-17.05A`, `KHAHP-17.05B`, `KHAHP-17.05C` — **OPEN / NOT SIGNED OFF**.

#### 17.06 — Home and evidence-directory permissions

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-007`.
- **Required A/B/C evidence:** Provenance of home and evidence-directory permissions; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Classify intended vendor exception and monitor unexpected permission drift.
- **Acceptance IDs:** `KHAHP-17.06A`, `KHAHP-17.06B`, `KHAHP-17.06C` — **OPEN / NOT SIGNED OFF**.

#### 17.07 — Sticky-bit and shared-directory permission policy

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-006`, `I15-007`.
- **Required A/B/C evidence:** Provenance of sticky-bit and shared-directory permission policy; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Classify intended vendor exception and monitor unexpected permission drift.
- **Acceptance IDs:** `KHAHP-17.07A`, `KHAHP-17.07B`, `KHAHP-17.07C` — **OPEN / NOT SIGNED OFF**.


### Section 18: PAM / Login / Faillock

#### 18.01 — PAM stack package provenance

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-010`.
- **Required A/B/C evidence:** Provenance of pam stack package provenance; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Prove safe recovery from lockout and decide local passphrase/aging requirements.
- **Acceptance IDs:** `KHAHP-18.01A`, `KHAHP-18.01B`, `KHAHP-18.01C` — **OPEN / NOT SIGNED OFF**.

#### 18.02 — password quality and hashing policy

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-009`.
- **Required A/B/C evidence:** Provenance of password quality and hashing policy; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Prove safe recovery from lockout and decide local passphrase/aging requirements.
- **Acceptance IDs:** `KHAHP-18.02A`, `KHAHP-18.02B`, `KHAHP-18.02C` — **OPEN / NOT SIGNED OFF**.

#### 18.03 — faillock/brute-force lockout policy

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-008`.
- **Required A/B/C evidence:** Provenance of faillock/brute-force lockout policy; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Prove safe recovery from lockout and decide local passphrase/aging requirements.
- **Acceptance IDs:** `KHAHP-18.03A`, `KHAHP-18.03B`, `KHAHP-18.03C` — **OPEN / NOT SIGNED OFF**.

#### 18.04 — login delay and retry controls

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-008`.
- **Required A/B/C evidence:** Provenance of login delay and retry controls; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Prove safe recovery from lockout and decide local passphrase/aging requirements.
- **Acceptance IDs:** `KHAHP-18.04A`, `KHAHP-18.04B`, `KHAHP-18.04C` — **OPEN / NOT SIGNED OFF**.

#### 18.05 — su/sudo/polkit PAM interaction

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-010`.
- **Required A/B/C evidence:** Provenance of su/sudo/polkit pam interaction; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Prove safe recovery from lockout and decide local passphrase/aging requirements.
- **Acceptance IDs:** `KHAHP-18.05A`, `KHAHP-18.05B`, `KHAHP-18.05C` — **OPEN / NOT SIGNED OFF**.

#### 18.06 — account aging and inactive-account policy

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-009`.
- **Required A/B/C evidence:** Provenance of account aging and inactive-account policy; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Prove safe recovery from lockout and decide local passphrase/aging requirements.
- **Acceptance IDs:** `KHAHP-18.06A`, `KHAHP-18.06B`, `KHAHP-18.06C` — **OPEN / NOT SIGNED OFF**.

#### 18.07 — USER/SYSMAINT login regression tests

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-008`, `I15-010`.
- **Required A/B/C evidence:** Provenance of user/sysmaint login regression tests; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Prove safe recovery from lockout and decide local passphrase/aging requirements.
- **Acceptance IDs:** `KHAHP-18.07A`, `KHAHP-18.07B`, `KHAHP-18.07C` — **OPEN / NOT SIGNED OFF**.


### Section 19: SSH Client / Server Security

#### 19.01 — Local SSH server service/socket state

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-011`.
- **Required A/B/C evidence:** Provenance of local ssh server service/socket state; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Preserve local exception and validate state after upgrades and recovery.
- **Acceptance IDs:** `KHAHP-19.01A`, `KHAHP-19.01B`, `KHAHP-19.01C` — **OPEN / NOT SIGNED OFF**.

#### 19.02 — sshd listener and inbound port absence

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-011`.
- **Required A/B/C evidence:** Provenance of sshd listener and inbound port absence; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Preserve local exception and validate state after upgrades and recovery.
- **Acceptance IDs:** `KHAHP-19.02A`, `KHAHP-19.02B`, `KHAHP-19.02C` — **OPEN / NOT SIGNED OFF**.

#### 19.03 — sshd_config security-misc policy if installed

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-011`.
- **Required A/B/C evidence:** Provenance of sshd_config security-misc policy if installed; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Preserve local exception and validate state after upgrades and recovery.
- **Acceptance IDs:** `KHAHP-19.03A`, `KHAHP-19.03B`, `KHAHP-19.03C` — **OPEN / NOT SIGNED OFF**.

#### 19.04 — SSH client configuration and host-key verification

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-012`.
- **Required A/B/C evidence:** Provenance of ssh client configuration and host-key verification; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Preserve local exception and validate state after upgrades and recovery.
- **Acceptance IDs:** `KHAHP-19.04A`, `KHAHP-19.04B`, `KHAHP-19.04C` — **OPEN / NOT SIGNED OFF**.

#### 19.05 — Private-key ownership and permission baseline

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-012`.
- **Required A/B/C evidence:** Provenance of private-key ownership and permission baseline; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Preserve local exception and validate state after upgrades and recovery.
- **Acceptance IDs:** `KHAHP-19.05A`, `KHAHP-19.05B`, `KHAHP-19.05C` — **OPEN / NOT SIGNED OFF**.

#### 19.06 — Password-authentication and root-login policy for future server use

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-011`.
- **Required A/B/C evidence:** Provenance of password-authentication and root-login policy for future server use; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Preserve local exception and validate state after upgrades and recovery.
- **Acceptance IDs:** `KHAHP-19.06A`, `KHAHP-19.06B`, `KHAHP-19.06C` — **OPEN / NOT SIGNED OFF**.

#### 19.07 — Known-hosts/key algorithm and crypto-policy review

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-012`.
- **Required A/B/C evidence:** Provenance of known-hosts/key algorithm and crypto-policy review; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Preserve local exception and validate state after upgrades and recovery.
- **Acceptance IDs:** `KHAHP-19.07A`, `KHAHP-19.07B`, `KHAHP-19.07C` — **OPEN / NOT SIGNED OFF**.


### Section 20: Enabled / Running Service Audit

#### 20.01 — Enabled systemd service inventory

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-013`.
- **Required A/B/C evidence:** Provenance of enabled systemd service inventory; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Classify dependencies and verify expected-role persistence; do not disable blindly.
- **Acceptance IDs:** `KHAHP-20.01A`, `KHAHP-20.01B`, `KHAHP-20.01C` — **OPEN / NOT SIGNED OFF**.

#### 20.02 — Running systemd service inventory

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-013`.
- **Required A/B/C evidence:** Provenance of running systemd service inventory; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Classify dependencies and verify expected-role persistence; do not disable blindly.
- **Acceptance IDs:** `KHAHP-20.02A`, `KHAHP-20.02B`, `KHAHP-20.02C` — **OPEN / NOT SIGNED OFF**.

#### 20.03 — Socket/path/timer activated service inventory

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-013`.
- **Required A/B/C evidence:** Provenance of socket/path/timer activated service inventory; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Classify dependencies and verify expected-role persistence; do not disable blindly.
- **Acceptance IDs:** `KHAHP-20.03A`, `KHAHP-20.03B`, `KHAHP-20.03C` — **OPEN / NOT SIGNED OFF**.

#### 20.04 — Kicksecure-required service attribution

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-013`, `I15-014`.
- **Required A/B/C evidence:** Provenance of kicksecure-required service attribution; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Classify dependencies and verify expected-role persistence; do not disable blindly.
- **Acceptance IDs:** `KHAHP-20.04A`, `KHAHP-20.04B`, `KHAHP-20.04C` — **OPEN / NOT SIGNED OFF**.

#### 20.05 — Unexpected or unnecessary service classification

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-014`.
- **Required A/B/C evidence:** Provenance of unexpected or unnecessary service classification; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Classify dependencies and verify expected-role persistence; do not disable blindly.
- **Acceptance IDs:** `KHAHP-20.05A`, `KHAHP-20.05B`, `KHAHP-20.05C` — **OPEN / NOT SIGNED OFF**.

#### 20.06 — Listener-to-service ownership correlation

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-013`, `I15-014`.
- **Required A/B/C evidence:** Provenance of listener-to-service ownership correlation; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Classify dependencies and verify expected-role persistence; do not disable blindly.
- **Acceptance IDs:** `KHAHP-20.06A`, `KHAHP-20.06B`, `KHAHP-20.06C` — **OPEN / NOT SIGNED OFF**.

#### 20.07 — Reboot persistence and failed-service review

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-013`.
- **Required A/B/C evidence:** Provenance of reboot persistence and failed-service review; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Classify dependencies and verify expected-role persistence; do not disable blindly.
- **Acceptance IDs:** `KHAHP-20.07A`, `KHAHP-20.07B`, `KHAHP-20.07C` — **OPEN / NOT SIGNED OFF**.


### Section 21: systemd Service Sandboxing

#### 21.01 — systemd-analyze security baseline

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-015`.
- **Required A/B/C evidence:** Provenance of systemd-analyze security baseline; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Rehearse proposed additional sandbox restrictions without breaking DNS.
- **Acceptance IDs:** `KHAHP-21.01A`, `KHAHP-21.01B`, `KHAHP-21.01C` — **OPEN / NOT SIGNED OFF**.

#### 21.02 — NoNewPrivileges adoption

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-016`.
- **Required A/B/C evidence:** Provenance of nonewprivileges adoption; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Rehearse proposed additional sandbox restrictions without breaking DNS.
- **Acceptance IDs:** `KHAHP-21.02A`, `KHAHP-21.02B`, `KHAHP-21.02C` — **OPEN / NOT SIGNED OFF**.

#### 21.03 — ProtectSystem/ProtectHome restrictions

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-015`.
- **Required A/B/C evidence:** Provenance of protectsystem/protecthome restrictions; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Rehearse proposed additional sandbox restrictions without breaking DNS.
- **Acceptance IDs:** `KHAHP-21.03A`, `KHAHP-21.03B`, `KHAHP-21.03C` — **OPEN / NOT SIGNED OFF**.

#### 21.04 — PrivateTmp/PrivateDevices isolation

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-016`.
- **Required A/B/C evidence:** Provenance of privatetmp/privatedevices isolation; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Rehearse proposed additional sandbox restrictions without breaking DNS.
- **Acceptance IDs:** `KHAHP-21.04A`, `KHAHP-21.04B`, `KHAHP-21.04C` — **OPEN / NOT SIGNED OFF**.

#### 21.05 — CapabilityBoundingSet and ambient capabilities

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-015`, `I15-016`.
- **Required A/B/C evidence:** Provenance of capabilityboundingset and ambient capabilities; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Rehearse proposed additional sandbox restrictions without breaking DNS.
- **Acceptance IDs:** `KHAHP-21.05A`, `KHAHP-21.05B`, `KHAHP-21.05C` — **OPEN / NOT SIGNED OFF**.

#### 21.06 — RestrictNamespaces/SystemCallFilter/address-family controls

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-016`.
- **Required A/B/C evidence:** Provenance of restrictnamespaces/systemcallfilter/address-family controls; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Rehearse proposed additional sandbox restrictions without breaking DNS.
- **Acceptance IDs:** `KHAHP-21.06A`, `KHAHP-21.06B`, `KHAHP-21.06C` — **OPEN / NOT SIGNED OFF**.

#### 21.07 — Service-specific compatibility exceptions and regressions

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-015`, `I15-016`.
- **Required A/B/C evidence:** Provenance of service-specific compatibility exceptions and regressions; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Rehearse proposed additional sandbox restrictions without breaking DNS.
- **Acceptance IDs:** `KHAHP-21.07A`, `KHAHP-21.07B`, `KHAHP-21.07C` — **OPEN / NOT SIGNED OFF**.


### Section 22: System.map / Core Dumps / PStore

#### 22.01 — System.map exposure and removal policy

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-017`.
- **Required A/B/C evidence:** Provenance of system.map exposure and removal policy; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm ongoing enforcement after updates; record forensic trade-offs.
- **Acceptance IDs:** `KHAHP-22.01A`, `KHAHP-22.01B`, `KHAHP-22.01C` — **OPEN / NOT SIGNED OFF**.

#### 22.02 — systemd-coredump configuration

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-017`.
- **Required A/B/C evidence:** Provenance of systemd-coredump configuration; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm ongoing enforcement after updates; record forensic trade-offs.
- **Acceptance IDs:** `KHAHP-22.02A`, `KHAHP-22.02B`, `KHAHP-22.02C` — **OPEN / NOT SIGNED OFF**.

#### 22.03 — kernel.core_pattern effective state

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-017`.
- **Required A/B/C evidence:** Provenance of kernel.core_pattern effective state; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm ongoing enforcement after updates; record forensic trade-offs.
- **Acceptance IDs:** `KHAHP-22.03A`, `KHAHP-22.03B`, `KHAHP-22.03C` — **OPEN / NOT SIGNED OFF**.

#### 22.04 — fs.suid_dumpable effective state

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-017`.
- **Required A/B/C evidence:** Provenance of fs.suid_dumpable effective state; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm ongoing enforcement after updates; record forensic trade-offs.
- **Acceptance IDs:** `KHAHP-22.04A`, `KHAHP-22.04B`, `KHAHP-22.04C` — **OPEN / NOT SIGNED OFF**.

#### 22.05 — pstore retention/disable policy

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-017`.
- **Required A/B/C evidence:** Provenance of pstore retention/disable policy; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm ongoing enforcement after updates; record forensic trade-offs.
- **Acceptance IDs:** `KHAHP-22.05A`, `KHAHP-22.05B`, `KHAHP-22.05C` — **OPEN / NOT SIGNED OFF**.

#### 22.06 — EFI pstore and ERST boot controls

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-017`.
- **Required A/B/C evidence:** Provenance of efi pstore and erst boot controls; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm ongoing enforcement after updates; record forensic trade-offs.
- **Acceptance IDs:** `KHAHP-22.06A`, `KHAHP-22.06B`, `KHAHP-22.06C` — **OPEN / NOT SIGNED OFF**.

#### 22.07 — Crash-evidence privacy versus diagnostic requirements

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-018`.
- **Required A/B/C evidence:** Provenance of crash-evidence privacy versus diagnostic requirements; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm ongoing enforcement after updates; record forensic trade-offs.
- **Acceptance IDs:** `KHAHP-22.07A`, `KHAHP-22.07B`, `KHAHP-22.07C` — **OPEN / NOT SIGNED OFF**.


### Section 23: Journald / Logging / Logrotate

#### 23.01 — journald security-misc configuration

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-019`.
- **Required A/B/C evidence:** Provenance of journald security-misc configuration; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Approve retention/rotation/access policy and time continuity evidence.
- **Acceptance IDs:** `KHAHP-23.01A`, `KHAHP-23.01B`, `KHAHP-23.01C` — **OPEN / NOT SIGNED OFF**.

#### 23.02 — Persistent versus volatile journal storage

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-019`.
- **Required A/B/C evidence:** Provenance of persistent versus volatile journal storage; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Approve retention/rotation/access policy and time continuity evidence.
- **Acceptance IDs:** `KHAHP-23.02A`, `KHAHP-23.02B`, `KHAHP-23.02C` — **OPEN / NOT SIGNED OFF**.

#### 23.03 — Journal file permissions and ownership

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-019`.
- **Required A/B/C evidence:** Provenance of journal file permissions and ownership; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Approve retention/rotation/access policy and time continuity evidence.
- **Acceptance IDs:** `KHAHP-23.03A`, `KHAHP-23.03B`, `KHAHP-23.03C` — **OPEN / NOT SIGNED OFF**.

#### 23.04 — Rate limiting and size/retention policy

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-019`.
- **Required A/B/C evidence:** Provenance of rate limiting and size/retention policy; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Approve retention/rotation/access policy and time continuity evidence.
- **Acceptance IDs:** `KHAHP-23.04A`, `KHAHP-23.04B`, `KHAHP-23.04C` — **OPEN / NOT SIGNED OFF**.

#### 23.05 — Forwarding/syslog integration state

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-019`.
- **Required A/B/C evidence:** Provenance of forwarding/syslog integration state; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Approve retention/rotation/access policy and time continuity evidence.
- **Acceptance IDs:** `KHAHP-23.05A`, `KHAHP-23.05B`, `KHAHP-23.05C` — **OPEN / NOT SIGNED OFF**.

#### 23.06 — logrotate configuration and sensitive-log modes

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-019`.
- **Required A/B/C evidence:** Provenance of logrotate configuration and sensitive-log modes; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Approve retention/rotation/access policy and time continuity evidence.
- **Acceptance IDs:** `KHAHP-23.06A`, `KHAHP-23.06B`, `KHAHP-23.06C` — **OPEN / NOT SIGNED OFF**.

#### 23.07 — Log integrity, time coherence and reboot persistence

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-020`.
- **Required A/B/C evidence:** Provenance of log integrity, time coherence and reboot persistence; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Approve retention/rotation/access policy and time continuity evidence.
- **Acceptance IDs:** `KHAHP-23.07A`, `KHAHP-23.07B`, `KHAHP-23.07C` — **OPEN / NOT SIGNED OFF**.


### Section 24: Panic / Recovery / Emergency Shutdown

#### 24.01 — kernel panic-on-oops policy

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-021`.
- **Required A/B/C evidence:** Provenance of kernel panic-on-oops policy; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Rehearse safe recovery offline; no destructive production panic tests.
- **Acceptance IDs:** `KHAHP-24.01A`, `KHAHP-24.01B`, `KHAHP-24.01C` — **OPEN / NOT SIGNED OFF**.

#### 24.02 — panic timeout and fail-closed behavior

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-021`.
- **Required A/B/C evidence:** Provenance of panic timeout and fail-closed behavior; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Rehearse safe recovery offline; no destructive production panic tests.
- **Acceptance IDs:** `KHAHP-24.02A`, `KHAHP-24.02B`, `KHAHP-24.02C` — **OPEN / NOT SIGNED OFF**.

#### 24.03 — emerg-shutdown.service provenance and state

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-022`.
- **Required A/B/C evidence:** Provenance of emerg-shutdown.service provenance and state; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Rehearse safe recovery offline; no destructive production panic tests.
- **Acceptance IDs:** `KHAHP-24.03A`, `KHAHP-24.03B`, `KHAHP-24.03C` — **OPEN / NOT SIGNED OFF**.

#### 24.04 — rescue/emergency target restrictions

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-021`.
- **Required A/B/C evidence:** Provenance of rescue/emergency target restrictions; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Rehearse safe recovery offline; no destructive production panic tests.
- **Acceptance IDs:** `KHAHP-24.04A`, `KHAHP-24.04B`, `KHAHP-24.04C` — **OPEN / NOT SIGNED OFF**.

#### 24.05 — rd.emergency=halt and rd.shell=0 behavior

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-021`.
- **Required A/B/C evidence:** Provenance of rd.emergency=halt and rd.shell=0 behavior; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Rehearse safe recovery offline; no destructive production panic tests.
- **Acceptance IDs:** `KHAHP-24.05A`, `KHAHP-24.05B`, `KHAHP-24.05C` — **OPEN / NOT SIGNED OFF**.

#### 24.06 — Magic SysRq and recovery-surface policy

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-021`.
- **Required A/B/C evidence:** Provenance of magic sysrq and recovery-surface policy; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Rehearse safe recovery offline; no destructive production panic tests.
- **Acceptance IDs:** `KHAHP-24.06A`, `KHAHP-24.06B`, `KHAHP-24.06C` — **OPEN / NOT SIGNED OFF**.

#### 24.07 — Controlled failure/recovery evidence and rollback

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I15-022`.
- **Required A/B/C evidence:** Provenance of controlled failure/recovery evidence and rollback; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Rehearse safe recovery offline; no destructive production panic tests.
- **Acceptance IDs:** `KHAHP-24.07A`, `KHAHP-24.07B`, `KHAHP-24.07C` — **OPEN / NOT SIGNED OFF**.


### Section 25: RAM Wipe

#### 25.01 — ram-wipe package provenance and version

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-004`, `I-017`.
- **Required A/B/C evidence:** Provenance of ram-wipe package provenance and version; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm shutdown hooks, swap crypto path and residual cold-boot risk.
- **Acceptance IDs:** `KHAHP-25.01A`, `KHAHP-25.01B`, `KHAHP-25.01C` — **OPEN / NOT SIGNED OFF**.

#### 25.02 — GRUB/package RAM-wipe source presence

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-004`.
- **Required A/B/C evidence:** Provenance of grub/package ram-wipe source presence; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm shutdown hooks, swap crypto path and residual cold-boot risk.
- **Acceptance IDs:** `KHAHP-25.02A`, `KHAHP-25.02B`, `KHAHP-25.02C` — **OPEN / NOT SIGNED OFF**.

#### 25.03 — init_on_alloc/init_on_free live correlation

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of init_on_alloc/init_on_free live correlation; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm shutdown hooks, swap crypto path and residual cold-boot risk.
- **Acceptance IDs:** `KHAHP-25.03A`, `KHAHP-25.03B`, `KHAHP-25.03C` — **OPEN / NOT SIGNED OFF**.

#### 25.04 — Shutdown/reboot wipe hook inventory

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-004`, `I-017`.
- **Required A/B/C evidence:** Provenance of shutdown/reboot wipe hook inventory; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm shutdown hooks, swap crypto path and residual cold-boot risk.
- **Acceptance IDs:** `KHAHP-25.04A`, `KHAHP-25.04B`, `KHAHP-25.04C` — **OPEN / NOT SIGNED OFF**.

#### 25.05 — Swap/LUKS interaction during shutdown

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-003`.
- **Required A/B/C evidence:** Provenance of swap/luks interaction during shutdown; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm shutdown hooks, swap crypto path and residual cold-boot risk.
- **Acceptance IDs:** `KHAHP-25.05A`, `KHAHP-25.05B`, `KHAHP-25.05C` — **OPEN / NOT SIGNED OFF**.

#### 25.06 — Controlled reboot/shutdown persistence test

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-003`.
- **Required A/B/C evidence:** Provenance of controlled reboot/shutdown persistence test; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm shutdown hooks, swap crypto path and residual cold-boot risk.
- **Acceptance IDs:** `KHAHP-25.06A`, `KHAHP-25.06B`, `KHAHP-25.06C` — **OPEN / NOT SIGNED OFF**.

#### 25.07 — Limitations of software RAM wiping and cold-boot scope

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-004`.
- **Required A/B/C evidence:** Provenance of limitations of software ram wiping and cold-boot scope; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm shutdown hooks, swap crypto path and residual cold-boot risk.
- **Acceptance IDs:** `KHAHP-25.07A`, `KHAHP-25.07B`, `KHAHP-25.07C` — **OPEN / NOT SIGNED OFF**.


### Section 26: USBGuard / Peripheral Security

#### 26.01 — usbguard daemon and DBus service state

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of usbguard daemon and dbus service state; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Verify keyboard rejection through real keystroke test and first-match logs; test composite and network devices.
- **Acceptance IDs:** `KHAHP-26.01A`, `KHAHP-26.01B`, `KHAHP-26.01C` — **OPEN / NOT SIGNED OFF**.

#### 26.02 — Policy files and rule provenance

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-002`.
- **Required A/B/C evidence:** Provenance of policy files and rule provenance; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Verify keyboard rejection through real keystroke test and first-match logs; test composite and network devices.
- **Acceptance IDs:** `KHAHP-26.02A`, `KHAHP-26.02B`, `KHAHP-26.02C` — **OPEN / NOT SIGNED OFF**.

#### 26.03 — ImplicitPolicyTarget and device-policy settings

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of implicitpolicytarget and device-policy settings; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Verify keyboard rejection through real keystroke test and first-match logs; test composite and network devices.
- **Acceptance IDs:** `KHAHP-26.03A`, `KHAHP-26.03B`, `KHAHP-26.03C` — **OPEN / NOT SIGNED OFF**.

#### 26.04 — Allowed keyboard/mouse/audio/video/storage classes

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-001`.
- **Required A/B/C evidence:** Provenance of allowed keyboard/mouse/audio/video/storage classes; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Verify keyboard rejection through real keystroke test and first-match logs; test composite and network devices.
- **Acceptance IDs:** `KHAHP-26.04A`, `KHAHP-26.04B`, `KHAHP-26.04C` — **OPEN / NOT SIGNED OFF**.

#### 26.05 — Rejected HID+extra and RNDIS/network-device patterns

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-001`, `I-002`.
- **Required A/B/C evidence:** Provenance of rejected hid+extra and rndis/network-device patterns; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Verify keyboard rejection through real keystroke test and first-match logs; test composite and network devices.
- **Acceptance IDs:** `KHAHP-26.05A`, `KHAHP-26.05B`, `KHAHP-26.05C` — **OPEN / NOT SIGNED OFF**.

#### 26.06 — IPC authorization/notifier behavior

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of ipc authorization/notifier behavior; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Verify keyboard rejection through real keystroke test and first-match logs; test composite and network devices.
- **Acceptance IDs:** `KHAHP-26.06A`, `KHAHP-26.06B`, `KHAHP-26.06C` — **OPEN / NOT SIGNED OFF**.

#### 26.07 — Hot-plug negative tests and reboot persistence

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-001`, `I-002`, `I-018`.
- **Required A/B/C evidence:** Provenance of hot-plug negative tests and reboot persistence; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Verify keyboard rejection through real keystroke test and first-match logs; test composite and network devices.
- **Acceptance IDs:** `KHAHP-26.07A`, `KHAHP-26.07B`, `KHAHP-26.07C` — **OPEN / NOT SIGNED OFF**.


### Section 27: NetworkManager / Wi-Fi / MAC / DHCP

#### 27.01 — NetworkManager package/service state

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of networkmanager package/service state; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Correlate over-air identity and DHCP identifier on owned network; persist after reconnect.
- **Acceptance IDs:** `KHAHP-27.01A`, `KHAHP-27.01B`, `KHAHP-27.01C` — **OPEN / NOT SIGNED OFF**.

#### 27.02 — Saved Wi-Fi profile inventory and autoconnect

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of saved wi-fi profile inventory and autoconnect; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Correlate over-air identity and DHCP identifier on owned network; persist after reconnect.
- **Acceptance IDs:** `KHAHP-27.02A`, `KHAHP-27.02B`, `KHAHP-27.02C` — **OPEN / NOT SIGNED OFF**.

#### 27.03 — Active-profile cloned-MAC and DHCP privacy settings

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-005`.
- **Required A/B/C evidence:** Provenance of active-profile cloned-mac and dhcp privacy settings; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Correlate over-air identity and DHCP identifier on owned network; persist after reconnect.
- **Acceptance IDs:** `KHAHP-27.03A`, `KHAHP-27.03B`, `KHAHP-27.03C` — **OPEN / NOT SIGNED OFF**.

#### 27.04 — Scan MAC randomization

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of scan mac randomization; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Correlate over-air identity and DHCP identifier on owned network; persist after reconnect.
- **Acceptance IDs:** `KHAHP-27.04A`, `KHAHP-27.04B`, `KHAHP-27.04C` — **OPEN / NOT SIGNED OFF**.

#### 27.05 — Ethernet MAC randomization policy

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of ethernet mac randomization policy; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Correlate over-air identity and DHCP identifier on owned network; persist after reconnect.
- **Acceptance IDs:** `KHAHP-27.05A`, `KHAHP-27.05B`, `KHAHP-27.05C` — **OPEN / NOT SIGNED OFF**.

#### 27.06 — Runtime MAC versus permanent hardware MAC

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-005`.
- **Required A/B/C evidence:** Provenance of runtime mac versus permanent hardware mac; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Correlate over-air identity and DHCP identifier on owned network; persist after reconnect.
- **Acceptance IDs:** `KHAHP-27.06A`, `KHAHP-27.06B`, `KHAHP-27.06C` — **OPEN / NOT SIGNED OFF**.

#### 27.07 — DHCP client identifier and profile persistence

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-006`.
- **Required A/B/C evidence:** Provenance of dhcp client identifier and profile persistence; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Correlate over-air identity and DHCP identifier on owned network; persist after reconnect.
- **Acceptance IDs:** `KHAHP-27.07A`, `KHAHP-27.07B`, `KHAHP-27.07C` — **OPEN / NOT SIGNED OFF**.


### Section 28: IPv6 Policy

#### 28.01 — ipv6.disable=1 boot parameter

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-019`.
- **Required A/B/C evidence:** Provenance of ipv6.disable=1 boot parameter; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Resolve intentional disablement versus future advanced dual-stack privacy policy before changes.
- **Acceptance IDs:** `KHAHP-28.01A`, `KHAHP-28.01B`, `KHAHP-28.01C` — **OPEN / NOT SIGNED OFF**.

#### 28.02 — Absence of IPv6 addresses

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of absence of ipv6 addresses; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Resolve intentional disablement versus future advanced dual-stack privacy policy before changes.
- **Acceptance IDs:** `KHAHP-28.02A`, `KHAHP-28.02B`, `KHAHP-28.02C` — **OPEN / NOT SIGNED OFF**.

#### 28.03 — Absence of IPv6 routes

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of absence of ipv6 routes; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Resolve intentional disablement versus future advanced dual-stack privacy policy before changes.
- **Acceptance IDs:** `KHAHP-28.03A`, `KHAHP-28.03B`, `KHAHP-28.03C` — **OPEN / NOT SIGNED OFF**.

#### 28.04 — NetworkManager IPv6 method/state

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-007`, `I-019`.
- **Required A/B/C evidence:** Provenance of networkmanager ipv6 method/state; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Resolve intentional disablement versus future advanced dual-stack privacy policy before changes.
- **Acceptance IDs:** `KHAHP-28.04A`, `KHAHP-28.04B`, `KHAHP-28.04C` — **OPEN / NOT SIGNED OFF**.

#### 28.05 — Resolver absence of IPv6 nameservers

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of resolver absence of ipv6 nameservers; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Resolve intentional disablement versus future advanced dual-stack privacy policy before changes.
- **Acceptance IDs:** `KHAHP-28.05A`, `KHAHP-28.05B`, `KHAHP-28.05C` — **OPEN / NOT SIGNED OFF**.

#### 28.06 — IPv6 TCP/UDP listener exposure

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-007`.
- **Required A/B/C evidence:** Provenance of ipv6 tcp/udp listener exposure; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Resolve intentional disablement versus future advanced dual-stack privacy policy before changes.
- **Acceptance IDs:** `KHAHP-28.06A`, `KHAHP-28.06B`, `KHAHP-28.06C` — **OPEN / NOT SIGNED OFF**.

#### 28.07 — Reboot persistence and DNS/HTTPS regression test

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-007`, `I-019`.
- **Required A/B/C evidence:** Provenance of reboot persistence and dns/https regression test; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Resolve intentional disablement versus future advanced dual-stack privacy policy before changes.
- **Acceptance IDs:** `KHAHP-28.07A`, `KHAHP-28.07B`, `KHAHP-28.07C` — **OPEN / NOT SIGNED OFF**.


### Section 29: Unbound / Local DNS Architecture

#### 29.01 — Unbound package/service state

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of unbound package/service state; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm DHCP transition and resolver fail-safe without inadvertently breaking browsing.
- **Acceptance IDs:** `KHAHP-29.01A`, `KHAHP-29.01B`, `KHAHP-29.01C` — **OPEN / NOT SIGNED OFF**.

#### 29.02 — loopback DNS listener UDP/TCP listener and non-loopback absence

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of loopback DNS listener udp/tcp listener and non-loopback absence; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm DHCP transition and resolver fail-safe without inadvertently breaking browsing.
- **Acceptance IDs:** `KHAHP-29.02A`, `KHAHP-29.02B`, `KHAHP-29.02C` — **OPEN / NOT SIGNED OFF**.

#### 29.03 — resolv.conf local-resolver wiring

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-008`.
- **Required A/B/C evidence:** Provenance of resolv.conf local-resolver wiring; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm DHCP transition and resolver fail-safe without inadvertently breaking browsing.
- **Acceptance IDs:** `KHAHP-29.03A`, `KHAHP-29.03B`, `KHAHP-29.03C` — **OPEN / NOT SIGNED OFF**.

#### 29.04 — NetworkManager effective DNS assignment

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-008`.
- **Required A/B/C evidence:** Provenance of networkmanager effective dns assignment; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm DHCP transition and resolver fail-safe without inadvertently breaking browsing.
- **Acceptance IDs:** `KHAHP-29.04A`, `KHAHP-29.04B`, `KHAHP-29.04C` — **OPEN / NOT SIGNED OFF**.

#### 29.05 — Unbound configuration include tree validation

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of unbound configuration include tree validation; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm DHCP transition and resolver fail-safe without inadvertently breaking browsing.
- **Acceptance IDs:** `KHAHP-29.05A`, `KHAHP-29.05B`, `KHAHP-29.05C` — **OPEN / NOT SIGNED OFF**.

#### 29.06 — DoT forward-zone and IPv6 source policy

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-009`.
- **Required A/B/C evidence:** Provenance of dot forward-zone and ipv6 source policy; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm DHCP transition and resolver fail-safe without inadvertently breaking browsing.
- **Acceptance IDs:** `KHAHP-29.06A`, `KHAHP-29.06B`, `KHAHP-29.06C` — **OPEN / NOT SIGNED OFF**.

#### 29.07 — USER/SYSMAINT service behavior and persistence

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-008`, `I-020`.
- **Required A/B/C evidence:** Provenance of user/sysmaint service behavior and persistence; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm DHCP transition and resolver fail-safe without inadvertently breaking browsing.
- **Acceptance IDs:** `KHAHP-29.07A`, `KHAHP-29.07B`, `KHAHP-29.07C` — **OPEN / NOT SIGNED OFF**.


### Section 30: DNSSEC / DoT / DNS Leak Prevention

#### 30.01 — DNSSEC positive validation test

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-021`.
- **Required A/B/C evidence:** Provenance of dnssec positive validation test; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Demonstrate Unbound-owned authenticated TLS; prove UDP/TCP direct DNS egress policy with owned peer.
- **Acceptance IDs:** `KHAHP-30.01A`, `KHAHP-30.01B`, `KHAHP-30.01C` — **OPEN / NOT SIGNED OFF**.

#### 30.02 — Broken-DNSSEC negative test

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-021`.
- **Required A/B/C evidence:** Provenance of broken-dnssec negative test; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Demonstrate Unbound-owned authenticated TLS; prove UDP/TCP direct DNS egress policy with owned peer.
- **Acceptance IDs:** `KHAHP-30.02A`, `KHAHP-30.02B`, `KHAHP-30.02C` — **OPEN / NOT SIGNED OFF**.

#### 30.03 — DoT forwarding configuration and reachability scope

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-009`.
- **Required A/B/C evidence:** Provenance of dot forwarding configuration and reachability scope; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Demonstrate Unbound-owned authenticated TLS; prove UDP/TCP direct DNS egress policy with owned peer.
- **Acceptance IDs:** `KHAHP-30.03A`, `KHAHP-30.03B`, `KHAHP-30.03C` — **OPEN / NOT SIGNED OFF**.

#### 30.04 — Plaintext external UDP/53 block

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-010`.
- **Required A/B/C evidence:** Provenance of plaintext external udp/53 block; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Demonstrate Unbound-owned authenticated TLS; prove UDP/TCP direct DNS egress policy with owned peer.
- **Acceptance IDs:** `KHAHP-30.04A`, `KHAHP-30.04B`, `KHAHP-30.04C` — **OPEN / NOT SIGNED OFF**.

#### 30.05 — Plaintext external TCP/53 block

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-010`.
- **Required A/B/C evidence:** Provenance of plaintext external tcp/53 block; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Demonstrate Unbound-owned authenticated TLS; prove UDP/TCP direct DNS egress policy with owned peer.
- **Acceptance IDs:** `KHAHP-30.05A`, `KHAHP-30.05B`, `KHAHP-30.05C` — **OPEN / NOT SIGNED OFF**.

#### 30.06 — Local DNS functionality after firewall enforcement

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-021`.
- **Required A/B/C evidence:** Provenance of local dns functionality after firewall enforcement; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Demonstrate Unbound-owned authenticated TLS; prove UDP/TCP direct DNS egress policy with owned peer.
- **Acceptance IDs:** `KHAHP-30.06A`, `KHAHP-30.06B`, `KHAHP-30.06C` — **OPEN / NOT SIGNED OFF**.

#### 30.07 — DNS leak/bypass and reboot-persistence testing

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-011`.
- **Required A/B/C evidence:** Provenance of dns leak/bypass and reboot-persistence testing; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Demonstrate Unbound-owned authenticated TLS; prove UDP/TCP direct DNS egress policy with owned peer.
- **Acceptance IDs:** `KHAHP-30.07A`, `KHAHP-30.07B`, `KHAHP-30.07C` — **OPEN / NOT SIGNED OFF**.


### Section 31: nftables Firewall

#### 31.01 — nftables package/service/runtime ruleset state

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of nftables package/service/runtime ruleset state; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Prove effective outbound packet verdict and exact loaded-ruleset persistence.
- **Acceptance IDs:** `KHAHP-31.01A`, `KHAHP-31.01B`, `KHAHP-31.01C` — **OPEN / NOT SIGNED OFF**.

#### 31.02 — Dedicated inet kicksecure_hardening table

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of dedicated inet kicksecure_hardening table; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Prove effective outbound packet verdict and exact loaded-ruleset persistence.
- **Acceptance IDs:** `KHAHP-31.02A`, `KHAHP-31.02B`, `KHAHP-31.02C` — **OPEN / NOT SIGNED OFF**.

#### 31.03 — Input default-drop policy

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of input default-drop policy; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Prove effective outbound packet verdict and exact loaded-ruleset persistence.
- **Acceptance IDs:** `KHAHP-31.03A`, `KHAHP-31.03B`, `KHAHP-31.03C` — **OPEN / NOT SIGNED OFF**.

#### 31.04 — Forward default-drop policy

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of forward default-drop policy; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Prove effective outbound packet verdict and exact loaded-ruleset persistence.
- **Acceptance IDs:** `KHAHP-31.04A`, `KHAHP-31.04B`, `KHAHP-31.04C` — **OPEN / NOT SIGNED OFF**.

#### 31.05 — Loopback, established/related and invalid handling

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of loopback, established/related and invalid handling; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Prove effective outbound packet verdict and exact loaded-ruleset persistence.
- **Acceptance IDs:** `KHAHP-31.05A`, `KHAHP-31.05B`, `KHAHP-31.05C` — **OPEN / NOT SIGNED OFF**.

#### 31.06 — DHCP/ICMP and required inbound exceptions

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-012`.
- **Required A/B/C evidence:** Provenance of dhcp/icmp and required inbound exceptions; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Prove effective outbound packet verdict and exact loaded-ruleset persistence.
- **Acceptance IDs:** `KHAHP-31.06A`, `KHAHP-31.06B`, `KHAHP-31.06C` — **OPEN / NOT SIGNED OFF**.

#### 31.07 — Static syntax, reload safety and reboot persistence

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-012`, `I-013`.
- **Required A/B/C evidence:** Provenance of static syntax, reload safety and reboot persistence; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Prove effective outbound packet verdict and exact loaded-ruleset persistence.
- **Acceptance IDs:** `KHAHP-31.07A`, `KHAHP-31.07B`, `KHAHP-31.07C` — **OPEN / NOT SIGNED OFF**.


### Section 32: LAN Discovery / Multicast / LLMNR / mDNS

#### 32.01 — Avahi/mDNS daemon state

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-022`.
- **Required A/B/C evidence:** Provenance of avahi/mdns daemon state; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Collect protocol-specific peer mDNS/LLMNR/SSDP evidence; do not infer from unicast scans.
- **Acceptance IDs:** `KHAHP-32.01A`, `KHAHP-32.01B`, `KHAHP-32.01C` — **OPEN / NOT SIGNED OFF**.

#### 32.02 — LLMNR/resolved multicast name-resolution state

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-022`.
- **Required A/B/C evidence:** Provenance of llmnr/resolved multicast name-resolution state; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Collect protocol-specific peer mDNS/LLMNR/SSDP evidence; do not infer from unicast scans.
- **Acceptance IDs:** `KHAHP-32.02A`, `KHAHP-32.02B`, `KHAHP-32.02C` — **OPEN / NOT SIGNED OFF**.

#### 32.03 — wsdd/Samba discovery state

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of wsdd/samba discovery state; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Collect protocol-specific peer mDNS/LLMNR/SSDP evidence; do not infer from unicast scans.
- **Acceptance IDs:** `KHAHP-32.03A`, `KHAHP-32.03B`, `KHAHP-32.03C` — **OPEN / NOT SIGNED OFF**.

#### 32.04 — rpcbind/minidlna/UPnP service state

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of rpcbind/minidlna/upnp service state; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Collect protocol-specific peer mDNS/LLMNR/SSDP evidence; do not infer from unicast scans.
- **Acceptance IDs:** `KHAHP-32.04A`, `KHAHP-32.04B`, `KHAHP-32.04C` — **OPEN / NOT SIGNED OFF**.

#### 32.05 — Multicast/discovery TCP+UDP listener inventory

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-022`.
- **Required A/B/C evidence:** Provenance of multicast/discovery tcp+udp listener inventory; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Collect protocol-specific peer mDNS/LLMNR/SSDP evidence; do not infer from unicast scans.
- **Acceptance IDs:** `KHAHP-32.05A`, `KHAHP-32.05B`, `KHAHP-32.05C` — **OPEN / NOT SIGNED OFF**.

#### 32.06 — Firewall exposure of discovery ports

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of firewall exposure of discovery ports; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Collect protocol-specific peer mDNS/LLMNR/SSDP evidence; do not infer from unicast scans.
- **Acceptance IDs:** `KHAHP-32.06A`, `KHAHP-32.06B`, `KHAHP-32.06C` — **OPEN / NOT SIGNED OFF**.

#### 32.07 — Negative LAN discovery and reboot-persistence test

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-014`, `I-022`.
- **Required A/B/C evidence:** Provenance of negative lan discovery and reboot-persistence test; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Collect protocol-specific peer mDNS/LLMNR/SSDP evidence; do not infer from unicast scans.
- **Acceptance IDs:** `KHAHP-32.07A`, `KHAHP-32.07B`, `KHAHP-32.07C` — **OPEN / NOT SIGNED OFF**.


### Section 33: Tor / SOCKS / DNS Isolation

#### 33.01 — Tor package/service state

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of tor package/service state; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Test Tor Browser-specific proxy/DNS routing and safe fail-close without a disruptive global service stop.
- **Acceptance IDs:** `KHAHP-33.01A`, `KHAHP-33.01B`, `KHAHP-33.01C` — **OPEN / NOT SIGNED OFF**.

#### 33.02 — SOCKS listener loopback Tor SOCKS listener and non-loopback absence

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of socks listener loopback Tor SOCKS listener and non-loopback absence; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Test Tor Browser-specific proxy/DNS routing and safe fail-close without a disruptive global service stop.
- **Acceptance IDs:** `KHAHP-33.02A`, `KHAHP-33.02B`, `KHAHP-33.02C` — **OPEN / NOT SIGNED OFF**.

#### 33.03 — Tor configuration provenance and syntax validation

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of tor configuration provenance and syntax validation; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Test Tor Browser-specific proxy/DNS routing and safe fail-close without a disruptive global service stop.
- **Acceptance IDs:** `KHAHP-33.03A`, `KHAHP-33.03B`, `KHAHP-33.03C` — **OPEN / NOT SIGNED OFF**.

#### 33.04 — Application proxy routing where intended

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-015`.
- **Required A/B/C evidence:** Provenance of application proxy routing where intended; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Test Tor Browser-specific proxy/DNS routing and safe fail-close without a disruptive global service stop.
- **Acceptance IDs:** `KHAHP-33.04A`, `KHAHP-33.04B`, `KHAHP-33.04C` — **OPEN / NOT SIGNED OFF**.

#### 33.05 — Tor DNS isolation behavior

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-015`.
- **Required A/B/C evidence:** Provenance of tor dns isolation behavior; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Test Tor Browser-specific proxy/DNS routing and safe fail-close without a disruptive global service stop.
- **Acceptance IDs:** `KHAHP-33.05A`, `KHAHP-33.05B`, `KHAHP-33.05C` — **OPEN / NOT SIGNED OFF**.

#### 33.06 — Clearnet bypass classification for Tor-mode applications

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-015`.
- **Required A/B/C evidence:** Provenance of clearnet bypass classification for tor-mode applications; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Test Tor Browser-specific proxy/DNS routing and safe fail-close without a disruptive global service stop.
- **Acceptance IDs:** `KHAHP-33.06A`, `KHAHP-33.06B`, `KHAHP-33.06C` — **OPEN / NOT SIGNED OFF**.

#### 33.07 — Bootstrap, circuit, restart and failure-mode behavior

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-015`.
- **Required A/B/C evidence:** Provenance of bootstrap, circuit, restart and failure-mode behavior; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Test Tor Browser-specific proxy/DNS routing and safe fail-close without a disruptive global service stop.
- **Acceptance IDs:** `KHAHP-33.07A`, `KHAHP-33.07B`, `KHAHP-33.07C` — **OPEN / NOT SIGNED OFF**.


### Section 34: sdwdate / Secure Time / Boot Clock

#### 34.01 — sdwdate package/service state

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of sdwdate package/service state; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Review execution chronology and controlled VM-only clock rollback.
- **Acceptance IDs:** `KHAHP-34.01A`, `KHAHP-34.01B`, `KHAHP-34.01C` — **OPEN / NOT SIGNED OFF**.

#### 34.02 — timesanitycheck execution state

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-016`.
- **Required A/B/C evidence:** Provenance of timesanitycheck execution state; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Review execution chronology and controlled VM-only clock rollback.
- **Acceptance IDs:** `KHAHP-34.02A`, `KHAHP-34.02B`, `KHAHP-34.02C` — **OPEN / NOT SIGNED OFF**.

#### 34.03 — bootclockrandomization execution state

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-016`.
- **Required A/B/C evidence:** Provenance of bootclockrandomization execution state; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Review execution chronology and controlled VM-only clock rollback.
- **Acceptance IDs:** `KHAHP-34.03A`, `KHAHP-34.03B`, `KHAHP-34.03C` — **OPEN / NOT SIGNED OFF**.

#### 34.04 — System clock sanity metadata

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-016`.
- **Required A/B/C evidence:** Provenance of system clock sanity metadata; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Review execution chronology and controlled VM-only clock rollback.
- **Acceptance IDs:** `KHAHP-34.04A`, `KHAHP-34.04B`, `KHAHP-34.04C` — **OPEN / NOT SIGNED OFF**.

#### 34.05 — NTP/systemd-timesyncd conflicts

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of ntp/systemd-timesyncd conflicts; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Review execution chronology and controlled VM-only clock rollback.
- **Acceptance IDs:** `KHAHP-34.05A`, `KHAHP-34.05B`, `KHAHP-34.05C` — **OPEN / NOT SIGNED OFF**.

#### 34.06 — USER versus SYSMAINT time-source behavior

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of user versus sysmaint time-source behavior; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Review execution chronology and controlled VM-only clock rollback.
- **Acceptance IDs:** `KHAHP-34.06A`, `KHAHP-34.06B`, `KHAHP-34.06C` — **OPEN / NOT SIGNED OFF**.

#### 34.07 — Time rollback/jump detection and log coherence

- **Evidence status:** Documented historical baseline, formal acceptance open.
- **Linked engineering record(s):** `I-016`, `I-023`.
- **Required A/B/C evidence:** Provenance of time rollback/jump detection and log coherence; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Review execution chronology and controlled VM-only clock rollback.
- **Acceptance IDs:** `KHAHP-34.07A`, `KHAHP-34.07B`, `KHAHP-34.07C` — **OPEN / NOT SIGNED OFF**.


### Section 35: Entropy / RNG

#### 35.01 — Kernel RNG readiness at boot

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of kernel rng readiness at boot; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Record early-boot quality, seed handling, package choices and role-matched persistence.
- **Acceptance IDs:** `KHAHP-35.01A`, `KHAHP-35.01B`, `KHAHP-35.01C` — **OPEN / NOT SIGNED OFF**.

#### 35.02 — haveged package/service state

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of haveged package/service state; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Record early-boot quality, seed handling, package choices and role-matched persistence.
- **Acceptance IDs:** `KHAHP-35.02A`, `KHAHP-35.02B`, `KHAHP-35.02C` — **OPEN / NOT SIGNED OFF**.

#### 35.03 — jitterentropy-rngd package/service state

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of jitterentropy-rngd package/service state; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Record early-boot quality, seed handling, package choices and role-matched persistence.
- **Acceptance IDs:** `KHAHP-35.03A`, `KHAHP-35.03B`, `KHAHP-35.03C` — **OPEN / NOT SIGNED OFF**.

#### 35.04 — random.trust_cpu boot policy

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of random.trust_cpu boot policy; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Record early-boot quality, seed handling, package choices and role-matched persistence.
- **Acceptance IDs:** `KHAHP-35.04A`, `KHAHP-35.04B`, `KHAHP-35.04C` — **OPEN / NOT SIGNED OFF**.

#### 35.05 — random.trust_bootloader boot policy

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of random.trust_bootloader boot policy; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Record early-boot quality, seed handling, package choices and role-matched persistence.
- **Acceptance IDs:** `KHAHP-35.05A`, `KHAHP-35.05B`, `KHAHP-35.05C` — **OPEN / NOT SIGNED OFF**.

#### 35.06 — Entropy source and /dev/random behavior

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of entropy source and /dev/random behavior; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Record early-boot quality, seed handling, package choices and role-matched persistence.
- **Acceptance IDs:** `KHAHP-35.06A`, `KHAHP-35.06B`, `KHAHP-35.06C` — **OPEN / NOT SIGNED OFF**.

#### 35.07 — Early-boot entropy persistence and regression evidence

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of early-boot entropy persistence and regression evidence; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Record early-boot quality, seed handling, package choices and role-matched persistence.
- **Acceptance IDs:** `KHAHP-35.07A`, `KHAHP-35.07B`, `KHAHP-35.07C` — **OPEN / NOT SIGNED OFF**.


### Section 36: Browser DoH / WebRTC / Telemetry

#### 36.01 — Browser DNS-over-HTTPS/TRR setting

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Linked engineering record(s):** `I-011`.
- **Required A/B/C evidence:** Provenance of browser dns-over-https/trr setting; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Run USER browser checks for DNS-over-HTTPS, WebRTC leakage, telemetry and upgrades.
- **Acceptance IDs:** `KHAHP-36.01A`, `KHAHP-36.01B`, `KHAHP-36.01C` — **OPEN / NOT SIGNED OFF**.

#### 36.02 — Browser proxy DNS routing behavior

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of browser proxy dns routing behavior; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Run USER browser checks for DNS-over-HTTPS, WebRTC leakage, telemetry and upgrades.
- **Acceptance IDs:** `KHAHP-36.02A`, `KHAHP-36.02B`, `KHAHP-36.02C` — **OPEN / NOT SIGNED OFF**.

#### 36.03 — WebRTC/STUN local/public IP exposure

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of webrtc/stun local/public ip exposure; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Run USER browser checks for DNS-over-HTTPS, WebRTC leakage, telemetry and upgrades.
- **Acceptance IDs:** `KHAHP-36.03A`, `KHAHP-36.03B`, `KHAHP-36.03C` — **OPEN / NOT SIGNED OFF**.

#### 36.04 — Telemetry and crash-report settings

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of telemetry and crash-report settings; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Run USER browser checks for DNS-over-HTTPS, WebRTC leakage, telemetry and upgrades.
- **Acceptance IDs:** `KHAHP-36.04A`, `KHAHP-36.04B`, `KHAHP-36.04C` — **OPEN / NOT SIGNED OFF**.

#### 36.05 — Safe browsing/prediction/background network features

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of safe browsing/prediction/background network features; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Run USER browser checks for DNS-over-HTTPS, WebRTC leakage, telemetry and upgrades.
- **Acceptance IDs:** `KHAHP-36.05A`, `KHAHP-36.05B`, `KHAHP-36.05C` — **OPEN / NOT SIGNED OFF**.

#### 36.06 — Extension/add-on inventory and trust

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of extension/add-on inventory and trust; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Run USER browser checks for DNS-over-HTTPS, WebRTC leakage, telemetry and upgrades.
- **Acceptance IDs:** `KHAHP-36.06A`, `KHAHP-36.06B`, `KHAHP-36.06C` — **OPEN / NOT SIGNED OFF**.

#### 36.07 — Browser update, profile persistence and leak tests

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of browser update, profile persistence and leak tests; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Run USER browser checks for DNS-over-HTTPS, WebRTC leakage, telemetry and upgrades.
- **Acceptance IDs:** `KHAHP-36.07A`, `KHAHP-36.07B`, `KHAHP-36.07C` — **OPEN / NOT SIGNED OFF**.


### Section 37: Application / File / Metadata Privacy

#### 37.01 — Desktop search/indexing services

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of desktop search/indexing services; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Revisit app caches, thumbnails, history retention and runtime confinement.
- **Acceptance IDs:** `KHAHP-37.01A`, `KHAHP-37.01B`, `KHAHP-37.01C` — **OPEN / NOT SIGNED OFF**.

#### 37.02 — Thumbnail and preview cache behavior

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of thumbnail and preview cache behavior; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Revisit app caches, thumbnails, history retention and runtime confinement.
- **Acceptance IDs:** `KHAHP-37.02A`, `KHAHP-37.02B`, `KHAHP-37.02C` — **OPEN / NOT SIGNED OFF**.

#### 37.03 — Recent-files/history and clipboard retention

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of recent-files/history and clipboard retention; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Revisit app caches, thumbnails, history retention and runtime confinement.
- **Acceptance IDs:** `KHAHP-37.03A`, `KHAHP-37.03B`, `KHAHP-37.03C` — **OPEN / NOT SIGNED OFF**.

#### 37.04 — Document/image metadata handling

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of document/image metadata handling; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Revisit app caches, thumbnails, history retention and runtime confinement.
- **Acceptance IDs:** `KHAHP-37.04A`, `KHAHP-37.04B`, `KHAHP-37.04C` — **OPEN / NOT SIGNED OFF**.

#### 37.05 — Temporary-file and application-cache exposure

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of temporary-file and application-cache exposure; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Revisit app caches, thumbnails, history retention and runtime confinement.
- **Acceptance IDs:** `KHAHP-37.05A`, `KHAHP-37.05B`, `KHAHP-37.05C` — **OPEN / NOT SIGNED OFF**.

#### 37.06 — Sandboxed versus unsandboxed application inventory

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of sandboxed versus unsandboxed application inventory; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Revisit app caches, thumbnails, history retention and runtime confinement.
- **Acceptance IDs:** `KHAHP-37.06A`, `KHAHP-37.06B`, `KHAHP-37.06C` — **OPEN / NOT SIGNED OFF**.

#### 37.07 — Metadata-removal workflow and regression testing

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of metadata-removal workflow and regression testing; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Revisit app caches, thumbnails, history retention and runtime confinement.
- **Acceptance IDs:** `KHAHP-37.07A`, `KHAHP-37.07B`, `KHAHP-37.07C` — **OPEN / NOT SIGNED OFF**.


### Section 38: Camera / Microphone / Power / Screen Lock

#### 38.01 — Camera hardware/device exposure

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of camera hardware/device exposure; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Prove actual idle lock, lid/suspend/resume authentication and hotplug behavior.
- **Acceptance IDs:** `KHAHP-38.01A`, `KHAHP-38.01B`, `KHAHP-38.01C` — **OPEN / NOT SIGNED OFF**.

#### 38.02 — Microphone hardware/device exposure

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of microphone hardware/device exposure; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Prove actual idle lock, lid/suspend/resume authentication and hotplug behavior.
- **Acceptance IDs:** `KHAHP-38.02A`, `KHAHP-38.02B`, `KHAHP-38.02C` — **OPEN / NOT SIGNED OFF**.

#### 38.03 — Bluetooth/rfkill interaction with peripherals

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of bluetooth/rfkill interaction with peripherals; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Prove actual idle lock, lid/suspend/resume authentication and hotplug behavior.
- **Acceptance IDs:** `KHAHP-38.03A`, `KHAHP-38.03B`, `KHAHP-38.03C` — **OPEN / NOT SIGNED OFF**.

#### 38.04 — Screen-lock timeout and authentication

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of screen-lock timeout and authentication; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Prove actual idle lock, lid/suspend/resume authentication and hotplug behavior.
- **Acceptance IDs:** `KHAHP-38.04A`, `KHAHP-38.04B`, `KHAHP-38.04C` — **OPEN / NOT SIGNED OFF**.

#### 38.05 — Suspend/lock-on-lid and idle behavior

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of suspend/lock-on-lid and idle behavior; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Prove actual idle lock, lid/suspend/resume authentication and hotplug behavior.
- **Acceptance IDs:** `KHAHP-38.05A`, `KHAHP-38.05B`, `KHAHP-38.05C` — **OPEN / NOT SIGNED OFF**.

#### 38.06 — Hibernation configuration and encrypted-swap implications

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of hibernation configuration and encrypted-swap implications; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Prove actual idle lock, lid/suspend/resume authentication and hotplug behavior.
- **Acceptance IDs:** `KHAHP-38.06A`, `KHAHP-38.06B`, `KHAHP-38.06C` — **OPEN / NOT SIGNED OFF**.

#### 38.07 — Shutdown-versus-suspend operational policy

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of shutdown-versus-suspend operational policy; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Prove actual idle lock, lid/suspend/resume authentication and hotplug behavior.
- **Acceptance IDs:** `KHAHP-38.07A`, `KHAHP-38.07B`, `KHAHP-38.07C` — **OPEN / NOT SIGNED OFF**.


### Section 39: Firmware / BIOS / Secure Boot / TPM

#### 39.01 — BIOS/UEFI vendor, model and firmware version

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of bios/uefi vendor, model and firmware version; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Owner-controlled firmware/DMA/boot policy inspection; no blind MOK re-enrollment.
- **Acceptance IDs:** `KHAHP-39.01A`, `KHAHP-39.01B`, `KHAHP-39.01C` — **OPEN / NOT SIGNED OFF**.

#### 39.02 — fwupd device/security-attribute inventory

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of fwupd device/security-attribute inventory; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Owner-controlled firmware/DMA/boot policy inspection; no blind MOK re-enrollment.
- **Acceptance IDs:** `KHAHP-39.02A`, `KHAHP-39.02B`, `KHAHP-39.02C` — **OPEN / NOT SIGNED OFF**.

#### 39.03 — Secure Boot state and Setup Mode

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of secure boot state and setup mode; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Owner-controlled firmware/DMA/boot policy inspection; no blind MOK re-enrollment.
- **Acceptance IDs:** `KHAHP-39.03A`, `KHAHP-39.03B`, `KHAHP-39.03C` — **OPEN / NOT SIGNED OFF**.

#### 39.04 — TPM presence, version and ownership state

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of tpm presence, version and ownership state; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Owner-controlled firmware/DMA/boot policy inspection; no blind MOK re-enrollment.
- **Acceptance IDs:** `KHAHP-39.04A`, `KHAHP-39.04B`, `KHAHP-39.04C` — **OPEN / NOT SIGNED OFF**.

#### 39.05 — BIOS/UEFI administrator password manual check

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of bios/uefi administrator password manual check; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Owner-controlled firmware/DMA/boot policy inspection; no blind MOK re-enrollment.
- **Acceptance IDs:** `KHAHP-39.05A`, `KHAHP-39.05B`, `KHAHP-39.05C` — **OPEN / NOT SIGNED OFF**.

#### 39.06 — PXE/CSM/external-boot/manual boot- order policy

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of pxe/csm/external-boot/manual boot- order policy; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Owner-controlled firmware/DMA/boot policy inspection; no blind MOK re-enrollment.
- **Acceptance IDs:** `KHAHP-39.06A`, `KHAHP-39.06B`, `KHAHP-39.06C` — **OPEN / NOT SIGNED OFF**.

#### 39.07 — Firmware update, DKMS/MOK and Secure-Boot readiness

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of firmware update, dkms/mok and secure-boot readiness; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Owner-controlled firmware/DMA/boot policy inspection; no blind MOK re-enrollment.
- **Acceptance IDs:** `KHAHP-39.07A`, `KHAHP-39.07B`, `KHAHP-39.07C` — **OPEN / NOT SIGNED OFF**.


### Section 40: Auditd / AIDE / Integrity Monitoring

#### 40.01 — auditd package/service state

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of auditd package/service state; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Verify permitted audit event retrieval, AIDE alert lifecycle and retention; do not reinitialize AIDE.
- **Acceptance IDs:** `KHAHP-40.01A`, `KHAHP-40.01B`, `KHAHP-40.01C` — **OPEN / NOT SIGNED OFF**.

#### 40.02 — Audit rule inventory and immutable/finalize policy

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of audit rule inventory and immutable/finalize policy; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Verify permitted audit event retrieval, AIDE alert lifecycle and retention; do not reinitialize AIDE.
- **Acceptance IDs:** `KHAHP-40.02A`, `KHAHP-40.02B`, `KHAHP-40.02C` — **OPEN / NOT SIGNED OFF**.

#### 40.03 — Privileged-command and identity- change audit coverage

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of privileged-command and identity- change audit coverage; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Verify permitted audit event retrieval, AIDE alert lifecycle and retention; do not reinitialize AIDE.
- **Acceptance IDs:** `KHAHP-40.03A`, `KHAHP-40.03B`, `KHAHP-40.03C` — **OPEN / NOT SIGNED OFF**.

#### 40.04 — AIDE package/database/configuration state

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of aide package/database/configuration state; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Verify permitted audit event retrieval, AIDE alert lifecycle and retention; do not reinitialize AIDE.
- **Acceptance IDs:** `KHAHP-40.04A`, `KHAHP-40.04B`, `KHAHP-40.04C` — **OPEN / NOT SIGNED OFF**.

#### 40.05 — File-integrity baseline and scheduled checks

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of file-integrity baseline and scheduled checks; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Verify permitted audit event retrieval, AIDE alert lifecycle and retention; do not reinitialize AIDE.
- **Acceptance IDs:** `KHAHP-40.05A`, `KHAHP-40.05B`, `KHAHP-40.05C` — **OPEN / NOT SIGNED OFF**.

#### 40.06 — Audit-log ownership, rotation and tamper resistance

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of audit-log ownership, rotation and tamper resistance; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Verify permitted audit event retrieval, AIDE alert lifecycle and retention; do not reinitialize AIDE.
- **Acceptance IDs:** `KHAHP-40.06A`, `KHAHP-40.06B`, `KHAHP-40.06C` — **OPEN / NOT SIGNED OFF**.

#### 40.07 — CIS/DISA accountability-gap analysis

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of cis/disa accountability-gap analysis; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Verify permitted audit event retrieval, AIDE alert lifecycle and retention; do not reinitialize AIDE.
- **Acceptance IDs:** `KHAHP-40.07A`, `KHAHP-40.07B`, `KHAHP-40.07C` — **OPEN / NOT SIGNED OFF**.


### Section 41: Cron / Timers / Persistence / Supply Chain

#### 41.01 — cron/anacron job inventory

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of cron/anacron job inventory; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Establish desktop autostart provenance, signing sources and two-boot drift.
- **Acceptance IDs:** `KHAHP-41.01A`, `KHAHP-41.01B`, `KHAHP-41.01C` — **OPEN / NOT SIGNED OFF**.

#### 41.02 — systemd timer inventory

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of systemd timer inventory; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Establish desktop autostart provenance, signing sources and two-boot drift.
- **Acceptance IDs:** `KHAHP-41.02A`, `KHAHP-41.02B`, `KHAHP-41.02C` — **OPEN / NOT SIGNED OFF**.

#### 41.03 — User autostart and desktop persistence inventory

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of user autostart and desktop persistence inventory; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Establish desktop autostart provenance, signing sources and two-boot drift.
- **Acceptance IDs:** `KHAHP-41.03A`, `KHAHP-41.03B`, `KHAHP-41.03C` — **OPEN / NOT SIGNED OFF**.

#### 41.04 — Package repository and signing-key provenance

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of package repository and signing-key provenance; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Establish desktop autostart provenance, signing sources and two-boot drift.
- **Acceptance IDs:** `KHAHP-41.04A`, `KHAHP-41.04B`, `KHAHP-41.04C` — **OPEN / NOT SIGNED OFF**.

#### 41.05 — APT pinning/holds and update-policy review

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of apt pinning/holds and update-policy review; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Establish desktop autostart provenance, signing sources and two-boot drift.
- **Acceptance IDs:** `KHAHP-41.05A`, `KHAHP-41.05B`, `KHAHP-41.05C` — **OPEN / NOT SIGNED OFF**.

#### 41.06 — Unexpected startup scripts/services/modules

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of unexpected startup scripts/services/modules; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Establish desktop autostart provenance, signing sources and two-boot drift.
- **Acceptance IDs:** `KHAHP-41.06A`, `KHAHP-41.06B`, `KHAHP-41.06C` — **OPEN / NOT SIGNED OFF**.

#### 41.07 — Supply-chain drift and reboot- persistence evidence

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of supply-chain drift and reboot- persistence evidence; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Establish desktop autostart provenance, signing sources and two-boot drift.
- **Acceptance IDs:** `KHAHP-41.07A`, `KHAHP-41.07B`, `KHAHP-41.07C` — **OPEN / NOT SIGNED OFF**.


### Section 42: Credentials / SSH Keys / Secrets / Backup

#### 42.01 — SSH private-key inventory and permissions

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of ssh private-key inventory and permissions; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Complete actual encrypted backup, isolated restore and release-secret exclusion.
- **Acceptance IDs:** `KHAHP-42.01A`, `KHAHP-42.01B`, `KHAHP-42.01C` — **OPEN / NOT SIGNED OFF**.

#### 42.02 — API/token/secret storage locations

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of api/token/secret storage locations; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Complete actual encrypted backup, isolated restore and release-secret exclusion.
- **Acceptance IDs:** `KHAHP-42.02A`, `KHAHP-42.02B`, `KHAHP-42.02C` — **OPEN / NOT SIGNED OFF**.

#### 42.03 — Password-manager selection and vault policy

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of password-manager selection and vault policy; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Complete actual encrypted backup, isolated restore and release-secret exclusion.
- **Acceptance IDs:** `KHAHP-42.03A`, `KHAHP-42.03B`, `KHAHP-42.03C` — **OPEN / NOT SIGNED OFF**.

#### 42.04 — FIDO2/YubiKey readiness and hardware-backed keys

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of fido2/yubikey readiness and hardware-backed keys; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Complete actual encrypted backup, isolated restore and release-secret exclusion.
- **Acceptance IDs:** `KHAHP-42.04A`, `KHAHP-42.04B`, `KHAHP-42.04C` — **OPEN / NOT SIGNED OFF**.

#### 42.05 — Recovery-code generation and offline storage

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of recovery-code generation and offline storage; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Complete actual encrypted backup, isolated restore and release-secret exclusion.
- **Acceptance IDs:** `KHAHP-42.05A`, `KHAHP-42.05B`, `KHAHP-42.05C` — **OPEN / NOT SIGNED OFF**.

#### 42.06 — Encrypted backup creation and retention

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of encrypted backup creation and retention; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Complete actual encrypted backup, isolated restore and release-secret exclusion.
- **Acceptance IDs:** `KHAHP-42.06A`, `KHAHP-42.06B`, `KHAHP-42.06C` — **OPEN / NOT SIGNED OFF**.

#### 42.07 — Restore test, key recovery and disaster-recovery evidence

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of restore test, key recovery and disaster-recovery evidence; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Complete actual encrypted backup, isolated restore and release-secret exclusion.
- **Acceptance IDs:** `KHAHP-42.07A`, `KHAHP-42.07B`, `KHAHP-42.07C` — **OPEN / NOT SIGNED OFF**.


### Section 43: CIS / DISA GPOS / KSPP Mapping

#### 43.01 — CIS Debian 13 Level 2 applicability mapping

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of cis debian 13 level 2 applicability mapping; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm applicability and source mapping one by one; no certification claim.
- **Acceptance IDs:** `KHAHP-43.01A`, `KHAHP-43.01B`, `KHAHP-43.01C` — **OPEN / NOT SIGNED OFF**.

#### 43.02 — DISA GPOS/SRG objective mapping

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of disa gpos/srg objective mapping; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm applicability and source mapping one by one; no certification claim.
- **Acceptance IDs:** `KHAHP-43.02A`, `KHAHP-43.02B`, `KHAHP-43.02C` — **OPEN / NOT SIGNED OFF**.

#### 43.03 — KSPP/kernel-self-protection mapping

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of kspp/kernel-self-protection mapping; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm applicability and source mapping one by one; no certification claim.
- **Acceptance IDs:** `KHAHP-43.03A`, `KHAHP-43.03B`, `KHAHP-43.03C` — **OPEN / NOT SIGNED OFF**.

#### 43.04 — Kicksecure-native equivalent control mapping

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of kicksecure-native equivalent control mapping; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm applicability and source mapping one by one; no certification claim.
- **Acceptance IDs:** `KHAHP-43.04A`, `KHAHP-43.04B`, `KHAHP-43.04C` — **OPEN / NOT SIGNED OFF**.

#### 43.05 — Project-extension control mapping

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of project-extension control mapping; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm applicability and source mapping one by one; no certification claim.
- **Acceptance IDs:** `KHAHP-43.05A`, `KHAHP-43.05B`, `KHAHP-43.05C` — **OPEN / NOT SIGNED OFF**.

#### 43.06 — Exception/N-A/manual-control rationale

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of exception/n-a/manual-control rationale; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm applicability and source mapping one by one; no certification claim.
- **Acceptance IDs:** `KHAHP-43.06A`, `KHAHP-43.06B`, `KHAHP-43.06C` — **OPEN / NOT SIGNED OFF**.

#### 43.07 — Evidence citation and no-certification disclaimer

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of evidence citation and no-certification disclaimer; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Confirm applicability and source mapping one by one; no certification claim.
- **Acceptance IDs:** `KHAHP-43.07A`, `KHAHP-43.07B`, `KHAHP-43.07C` — **OPEN / NOT SIGNED OFF**.


### Section 44: Final Acceptance / Evidence / Scoring

#### 44.01 — Full reboot persistence acceptance

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of full reboot persistence acceptance; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Complete two-role/two-boot regressions, negative tests, recovery and final owner sign-off.
- **Acceptance IDs:** `KHAHP-44.01A`, `KHAHP-44.01B`, `KHAHP-44.01C` — **OPEN / NOT SIGNED OFF**.

#### 44.02 — USER-mode regression acceptance

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of user-mode regression acceptance; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Complete two-role/two-boot regressions, negative tests, recovery and final owner sign-off.
- **Acceptance IDs:** `KHAHP-44.02A`, `KHAHP-44.02B`, `KHAHP-44.02C` — **OPEN / NOT SIGNED OFF**.

#### 44.03 — SYSMAINT-mode regression acceptance

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of sysmaint-mode regression acceptance; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Complete two-role/two-boot regressions, negative tests, recovery and final owner sign-off.
- **Acceptance IDs:** `KHAHP-44.03A`, `KHAHP-44.03B`, `KHAHP-44.03C` — **OPEN / NOT SIGNED OFF**.

#### 44.04 — Network/DNS/firewall/Tor/USB negative-test acceptance

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of network/dns/firewall/tor/usb negative-test acceptance; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Complete two-role/two-boot regressions, negative tests, recovery and final owner sign-off.
- **Acceptance IDs:** `KHAHP-44.04A`, `KHAHP-44.04B`, `KHAHP-44.04C` — **OPEN / NOT SIGNED OFF**.

#### 44.05 — Recovery/rollback/backup acceptance

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of recovery/rollback/backup acceptance; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Complete two-role/two-boot regressions, negative tests, recovery and final owner sign-off.
- **Acceptance IDs:** `KHAHP-44.05A`, `KHAHP-44.05B`, `KHAHP-44.05C` — **OPEN / NOT SIGNED OFF**.

#### 44.06 — Evidence completeness, hashes and chain-of-custody bundle

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of evidence completeness, hashes and chain-of-custody bundle; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Complete two-role/two-boot regressions, negative tests, recovery and final owner sign-off.
- **Acceptance IDs:** `KHAHP-44.06A`, `KHAHP-44.06B`, `KHAHP-44.06C` — **OPEN / NOT SIGNED OFF**.

#### 44.07 — Final scorecard, residual risk and operator sign-off

- **Evidence status:** Provisional historical research, no current target-run acceptance.
- **Link to tracked findings:** Section-level review, original private dossier; no family-specific defect inferred.
- **Required A/B/C evidence:** Provenance of final scorecard, residual risk and operator sign-off; effective behavior in applicable boot role; controlled persistence/negative/recovery evidence or written exception.
- **Unresolved section-level work:** Complete two-role/two-boot regressions, negative tests, recovery and final owner sign-off.
- **Acceptance IDs:** `KHAHP-44.07A`, `KHAHP-44.07B`, `KHAHP-44.07C` — **OPEN / NOT SIGNED OFF**.


## 9. Future implementation and evidence publication process

| Stage | Required evidence | Safety/approval gate |
|---|---|---|
| 1. Triage | Proven observation, family ID and actual threat | Separate confirmed defect from test-only, enhancement and exception |
| 2. Ownership | Package/source provenance and USER/SYSMAINT scope | No blind changes to vendor-managed policy |
| 3. Design | Minimal configuration delta, dependency analysis, diff | Written approval; impact and recovery plan |
| 4. QA | Offline parser/syntax tests and isolated compatibility tests | No mutation of production laptop during design |
| 5. Apply | Pinned version/hash, role verification, backed-up original | Only explicitly authorized targeted change |
| 6. Runtime B | Positive and appropriate authorized negative tests | Retain only sanitized public summary |
| 7. Persistence C | Reboot/reconnect/upgrade and recovery checks | Do not close from source presence alone |
| 8. Closure | Reviewed A/B/C evidence, exceptions and reviewer | Final owner acceptance and documented residual risk |

**Production safety policies:** Preserve built-in input and recovery access before USBGuard changes; do not interrupt Unbound/nftables/Tor as a casual probe; prohibit arbitrary external DNS targets; use a disposable VM for destructive clock/boot or panic experiments; do not reinitialize AIDE baseline; do not share private backup/recovery secrets.

## 10. Proposed commercial-image release test suite — 60 tests

**All 60 tests below remain PROPOSED / NOT EXECUTED.** They provide release requirements, not evidence of a product already passing or being distributed.

### Clean-image common release requirements (20 tests)

| Test ID | Planned test | Gate status |
|---|---|---|
| `KHAHP-REL-COM-01` | Reproducible upstream source | NOT TESTED |
| `KHAHP-REL-COM-02` | Package provenance | NOT TESTED |
| `KHAHP-REL-COM-03` | Build isolation | NOT TESTED |
| `KHAHP-REL-COM-04` | Credential exclusion | NOT TESTED |
| `KHAHP-REL-COM-05` | Unique machine identity | NOT TESTED |
| `KHAHP-REL-COM-06` | Unique SSH host keys | NOT TESTED |
| `KHAHP-REL-COM-07` | SSH access policy | NOT TESTED |
| `KHAHP-REL-COM-08` | Privileges and boot-role separation | NOT TESTED |
| `KHAHP-REL-COM-09` | Default firewall | NOT TESTED |
| `KHAHP-REL-COM-10` | DNS resolver protection | NOT TESTED |
| `KHAHP-REL-COM-11` | Network privacy behavior | NOT TESTED |
| `KHAHP-REL-COM-12` | MAC and device privacy | NOT TESTED |
| `KHAHP-REL-COM-13` | Mandatory access controls | NOT TESTED |
| `KHAHP-REL-COM-14` | Kernel hardening | NOT TESTED |
| `KHAHP-REL-COM-15` | Audit visibility | NOT TESTED |
| `KHAHP-REL-COM-16` | File integrity monitoring | NOT TESTED |
| `KHAHP-REL-COM-17` | Upgrade safety | NOT TESTED |
| `KHAHP-REL-COM-18` | Backup and restoration | NOT TESTED |
| `KHAHP-REL-COM-19` | Release signing | NOT TESTED |
| `KHAHP-REL-COM-20` | Customer documentation and licensing | NOT TESTED |

### Physical ISO / USB release requirements (20 tests)

| Test ID | Planned test | Gate status |
|---|---|---|
| `KHAHP-REL-ISO-01` | UEFI USB boot | NOT TESTED |
| `KHAHP-REL-ISO-02` | Installer storage detection | NOT TESTED |
| `KHAHP-REL-ISO-03` | Fresh encrypted installation | NOT TESTED |
| `KHAHP-REL-ISO-04` | Encryption recovery | NOT TESTED |
| `KHAHP-REL-ISO-05` | Secure Boot enrollment | NOT TESTED |
| `KHAHP-REL-ISO-06` | Firmware Setup Mode | NOT TESTED |
| `KHAHP-REL-ISO-07` | TPM optional path | NOT TESTED |
| `KHAHP-REL-ISO-08` | Intel and AMD support | NOT TESTED |
| `KHAHP-REL-ISO-09` | Graphics and desktop | NOT TESTED |
| `KHAHP-REL-ISO-10` | Wireless networking | NOT TESTED |
| `KHAHP-REL-ISO-11` | Ethernet and hotplug | NOT TESTED |
| `KHAHP-REL-ISO-12` | USBGuard defaults | NOT TESTED |
| `KHAHP-REL-ISO-13` | Installer device safety | NOT TESTED |
| `KHAHP-REL-ISO-14` | DMA/IOMMU capabilities | NOT TESTED |
| `KHAHP-REL-ISO-15` | Signed module lifecycle | NOT TESTED |
| `KHAHP-REL-ISO-16` | Physical webcam/microphone | NOT TESTED |
| `KHAHP-REL-ISO-17` | Power and RAM-wipe process | NOT TESTED |
| `KHAHP-REL-ISO-18` | BIOS recovery restrictions | NOT TESTED |
| `KHAHP-REL-ISO-19` | Multi-boot/firmware resilience | NOT TESTED |
| `KHAHP-REL-ISO-20` | Fresh-install two-device comparison | NOT TESTED |

### KVM / QCOW2 requirements (10 tests)

| Test ID | Planned test | Gate status |
|---|---|---|
| `KHAHP-REL-KVM-01` | QCOW2 import and boot | NOT TESTED |
| `KHAHP-REL-KVM-02` | Fresh clone identity | NOT TESTED |
| `KHAHP-REL-KVM-03` | Virtual firmware choice | NOT TESTED |
| `KHAHP-REL-KVM-04` | Virtual TPM support | NOT TESTED |
| `KHAHP-REL-KVM-05` | Host-guest firewall isolation | NOT TESTED |
| `KHAHP-REL-KVM-06` | Guest disk encryption | NOT TESTED |
| `KHAHP-REL-KVM-07` | Virtio device support | NOT TESTED |
| `KHAHP-REL-KVM-08` | KVM snapshot and restore | NOT TESTED |
| `KHAHP-REL-KVM-09` | KVM version regression | NOT TESTED |
| `KHAHP-REL-KVM-10` | QCOW2 sanitized release | NOT TESTED |

### VirtualBox / OVA requirements (10 tests)

| Test ID | Planned test | Gate status |
|---|---|---|
| `KHAHP-REL-OVA-01` | OVA packaging and import | NOT TESTED |
| `KHAHP-REL-OVA-02` | Unique identity on import | NOT TESTED |
| `KHAHP-REL-OVA-03` | Clipboard and drag-drop | NOT TESTED |
| `KHAHP-REL-OVA-04` | Shared-folder isolation | NOT TESTED |
| `KHAHP-REL-OVA-05` | USB passthrough restriction | NOT TESTED |
| `KHAHP-REL-OVA-06` | VirtualBox networking | NOT TESTED |
| `KHAHP-REL-OVA-07` | Guest addition safety | NOT TESTED |
| `KHAHP-REL-OVA-08` | Virtual disk recovery | NOT TESTED |
| `KHAHP-REL-OVA-09` | Supported host matrix | NOT TESTED |
| `KHAHP-REL-OVA-10` | OVA clean release gate | NOT TESTED |

## 11. Open challenge: requirements for an independently credible submission

Researchers are invited to submit a **threat model, OS/package provenance, tested security deltas, enforcement and non-enforcement results, negative tests, reboot/update persistence, recovery results and justified exceptions**. Screenshots or claimed hardening scores alone are insufficient. Reproduce tests in systems you own or are explicitly authorized to assess. Avoid exploitation of third-party infrastructure and avoid publishing sensitive identifiers or private data.

**No unsupported ranking:** KHAHP does not claim the strongest OS in the world, perfect anonymity, official CIS/DISA certification, universal device compatibility, or a completed Premium Hardened OS release. The product is proposed at **USD $1,250**, subject to proper release acceptance.

## 12. Source bibliography, limits and next-document revision

- **Public upstream:** `elite-cybersecurity-specialist/hardening-challenge` historical README and 308-family register, originally derived from a dated challenge PDF.
- **Private baseline A:** Sections 01–14 Technical Dossier v1.0, historical Oct 12–15 inspections and documented narrow temporary-filesystem change.
- **Private baseline B:** Sections 15–24 Technical Dossier v1.0 and 22-item follow-up tracker; original raw source collection only partially embedded in release.
- **Private baseline C:** Sections 25–34 Technical Documentation v1.0, reconciled 520 historical observations, updated v6.1 USER/SYSMAINT/LAN records and 23-item issue register.
- **Provisional baseline D:** Sections 35–44 Grand Verifier v1.0 QA Review and historical reconciliation. Offline QA is not a live target run. No completed Section 44 result is claimed.
- **Private custody:** Original checksummed reports, machine-specific configurations, exact hashes, operator observations, and recovery evidence are withheld from the public publication unless independently sanitized and approved.

**Next revision trigger:** When Sections 35–44 have real USER/SYSMAINT evidence, controlled manual/negative tests, actual encrypted backup/restore evidence, source-to-runtime reconciliations and sign-off decisions, issue a new reviewed release. Update Sections 01–34 if their operational state changes. Preserve historical public revisions in Git history.

**Public contact:** ELITE CYBERSECURITY SPECIALIST · Malaysia · [GitHub project repository](https://github.com/elite-cybersecurity-specialist/hardening-challenge).

---

*Copyright and third-party notices:* Kicksecure, Debian, CIS, DISA and other third-party tools and references remain subject to their respective license, trademark and usage terms. A license for original KHAHP publication content should be separately specified by the owner; none is implied by publication.
