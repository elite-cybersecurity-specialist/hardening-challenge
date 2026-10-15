# KHAHP — Full Technical Hardening and Verification Register

**Source:** `CYBERSECURITY-CHALLENGE.pdf`, *KHAHP Master Implementation & Evidence Challenge*, version 1.6, 15 October 2026 (107 pages). Converted into GitHub Markdown while retaining the technical family/checkpoint terminology and source-report references.

**Company:** ELITE CYBERSECURITY SPECIALIST · Malaysia · 202403184091 (MA0319303-P)  
**Project architect:** Yuhisern Navaratnam · Cybersecurity Engineer  
**Project:** Kicksecure High-Assurance Hardening Project (KHAHP) · **Open Cybersecurity Hardening Challenge**  
**Engineering effort:** Over 120 hours and counting  
**Project stage:** Ongoing implementation and acceptance

> This register documents **security weakness and hardening checkpoints**, not 984 demonstrated exploitable bugs or an already completed implementation. Historical evidence is retained as reported; any unverified state remains unverified. The final commercial release tests are proposals, not completed tests.

[← Return to repository overview](README.md)

## Project rationale and challenge

KHAHP demonstrates systematic OS security engineering: identify attack surfaces, document vulnerabilities and hardening opportunities, preserve controls already enforced, remediate confirmed gaps and test the effectiveness and persistence of every applicable protection. The project invites other cybersecurity specialists to demonstrate stronger, more reproducible results under transparent test constraints.

**Why Kicksecure:** Its Debian-based, security-oriented architecture and USER/SYSMAINT separation provide a promising base for deep kernel restrictions, mandatory access control, network privacy, audits, integrity monitoring and disciplined recovery. Anonymity and data confidentiality still depend on deployment-specific configuration and operational practices.

**Standards orientation:** CIS Debian Linux 13 Level 2 Workstation, STIG-oriented benchmark references, applicable DISA GPOS SRG objectives and KSPP. These references are **not claims of official certification**.

**Measurement:** 44 × 7 families × 3 A/B/C checks = **924 core checkpoints**, plus 60 commercial-release tests = **984 planned checks**.

## Implementation stage map

| Stage | Focus | Sections |
|:--|:--|:--|
| S0 | Safety and controlled change | Prerequisite |
| S1 | Application confinement and filesystem exposure | 15, 17, 37 |
| S2 | Disk, boot, kernel, firmware and memory | 06–14, 24–25, 39 |
| S3 | Accounts, privileges, services and peripherals | 01–05, 16, 18–23, 26, 38 |
| S4 | Network, DNS, firewall, Tor and browser privacy | 27–36 |
| S5 | Audit, integrity and persistence | 40–41 |
| S6 | Secrets, backup and restore | 42 |
| S7 | CIS / STIG-oriented / KSPP evidence closure | 43 |
| S8 | Final acceptance and sign-off | 44 |
| R0–R3 | Commercial release — clean-image common, physical ISO, QCOW2 and OVA | 60 tests |

## Core register — 44 categories / 924 checkpoints

For each family, the **A/B/C checkpoints** are tracked separately: **A** configuration/provenance, **B** runtime enforcement, and **C** persistence/negative/recovery. The source report references are archive filenames, not URLs to a public evidence archive.

## 01 — Platform / OS / Hardware Baseline

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 01.01 — Operating-system identity and Debian/Kicksecure release baseline

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-01.01A`, `KHAHP-01.01B`, `KHAHP-01.01C`

**Source / evidence status:** 01-platform-baseline-20261012-094204.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

### 01.02 — Kernel release, architecture and build identity

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-01.02A`, `KHAHP-01.02B`, `KHAHP-01.02C`

**Source / evidence status:** 01-platform-baseline-20261012-094204.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

### 01.03 — CPU model, topology and virtualization capability

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-01.03A`, `KHAHP-01.03B`, `KHAHP-01.03C`

**Source / evidence status:** 01-platform-baseline-20261012-094204.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

### 01.04 — Physical memory and swap capacity baseline

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-01.04A`, `KHAHP-01.04B`, `KHAHP-01.04C`

**Source / evidence status:** 01-platform-baseline-20261012-094204.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

### 01.05 — Storage controller, disk and filesystem topology

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-01.05A`, `KHAHP-01.05B`, `KHAHP-01.05C`

**Source / evidence status:** 01-platform-baseline-20261012-094204.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

### 01.06 — UEFI/bare-metal/virtualization platform state

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-01.06A`, `KHAHP-01.06B`, `KHAHP-01.06C`

**Source / evidence status:** 01-platform-baseline-20261012-094204.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

### 01.07 — Failed-unit, uptime, boot-time and baseline health state

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-01.07A`, `KHAHP-01.07B`, `KHAHP-01.07C`

**Source / evidence status:** 01-platform-baseline-20261012-094204.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

---

## 02 — Kicksecure Package Provenance

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 02.01 — Core Kicksecure package installation and exact versions

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-02.01A`, `KHAHP-02.01B`, `KHAHP-02.01C`

**Source / evidence status:** 02-kicksecure-package-provenance-20261012-115518.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

### 02.02 — Supporting security-package installation and exact versions

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-02.02A`, `KHAHP-02.02B`, `KHAHP-02.02C`

**Source / evidence status:** 02-kicksecure-package-provenance-20261012-115518.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

### 02.03 — APT source files and repository configuration

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-02.03A`, `KHAHP-02.03B`, `KHAHP-02.03C`

**Source / evidence status:** 02-kicksecure-package-provenance-20261012-115518.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

### 02.04 — APT policy and repository origin attribution

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-02.04A`, `KHAHP-02.04B`, `KHAHP-02.04C`

**Source / evidence status:** 02-kicksecure-package-provenance-20261012-115518.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

### 02.05 — Package ownership of security-critical configuration files

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-02.05A`, `KHAHP-02.05B`, `KHAHP-02.05C`

**Source / evidence status:** 02-kicksecure-package-provenance-20261012-115518.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

### 02.06 — Package holds, partial installs and dpkg database health

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-02.06A`, `KHAHP-02.06B`, `KHAHP-02.06C`

**Source / evidence status:** 02-kicksecure-package-provenance-20261012-115518.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

### 02.07 — Local modifications versus package-owned baseline

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-02.07A`, `KHAHP-02.07B`, `KHAHP-02.07C`

**Source / evidence status:** 02-kicksecure-package-provenance-20261012-115518.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

---

## 03 — USER / SYSMAINT Privilege Architecture

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 03.01 — USER, SYSMAINT and root account separation

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-03.01A`, `KHAHP-03.01B`, `KHAHP-03.01C`

**Source / evidence status:** 03-user-sysmaint-privilege-architecture-20261012-125417.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

### 03.02 — Distinct UID/GID and home-directory boundaries

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-03.02A`, `KHAHP-03.02B`, `KHAHP-03.02C`

**Source / evidence status:** 03-user-sysmaint-privilege-architecture-20261012-125417.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

### 03.03 — user-sysmaint-split package and owned policy files

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-03.03A`, `KHAHP-03.03B`, `KHAHP-03.03C`

**Source / evidence status:** 03-user-sysmaint-privilege-architecture-20261012-125417.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

### 03.04 — sudo binary ownership, mode and SYSMAINT-only execution

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-03.04A`, `KHAHP-03.04B`, `KHAHP-03.04C`

**Source / evidence status:** 03-user-sysmaint-privilege-architecture-20261012-125417.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

### 03.05 — sudoers syntax and user-sysmaint- split policy

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-03.05A`, `KHAHP-03.05B`, `KHAHP-03.05C`

**Source / evidence status:** 03-user-sysmaint-privilege-architecture-20261012-125417.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

### 03.06 — USER negative sudo/root acquisition probe

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-03.06A`, `KHAHP-03.06B`, `KHAHP-03.06C`

**Source / evidence status:** 03-user-sysmaint-privilege-architecture-20261012-125417.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

### 03.07 — Login-shell and boot-role separation behavior

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-03.07A`, `KHAHP-03.07B`, `KHAHP-03.07C`

**Source / evidence status:** 03-user-sysmaint-privilege-architecture-20261012-125417.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

---

## 04 — SYSMAINT Target / Boot Role

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 04.01 — boot-role=sysmaint kernel marker

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-04.01A`, `KHAHP-04.01B`, `KHAHP-04.01C`

**Source / evidence status:** 04-sysmaint-target-boot-role-20261012-124800.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

### 04.02 — systemd.unit=sysmaint-boot.target marker

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-04.02A`, `KHAHP-04.02B`, `KHAHP-04.02C`

**Source / evidence status:** 04-sysmaint-target-boot-role-20261012-124800.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

### 04.03 — sysmaint-boot.target package provenance and unit content

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-04.03A`, `KHAHP-04.03B`, `KHAHP-04.03C`

**Source / evidence status:** 04-sysmaint-target-boot-role-20261012-124800.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

### 04.04 — Required SYSMAINT dependencies and wanted units

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-04.04A`, `KHAHP-04.04B`, `KHAHP-04.04C`

**Source / evidence status:** 04-sysmaint-target-boot-role-20261012-124800.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

### 04.05 — Intentionally omitted USER-only or incompatible hardeners

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-04.05A`, `KHAHP-04.05B`, `KHAHP-04.05C`

**Source / evidence status:** 04-sysmaint-target-boot-role-20261012-124800.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

### 04.06 — Conflicting USER/graphical boot-role negative checks

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-04.06A`, `KHAHP-04.06B`, `KHAHP-04.06C`

**Source / evidence status:** 04-sysmaint-target-boot-role-20261012-124800.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

### 04.07 — Failed units and SYSMAINT boot health

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-04.07A`, `KHAHP-04.07B`, `KHAHP-04.07C`

**Source / evidence status:** 04-sysmaint-target-boot-role-20261012-124800.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

---

## 05 — Accounts / UID / GID / Local Identity

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 05.01 — root, USER and SYSMAINT account identity

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-05.01A`, `KHAHP-05.01B`, `KHAHP-05.01C`

**Source / evidence status:** 05-accounts-uid-gid-local-identity-20261012-130203.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

### 05.02 — Duplicate UID and duplicate GID detection

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-05.02A`, `KHAHP-05.02B`, `KHAHP-05.02C`

**Source / evidence status:** 05-accounts-uid-gid-local-identity-20261012-130203.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

### 05.03 — UID 0 exclusivity and privileged- account review

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-05.03A`, `KHAHP-05.03B`, `KHAHP-05.03C`

**Source / evidence status:** 05-accounts-uid-gid-local-identity-20261012-130203.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

### 05.04 — Low-UID service-account shell classification

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-05.04A`, `KHAHP-05.04B`, `KHAHP-05.04C`

**Source / evidence status:** 05-accounts-uid-gid-local-identity-20261012-130203.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

### 05.05 — Home-directory ownership and permissions

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-05.05A`, `KHAHP-05.05B`, `KHAHP-05.05C`

**Source / evidence status:** 05-accounts-uid-gid-local-identity-20261012-130203.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

### 05.06 — shadow/gshadow/passwd/group ownership and modes

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-05.06A`, `KHAHP-05.06B`, `KHAHP-05.06C`

**Source / evidence status:** 05-accounts-uid-gid-local-identity-20261012-130203.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

### 05.07 — NSS identity source configuration and root lock state

**Stage / source classification:** `S3 / P2`

**Historical evidence:** Positive observations identified in original report; family-specific A/B/C sign-off not demonstrated by aggregate review.

**Identified weakness / gap:** Specific assertion acceptance is not documented.

**Implementation task:** Preserve recorded protections and link A/B/C evidence to the report before sign-off.

**Core checkpoints:** `KHAHP-05.07A`, `KHAHP-05.07B`, `KHAHP-05.07C`

**Source / evidence status:** 05-accounts-uid-gid-local-identity-20261012-130203.txt | HISTORICAL EVIDENCE REVIEWED; NO PATCH DEMONSTRATED

---

## 06 — LUKS / Disk / Swap Encryption

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 06.01 — Root filesystem source and dm-crypt mapping

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Runtime demonstrated: / is ext4 over /dev/mapper/luks-…; root source resolves to dm-crypt.

**Identified weakness / gap:** No patch shown necessary; confirm unchanged at image installation.

**Implementation task:** No patch shown necessary; confirm unchanged at image installation.

**Core checkpoints:** `KHAHP-06.01A`, `KHAHP-06.01B`, `KHAHP-06.01C`

**Source / evidence status:** 06-luks-disk-swap-encryption-20261012-133453.txt | Runtime demonstrated

### 06.02 — LUKS2 backing partition and cryptsetup status

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Runtime demonstrated: Active cryptsetup mapping reports LUKS2, aes-xts-plain64 and backing partition of crypto_LUKS type.

**Identified weakness / gap:** Preserve mapping; no keyslot changes from this evidence.

**Implementation task:** Preserve mapping; no keyslot changes from this evidence.

**Core checkpoints:** `KHAHP-06.02A`, `KHAHP-06.02B`, `KHAHP-06.02C`

**Source / evidence status:** 06-luks-disk-swap-encryption-20261012-133453.txt | Runtime demonstrated

### 06.03 — LUKS header metadata without key- material disclosure

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Metadata demonstrated: LUKS header Version 2 and cipher read; keyslot/token/digest material withheld.

**Identified weakness / gap:** Passphrase quality, key custody and recovery remain untested, not assumed passed.

**Implementation task:** Passphrase quality, key custody and recovery remain untested, not assumed passed.

**Core checkpoints:** `KHAHP-06.03A`, `KHAHP-06.03B`, `KHAHP-06.03C`

**Source / evidence status:** 06-luks-disk-swap-encryption-20261012-133453.txt | Metadata demonstrated

### 06.04 — Root encryption chain from block device to mountpoint

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Runtime demonstrated: Report records backing partition →dm-crypt mapper →/ and marks chain PASS.

**Identified weakness / gap:** No correction indicated.

**Implementation task:** No correction indicated.

**Core checkpoints:** `KHAHP-06.04A`, `KHAHP-06.04B`, `KHAHP-06.04C`

**Source / evidence status:** 06-luks-disk-swap-encryption-20261012-133453.txt | Runtime demonstrated

### 06.05 — Active swap inventory and encrypted placement

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Runtime demonstrated: Active /var/swapfile under the encrypted root; no unencrypted active swap discovered.

**Identified weakness / gap:** No correction indicated for present swap placement.

**Implementation task:** No correction indicated for present swap placement.

**Core checkpoints:** `KHAHP-06.05A`, `KHAHP-06.05B`, `KHAHP-06.05C`

**Source / evidence status:** 06-luks-disk-swap-encryption-20261012-133453.txt | Runtime demonstrated

### 06.06 — swapfile ownership, mode and containing filesystem

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Runtime demonstrated: /var/swapfile is root:root 0600 and located on encrypted ext4 root.

**Identified weakness / gap:** No permission or storage patch indicated.

**Implementation task:** No permission or storage patch indicated.

**Core checkpoints:** `KHAHP-06.06A`, `KHAHP-06.06B`, `KHAHP-06.06C`

**Source / evidence status:** 06-luks-disk-swap-encryption-20261012-133453.txt | Runtime demonstrated

### 06.07 — crypttab/fstab encryption persistence and boot mapping

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Configuration demonstrated; recovery not tested: crypttab maps LUKS UUID; fstab mounts encrypted mapper at /.

**Identified weakness / gap:** Normal-boot recovery/key-restoration effectiveness not tested in this report; do not modify mapping blindly.

**Implementation task:** Normal-boot recovery/key-restoration effectiveness not tested in this report; do not modify mapping blindly.

**Core checkpoints:** `KHAHP-06.07A`, `KHAHP-06.07B`, `KHAHP-06.07C`

**Source / evidence status:** 06-luks-disk-swap-encryption-20261012-133453.txt | Configuration demonstrated; recovery not tested

---

## 07 — Filesystem / Mount Security

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 07.01 — Effective mount table and filesystem inventory

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Inventory demonstrated: Mounted filesystem table and disk usage recorded.

**Identified weakness / gap:** Mount capture does not itself establish all security options.

**Implementation task:** Mount capture does not itself establish all security options.

**Core checkpoints:** `KHAHP-07.01A`, `KHAHP-07.01B`, `KHAHP-07.01C`

**Source / evidence status:** 07-filesystem-mount-security-20261012-134148.txt | Inventory demonstrated

### 07.02 — Root mount source, filesystem and options

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Runtime demonstrated; policy review: Root is encrypted ext4 with rw,relatime; root not nodev/nosuid.

**Identified weakness / gap:** Root generally needs device and setuid semantics; do not add flags to / indiscriminately.

**Implementation task:** Root generally needs device and setuid semantics; do not add flags to / indiscriminately.

**Core checkpoints:** `KHAHP-07.02A`, `KHAHP-07.02B`, `KHAHP-07.02C`

**Source / evidence status:** 07-filesystem-mount-security-20261012-134148.txt | Runtime demonstrated; policy review

### 07.03 — /boot and /boot/efi separation, ownership and exposure

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Runtime demonstrated; integrity limitation: Separate ext4 /boot and FAT EFI; /boot root:root 0700; /boot/efi 0755.

**Identified weakness / gap:** Review boot-chain trust with Section 39; unencrypted /boot not magically protected by GRUB password.

**Implementation task:** Review boot-chain trust with Section 39; unencrypted /boot not magically protected by GRUB password.

**Core checkpoints:** `KHAHP-07.03A`, `KHAHP-07.03B`, `KHAHP-07.03C`

**Source / evidence status:** 07-filesystem-mount-security-20261012-134148.txt | Runtime demonstrated; integrity limitation

### 07.04 — /tmp tmpfs, sticky bit and mount- option review

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Hardening candidate: /tmp is tmpfs mode 1777 but lacks nodev, nosuid and noexec on runtime mount.

**Identified weakness / gap:** Prioritize compatibility review: nodev/nosuid candidate; noexec only after Kicksecure/installer tests and rollback.

**Implementation task:** Prioritize compatibility review: nodev/nosuid candidate; noexec only after Kicksecure/installer tests and rollback.

**Core checkpoints:** `KHAHP-07.04A`, `KHAHP-07.04B`, `KHAHP-07.04C`

**Source / evidence status:** 07-filesystem-mount-security-20261012-134148.txt | Hardening candidate

### 07.05 — /var/tmp sticky-bit and separate- mount review

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Partition-policy review: /var/tmp is mode 1777 but not a separate mount.

**Identified weakness / gap:** Consider isolating via compatible bind/mount policy if a real threat-model need; no blind repartitioning.

**Implementation task:** Consider isolating via compatible bind/mount policy if a real threat-model need; no blind repartitioning.

**Core checkpoints:** `KHAHP-07.05A`, `KHAHP-07.05B`, `KHAHP-07.05C`

**Source / evidence status:** 07-filesystem-mount-security-20261012-134148.txt | Partition-policy review

### 07.06 — /home containment, ownership and inherited options

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Partition-policy review: /home resides on encrypted root; USER and SYSMAINT home directories are owned by their corresponding accounts, both mode 0750.

**Identified weakness / gap:** Separate /home and nodev/nosuid options remain a design decision; test Kicksecure compatibility before migration.

**Implementation task:** Verify /home account ownership and mode 0750; assess separation and mount options only after Kicksecure compatibility and recovery planning.

**Core checkpoints:** `KHAHP-07.06A`, `KHAHP-07.06B`, `KHAHP-07.06C`

**Source / evidence status:** 07-filesystem-mount-security-20261012-134148.txt | Partition-policy review

### 07.07 — Writable mountpoints, fstab and remount-secure review

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Source present; enforcement incomplete: /tmp fstab entry is explicit; remount-secure.service file present; four reviewed mountpoint directories had no missing sticky bit.

**Identified weakness / gap:** Service presence does not prove activation or effective remounts; assess /dev/shm noexec and mount flags.

**Implementation task:** Service presence does not prove activation or effective remounts; assess /dev/shm noexec and mount flags.

**Core checkpoints:** `KHAHP-07.07A`, `KHAHP-07.07B`, `KHAHP-07.07C`

**Source / evidence status:** 07-filesystem-mount-security-20261012-134148.txt | Source present; enforcement incomplete

---

## 08 — GRUB / Bootloader Protection

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 08.01 — GRUB package baseline and generated grub.cfg

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Configuration demonstrated: GRUB EFI packages installed; /boot/grub/grub.cfg generated and populated.

**Identified weakness / gap:** Installed versions are dated snapshot, not ongoing patch freshness.

**Implementation task:** Installed versions are dated snapshot, not ongoing patch freshness.

**Core checkpoints:** `KHAHP-08.01A`, `KHAHP-08.01B`, `KHAHP-08.01C`

**Source / evidence status:** 08-grub-bootloader-protection-20261012-135756.txt | Configuration demonstrated

### 08.02 — grub.cfg ownership, permissions and menu entries

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Permissions demonstrated: grub.cfg root:root 0600, with boot menu entries.

**Identified weakness / gap:** No filesystem-permission patch indicated.

**Implementation task:** No filesystem-permission patch indicated.

**Core checkpoints:** `KHAHP-08.02A`, `KHAHP-08.02B`, `KHAHP-08.02C`

**Source / evidence status:** 08-grub-bootloader-protection-20261012-135756.txt | Permissions demonstrated

### 08.03 — GRUB password_pbkdf2 and superusers directives

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Configuration demonstrated; negative test absent: Both directives detected in source and generated configuration.

**Identified weakness / gap:** Actual unauthorized interactive GRUB-edit rejection not tested; no password/hash disclosure.

**Implementation task:** Actual unauthorized interactive GRUB-edit rejection not tested; no password/hash disclosure.

**Core checkpoints:** `KHAHP-08.03A`, `KHAHP-08.03B`, `KHAHP-08.03C`

**Source / evidence status:** 08-grub-bootloader-protection-20261012-135756.txt | Configuration demonstrated; negative test absent

### 08.04 — Kicksecure CPU/kernel/ram-wipe/remount/signed -module fragments

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Source attribution demonstrated: CPU mitigations, kernel hardening, ram wipe, remount-secure, module signing fragments package-attributed.

**Identified weakness / gap:** Runtime enforcement belongs to dedicated sections; package ownership alone is not an effective-state proof.

**Implementation task:** Runtime enforcement belongs to dedicated sections; package ownership alone is not an effective- state proof.

**Core checkpoints:** `KHAHP-08.04A`, `KHAHP-08.04B`, `KHAHP-08.04C`

**Source / evidence status:** 08-grub-bootloader-protection-20261012-135756.txt | Source attribution demonstrated

### 08.05 — Quiet-boot and recovery-restriction fragments

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Configuration demonstrated: Recovery-restriction fragment sets GRUB_DISABLE_RECOVERY and rd.emergency=halt / rd.shell=0.

**Identified weakness / gap:** No live rescue-mode bypass attempt; disabling recovery has availability tradeoffs.

**Implementation task:** No live rescue-mode bypass attempt; disabling recovery has availability tradeoffs.

**Core checkpoints:** `KHAHP-08.05A`, `KHAHP-08.05B`, `KHAHP-08.05C`

**Source / evidence status:** 08-grub-bootloader-protection-20261012-135756.txt | Configuration demonstrated

### 08.06 — Effective boot command-line correlation

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Runtime tokens demonstrated: /proc/cmdline contains many selected hardening flags corresponding to sources.

**Identified weakness / gap:** Tokens do not guarantee kernel recognizes them; see Section 09 unknown-parameter log.

**Implementation task:** Tokens do not guarantee kernel recognizes them; see Section 09 unknown-parameter log.

**Core checkpoints:** `KHAHP-08.06A`, `KHAHP-08.06B`, `KHAHP-08.06C`

**Source / evidence status:** 08-grub-bootloader-protection-20261012-135756.txt | Runtime tokens demonstrated

### 08.07 — /boot and EFI exposure versus cryptographic integrity limits

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Risk recorded; later positive evidence: /boot and EFI distinct and unencrypted; report disclaims GRUB password as integrity proof.

**Identified weakness / gap:** Later Section 39 Secure Boot/MOK signs/enrolls modules; boot-file coverage and physical attack recovery remain nuanced.

**Implementation task:** Later Section 39 Secure Boot/MOK signs/enrolls modules; boot-file coverage and physical attack recovery remain nuanced.

**Core checkpoints:** `KHAHP-08.07A`, `KHAHP-08.07B`, `KHAHP-08.07C`

**Source / evidence status:** 08-grub-bootloader-protection-20261012-135756.txt | Risk recorded; later positive evidence

---

## 09 — CPU Vulnerability Mitigations

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 09.01 — CPU identity, vendor and mitigation- capability baseline

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Inventory demonstrated: Intel Core i5-10210U; 4 online cores, 8 logical possible; VT-x support recorded.

**Identified weakness / gap:** Hardware-specific; must revalidate on each customer target.

**Implementation task:** Hardware-specific; must revalidate on each customer target.

**Core checkpoints:** `KHAHP-09.01A`, `KHAHP-09.01B`, `KHAHP-09.01C`

**Source / evidence status:** 09-cpu-vulnerability-mitigations-20261012-141547.txt | Inventory demonstrated

### 09.02 — SMT/Hyper-Threading disablement and topology

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Runtime demonstrated: smt/active=0, control=forceoff; one thread/core; nosmt=force live.

**Identified weakness / gap:** Already hardened on laptop; assess VM or different hardware separately.

**Implementation task:** Already hardened on laptop; assess VM or different hardware separately.

**Core checkpoints:** `KHAHP-09.02A`, `KHAHP-09.02B`, `KHAHP-09.02C`

**Source / evidence status:** 09-cpu-vulnerability-mitigations-20261012-141547.txt | Runtime demonstrated

### 09.03 — Runtime microcode revision and package baseline

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Runtime and package demonstrated: Microcode revision 0x100; intel-microcode package installed; kernel log says early updated from 0xde.

**Identified weakness / gap:** Security update freshness not established by installed-version presence alone.

**Implementation task:** Security update freshness not established by installed-version presence alone.

**Core checkpoints:** `KHAHP-09.03A`, `KHAHP-09.03B`, `KHAHP-09.03C`

**Source / evidence status:** 09-cpu-vulnerability-mitigations-20261012-141547.txt | Runtime and package demonstrated

### 09.04 — Kernel vulnerability-interface enumeration

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Runtime demonstrated: 17 /sys/devices/system/cpu/vulnerabilities entries examined; no reported unmitigated finding in selected test.

**Identified weakness / gap:** Keep as dated kernel interpretation, not proof against all future vulnerabilities.

**Implementation task:** Keep as dated kernel interpretation, not proof against all future vulnerabilities.

**Core checkpoints:** `KHAHP-09.04A`, `KHAHP-09.04B`, `KHAHP-09.04C`

**Source / evidence status:** 09-cpu-vulnerability-mitigations-20261012-141547.txt | Runtime demonstrated

### 09.05 — Spectre/Meltdown/L1TF/MDS/ Retbleed/BHI/SSB/TAA/GDS mitigations

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Runtime demonstrated: Kernel reports mitigated or Not affected for listed classes; GDS and SRBDS via microcode, SMT disabled.

**Identified weakness / gap:** No new patch indicated by report; recheck after kernel/microcode updates.

**Implementation task:** No new patch indicated by report; recheck after kernel/microcode updates.

**Core checkpoints:** `KHAHP-09.05A`, `KHAHP-09.05B`, `KHAHP-09.05C`

**Source / evidence status:** 09-cpu-vulnerability-mitigations-20261012-141547.txt | Runtime demonstrated

### 09.06 — Mitigation-related kernel command- line parameters

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Source/runtime tokens demonstrated; review: Report matches many policy boot tokens, including spectre_v2, ssbd, kpti, mitigations and vmscape.

**Identified weakness / gap:** Kernel log also identifies some unrecognized tokens; audit their actual support before crediting effects.

**Implementation task:** Kernel log also identifies some unrecognized tokens; audit their actual support before crediting effects.

**Core checkpoints:** `KHAHP-09.06A`, `KHAHP-09.06B`, `KHAHP-09.06C`

**Source / evidence status:** 09-cpu-vulnerability-mitigations-20261012-141547.txt | Source/runtime tokens demonstrated; review

### 09.07 — CPU mitigation flags and kernel-log confirmation

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Runtime demonstrated; parser limitation: CPU flags ibrs/ibpb/stibp/ssbd/md_clear/flush_l1d listed; logs confirm several mitigation actions.

**Identified weakness / gap:** Review unknown-kernel-parameter message as effectiveness caveat; do not remove or add flags blindly.

**Implementation task:** Review unknown-kernel-parameter message as effectiveness caveat; do not remove or add flags blindly.

**Core checkpoints:** `KHAHP-09.07A`, `KHAHP-09.07B`, `KHAHP-09.07C`

**Source / evidence status:** 09-cpu-vulnerability-mitigations-20261012-141547.txt | Runtime demonstrated; parser limitation

---

## 10 — IOMMU / DMA Protection

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 10.01 — CPU virtualization/VT-d capability baseline

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Inventory demonstrated: Intel VT-x and CPU vendor identified.

**Identified weakness / gap:** VT-x capability alone is not VT-d proof; see runtime DMAR.

**Implementation task:** VT-x capability alone is not VT-d proof; see runtime DMAR.

**Core checkpoints:** `KHAHP-10.01A`, `KHAHP-10.01B`, `KHAHP-10.01C`

**Source / evidence status:** 10-iommu-dma-protection-20261012-142405.txt | Inventory demonstrated

### 10.02 — IOMMU kernel parameters and passthrough policy

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Runtime tokens demonstrated: intel_iommu=on, iommu=force, iommu.passthrough=0, iommu.strict=1, early PCI DMA restriction present.

**Identified weakness / gap:** Cross-vendor amd_iommu option is logged as informational, not failure.

**Implementation task:** Cross-vendor amd_iommu option is logged as informational, not failure.

**Core checkpoints:** `KHAHP-10.02A`, `KHAHP-10.02B`, `KHAHP-10.02C`

**Source / evidence status:** 10-iommu-dma-protection-20261012-142405.txt | Runtime tokens demonstrated

### 10.03 — DMAR/IOMMU runtime enablement

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Runtime demonstrated: Kernel DMAR reports IOMMU enabled, VT-d recognized.

**Identified weakness / gap:** No patch indicated by reported runtime.

**Implementation task:** No patch indicated by reported runtime.

**Core checkpoints:** `KHAHP-10.03A`, `KHAHP-10.03B`, `KHAHP-10.03C`

**Source / evidence status:** 10-iommu-dma-protection-20261012-142405.txt | Runtime demonstrated

### 10.04 — Translated default domain and strict invalidation

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Runtime demonstrated: Kernel explicitly reports translated default DMA domain and strict invalidation policy.

**Identified weakness / gap:** No patch indicated.

**Implementation task:** No patch indicated.

**Core checkpoints:** `KHAHP-10.04A`, `KHAHP-10.04B`, `KHAHP-10.04C`

**Source / evidence status:** 10-iommu-dma-protection-20261012-142405.txt | Runtime demonstrated

### 10.05 — IRQ/interrupt remapping

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Runtime demonstrated: Kernel reports IRQ remapping enabled in x2APIC mode.

**Identified weakness / gap:** No patch indicated.

**Implementation task:** No patch indicated.

**Core checkpoints:** `KHAHP-10.05A`, `KHAHP-10.05B`, `KHAHP-10.05C`

**Source / evidence status:** 10-iommu-dma-protection-20261012-142405.txt | Runtime demonstrated

### 10.06 — IOMMU group topology and full PCI membership

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Runtime demonstrated; topology review: 23/23 PCI devices have IOMMU groups; 17 groups total, 4 contain multiple devices.

**Identified weakness / gap:** Multi-device groups are not automatically unsafe; device assignment/pass-through policy needs separate review.

**Implementation task:** Multi-device groups are not automatically unsafe; device assignment/pass-through policy needs separate review.

**Core checkpoints:** `KHAHP-10.06A`, `KHAHP-10.06B`, `KHAHP-10.06C`

**Source / evidence status:** 10-iommu-dma-protection-20261012-142405.txt | Runtime demonstrated; topology review

### 10.07 — Early PCI DMA restriction and firmware WSMT evidence

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Runtime token + firmware inventory: efi=disable_early_pci_dma present; WSMT table identified.

**Identified weakness / gap:** Firmware-based preboot DMA and physical access not fully verified by runtime logs; Section 39 remains relevant.

**Implementation task:** Firmware-based preboot DMA and physical access not fully verified by runtime logs; Section 39 remains relevant.

**Core checkpoints:** `KHAHP-10.07A`, `KHAHP-10.07B`, `KHAHP-10.07C`

**Source / evidence status:** 10-iommu-dma-protection-20261012-142405.txt | Runtime token + firmware inventory

---

## 11 — Kernel Sysctl Hardening

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 11.01 — Sysctl source-tree inventory and precedence

**Stage / source classification:** `S2 / NO PATCH SHOWN`

**Historical evidence:** Sysctl configuration files, precedence view and selected live values inventoried.

**Identified weakness / gap:** File inventory does not itself prove every precedence override persists through upgrade.

**Implementation task:** PRESERVE / LINK EVIDENCE

**Core checkpoints:** `KHAHP-11.01A`, `KHAHP-11.01B`, `KHAHP-11.01C`

**Source / evidence status:** 11-kernel-sysctl-hardening-20261012-143141.txt | NO PATCH SHOWN

### 11.02 — Kicksecure security-misc sysctl source files

**Stage / source classification:** `S2 / NO PATCH SHOWN`

**Historical evidence:** Kicksecure/security-misc sources for kexec, ptrace, printk and ASLR were found and attributed.

**Identified weakness / gap:** Provenance and live behavior supported for selected values; do not override package policy blindly.

**Implementation task:** PRESERVE PACKAGE POLICY

**Core checkpoints:** `KHAHP-11.02A`, `KHAHP-11.02B`, `KHAHP-11.02C`

**Source / evidence status:** 11-kernel-sysctl-hardening-20261012-143141.txt | NO PATCH SHOWN

### 11.03 — Kernel information-leak restrictions

**Stage / source classification:** `S2 / ENFORCED IN REPORT`

**Historical evidence:** Live kptr_restrict=2, dmesg_restrict=1 and perf_event_paranoid=3 positively observed.

**Identified weakness / gap:** Current-boot checks; customer builds must repeat.

**Implementation task:** Retain the observed protection; link complete source/runtime/persistence proof and re-verify after changes.

**Core checkpoints:** `KHAHP-11.03A`, `KHAHP-11.03B`, `KHAHP-11.03C`

**Source / evidence status:** 11-kernel-sysctl-hardening-20261012-143141.txt | ENFORCED IN REPORT

### 11.04 — ASLR, mmap, kexec and privileged- coredump controls

**Stage / source classification:** `S2 / ENFORCED IN REPORT`

**Historical evidence:** ASLR=2, kexec_load_disabled=1, mmap_min_addr=65536 and suid_dumpable=0 checked live.

**Identified weakness / gap:** No bypass or upgrade-persistence experiment in this source.

**Implementation task:** Retain the observed protection; link complete source/runtime/persistence proof and re-verify after changes.

**Core checkpoints:** `KHAHP-11.04A`, `KHAHP-11.04B`, `KHAHP-11.04C`

**Source / evidence status:** 11-kernel-sysctl-hardening-20261012-143141.txt | ENFORCED IN REPORT

### 11.05 — BPF, ptrace, perf and TTY line- discipline restrictions

**Stage / source classification:** `S2 / ENFORCED IN REPORT`

**Historical evidence:** unprivileged_bpf_disabled=1, BPF JIT harden=2, ptrace_scope=3 and TTY autoload=0 checked live.

**Identified weakness / gap:** Unprivileged user namespace was 1 and flagged compatibility-sensitive, not automatically failed.

**Implementation task:** RETAIN; CONTEXT REVIEW

**Core checkpoints:** `KHAHP-11.05A`, `KHAHP-11.05B`, `KHAHP-11.05C`

**Source / evidence status:** 11-kernel-sysctl-hardening-20261012-143141.txt | ENFORCED IN REPORT

### 11.06 — Protected links/FIFOs/regular-file controls

**Stage / source classification:** `S2 / ENFORCED IN REPORT`

**Historical evidence:** protected_hardlinks/symlinks=1, protected_fifos/regular=2 checked live.

**Identified weakness / gap:** No live bypass test; positive sysctl state established.

**Implementation task:** Retain the observed protection; link complete source/runtime/persistence proof and re-verify after changes.

**Core checkpoints:** `KHAHP-11.06A`, `KHAHP-11.06B`, `KHAHP-11.06C`

**Source / evidence status:** 11-kernel-sysctl-hardening-20261012-143141.txt | ENFORCED IN REPORT

### 11.07 — Network-stack sysctl hardening observations

**Stage / source classification:** `S2 / CROSS-SECTION REVIEW`

**Historical evidence:** IPv4 redirect/source-route restrictions, log_martians=1, syncookies=1 recorded.

**Identified weakness / gap:** Report explicitly defers final networking/DNS policy interpretation to later sections.

**Implementation task:** LINK TO NETWORK REPORTS

**Core checkpoints:** `KHAHP-11.07A`, `KHAHP-11.07B`, `KHAHP-11.07C`

**Source / evidence status:** 11-kernel-sysctl-hardening-20261012-143141.txt | CROSS-SECTION REVIEW

---

## 12 — Kernel Boot / Memory Hardening

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 12.01 — Slab allocator hardening and slab_nomerge

**Stage / source classification:** `S2 / CONFIG & BOOT CONFIRMED`

**Historical evidence:** slab_nomerge and slab_debug=FZ found in source GRUB, generated GRUB and /proc/cmdline.

**Identified weakness / gap:** Flag presence does not prove allocator behavior beyond supported kernel evidence.

**Implementation task:** RETAIN / CHECK EFFECT

**Core checkpoints:** `KHAHP-12.01A`, `KHAHP-12.01B`, `KHAHP-12.01C`

**Source / evidence status:** 12-kernel-boot-memory-hardening-20261012-161307.txt | CONFIG & BOOT CONFIRMED

### 12.02 — init_on_alloc and init_on_free memory initialization

**Stage / source classification:** `S2 / CONFIG & BOOT CONFIRMED`

**Historical evidence:** init_on_alloc=1, init_on_free=1 found in source, generated GRUB and live boot.

**Identified weakness / gap:** Memory initialization build/runtime effect not independently stress-tested.

**Implementation task:** Retain the observed protection; link complete source/runtime/persistence proof and re-verify after changes.

**Core checkpoints:** `KHAHP-12.02A`, `KHAHP-12.02B`, `KHAHP-12.02C`

**Source / evidence status:** 12-kernel-boot-memory-hardening-20261012-161307.txt | CONFIG & BOOT CONFIRMED

### 12.03 — page allocator shuffle and stack randomization

**Stage / source classification:** `S2 / CONFIG & BOOT CONFIRMED`

**Historical evidence:** page_alloc.shuffle=1 and randomize_kstack_offset=on persisted through source, GRUB and boot.

**Identified weakness / gap:** Runtime randomization quality not experimentally evaluated.

**Implementation task:** Retain the observed protection; link complete source/runtime/persistence proof and re-verify after changes.

**Core checkpoints:** `KHAHP-12.03A`, `KHAHP-12.03B`, `KHAHP-12.03C`

**Source / evidence status:** 12-kernel-boot-memory-hardening-20261012-161307.txt | CONFIG & BOOT CONFIRMED

### 12.04 — vsyscall, vdso32 and 32-bit compatibility restrictions

**Stage / source classification:** `S2 / CONFIG & LIMITED RUNTIME`

**Historical evidence:** vsyscall=none, vdso32=0 and ia32_emulation=0 present; verifier showed no vsyscall mapping.

**Identified weakness / gap:** Architecture/compatibility needs reassessment on clean builds.

**Implementation task:** Retain the observed protection; link complete source/runtime/persistence proof and re-verify after changes.

**Core checkpoints:** `KHAHP-12.04A`, `KHAHP-12.04B`, `KHAHP-12.04C`

**Source / evidence status:** 12-kernel-boot-memory-hardening-20261012-161307.txt | CONFIG & LIMITED RUNTIME

### 12.05 — debugfs, KFENCE and kernel debug- surface controls

**Stage / source classification:** `S2 / ENFORCED IN REPORT`

**Historical evidence:** debugfs=off, KFENCE sample interval 100 and unmounted debugfs directly observed.

**Identified weakness / gap:** KFENCE sample interval does not prove detected faults; no intentional fault injection.

**Implementation task:** Retain the observed protection; link complete source/runtime/persistence proof and re-verify after changes.

**Core checkpoints:** `KHAHP-12.05A`, `KHAHP-12.05B`, `KHAHP-12.05C`

**Source / evidence status:** 12-kernel-boot-memory-hardening-20261012-161307.txt | ENFORCED IN REPORT

### 12.06 — CFI/KCFI and boot-time control acceptance

**Stage / source classification:** `S2 / OPEN EFFECTIVENESS WARNING`

**Historical evidence:** cfi=kcfi persisted in GRUB and command line; kernel logged it as an unknown boot option and no positive CFI enablement was found.

**Identified weakness / gap:** CONFIG_ARCH_SUPPORTS_CFI_CLANG=y indicates support capability, NOT CONFIG_CFI_CLANG or active KCFI.

**Implementation task:** TARGETED KERNEL BUILD/RUNTIME VALIDATION

**Core checkpoints:** `KHAHP-12.06A`, `KHAHP-12.06B`, `KHAHP-12.06C`

**Source / evidence status:** 12-kernel-boot-memory-hardening-20261012-161307.txt | OPEN EFFECTIVENESS WARNING

### 12.07 — pstore/ERST/proc_mem/entropy trust boot parameters

**Stage / source classification:** `S2 / CONFIG ONLY / REVIEW`

**Historical evidence:** pstore/ERST, proc_mem and random trust tokens inventoried; extra_latent_entropy forwarded as unknown and no userspace consumer found.

**Identified weakness / gap:** Some boot tokens are non-effective, and pstore is mounted; see Section 22 before proposing replacement flags.

**Implementation task:** DISTINGUISH REAL FROM INERT CONTROLS

**Core checkpoints:** `KHAHP-12.07A`, `KHAHP-12.07B`, `KHAHP-12.07C`

**Source / evidence status:** 12-kernel-boot-memory-hardening-20261012-161307.txt | CONFIG ONLY / REVIEW

---

## 13 — Kernel Module Restrictions

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 13.01 — security-misc module blacklist configuration

**Stage / source classification:** `S2 / SOURCE CONFIRMED`

**Historical evidence:** security-misc blacklist/disable source files were package-attributed; effective modprobe config recorded.

**Identified weakness / gap:** Source integrity not identical to current-boot negative-load tests.

**Implementation task:** Retain the observed protection; link complete source/runtime/persistence proof and re-verify after changes.

**Core checkpoints:** `KHAHP-13.01A`, `KHAHP-13.01B`, `KHAHP-13.01C`

**Source / evidence status:** 13-kernel-module-restrictions-20261012-162051.txt | SOURCE CONFIRMED

### 13.02 — Hard-disable install rules for risky modules

**Stage / source classification:** `S2 / SOURCE CONFIRMED`

**Historical evidence:** Hard-disable install rules using Kicksecure handlers found in effective modprobe config.

**Identified weakness / gap:** One exceptional dry-run requires review; see 13.07.

**Implementation task:** RETAIN / CROSS-CHECK

**Core checkpoints:** `KHAHP-13.02A`, `KHAHP-13.02B`, `KHAHP-13.02C`

**Source / evidence status:** 13-kernel-module-restrictions-20261012-162051.txt | SOURCE CONFIRMED

### 13.03 — Loaded-module inventory versus policy

**Stage / source classification:** `S2 / RUNTIME CONFIRMED`

**Historical evidence:** Loaded modules enumerated; zero modules matched examined blacklist/install-rule-disabled lists.

**Identified weakness / gap:** Current boot only; future modules and dynamic loading not prevented by this observation.

**Implementation task:** Retain the observed protection; link complete source/runtime/persistence proof and re-verify after changes.

**Core checkpoints:** `KHAHP-13.03A`, `KHAHP-13.03B`, `KHAHP-13.03C`

**Source / evidence status:** 13-kernel-module-restrictions-20261012-162051.txt | RUNTIME CONFIRMED

### 13.04 — Legacy filesystem module restrictions

**Stage / source classification:** `S2 / SOURCE CONFIRMED`

**Historical evidence:** Legacy filesystem module restrictions shown in security-misc policy.

**Identified weakness / gap:** Not all filesystem module absence/build status proven by policy presence.

**Implementation task:** RETAIN / PROFILE REVIEW

**Core checkpoints:** `KHAHP-13.04A`, `KHAHP-13.04B`, `KHAHP-13.04C`

**Source / evidence status:** 13-kernel-module-restrictions-20261012-162051.txt | SOURCE CONFIRMED

### 13.05 — Legacy network/protocol module restrictions

**Stage / source classification:** `S2 / SOURCE CONFIRMED`

**Historical evidence:** Legacy network/protocol module restriction sources and safe dry-run samples recorded.

**Identified weakness / gap:** No aggressive blocking of necessary Kicksecure protocols without compatibility validation.

**Implementation task:** RETAIN / PROFILE REVIEW

**Core checkpoints:** `KHAHP-13.05A`, `KHAHP-13.05B`, `KHAHP-13.05C`

**Source / evidence status:** 13-kernel-module-restrictions-20261012-162051.txt | SOURCE CONFIRMED

### 13.06 — USB/storage/media module restriction exceptions

**Stage / source classification:** `S2 / INTENTIONAL POLICY`

**Historical evidence:** Report confirms usb_storage and uas were intentionally not hard-disabled.

**Identified weakness / gap:** Deliberate requirement to permit USB mass-storage; do not blacklist these modules.

**Implementation task:** DOCUMENT INTENTIONAL EXCEPTION

**Core checkpoints:** `KHAHP-13.06A`, `KHAHP-13.06B`, `KHAHP-13.06C`

**Source / evidence status:** 13-kernel-module-restrictions-20261012-162051.txt | INTENTIONAL POLICY

### 13.07 — Module-load negative tests and compatibility exceptions

**Stage / source classification:** `S2 / OPEN CLASSIFICATION WARNING`

**Historical evidence:** 145 of 146 simulated module loads showed restriction-like results; vesafb returned rc=0 with empty output.

**Identified weakness / gap:** vesafb result inconclusive: module may be built in, absent or not subject to expected install rule; no actual exploit proved.

**Implementation task:** TARGETED VESAFB CLASSIFICATION

**Core checkpoints:** `KHAHP-13.07A`, `KHAHP-13.07B`, `KHAHP-13.07C`

**Source / evidence status:** 13-kernel-module-restrictions-20261012-162051.txt | OPEN CLASSIFICATION WARNING

---

## 14 — Kernel Module Signing / DKMS

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 14.01 — Loaded-module signer inventory

**Stage / source classification:** `S2 / SOURCE/RUNTIME WITH LATER EVIDENCE`

**Historical evidence:** All loaded modules showed signer metadata in historical Section 14 inventory.

**Identified weakness / gap:** Signer metadata alone does not prove platform trust or enforcement at that date.

**Implementation task:** LINK TO 39 SECURE BOOT

**Core checkpoints:** `KHAHP-14.01A`, `KHAHP-14.01B`, `KHAHP-14.01C`

**Source / evidence status:** 14-kernel-module-signing-dkms-20261012-163518.txt | SOURCE/RUNTIME WITH LATER EVIDENCE

### 14.02 — DKMS package and built-module inventory

**Stage / source classification:** `S2 / HISTORICAL WARNING OVERRIDDEN`

**Historical evidence:** dkms status lists tirdad for the running and older kernel; DKMS module file present.

**Identified weakness / gap:** Verifier warning about missing running-kernel DKMS build contradicts its own dkms status; likely classifier defect.

**Implementation task:** RESOLVE FALSE-POSITIVE WARNING

**Core checkpoints:** `KHAHP-14.02A`, `KHAHP-14.02B`, `KHAHP-14.02C`

**Source / evidence status:** 14-kernel-module-signing-dkms-20261012-163518.txt | HISTORICAL WARNING OVERRIDDEN

### 14.03 — tirdad DKMS build, signer and runtime state

**Stage / source classification:** `S2 / SUPERSEDED BY LATER EVIDENCE`

**Historical evidence:** Signed tirdad module was loaded; later Section 39 confirms Secure Boot enabled and signer/MOK present.

**Identified weakness / gap:** Do not treat early Setup Mode report as current state; firmware exceptions remain.

**Implementation task:** CREDIT LATER SECTION 39

**Core checkpoints:** `KHAHP-14.03A`, `KHAHP-14.03B`, `KHAHP-14.03C`

**Source / evidence status:** 14-kernel-module-signing-dkms-20261012-163518.txt | SUPERSEDED BY LATER EVIDENCE

### 14.04 — NVIDIA/other third-party module signer state

**Stage / source classification:** `S2 / NO PATCH SHOWN`

**Historical evidence:** Only reported third-party loaded module was signed tirdad; NVIDIA absent.

**Identified weakness / gap:** NVIDIA not installed is informational, not a missing patch.

**Implementation task:** NO NVIDIA REMEDIATION

**Core checkpoints:** `KHAHP-14.04A`, `KHAHP-14.04B`, `KHAHP-14.04C`

**Source / evidence status:** 14-kernel-module-signing-dkms-20261012-163518.txt | NO PATCH SHOWN

### 14.05 — Kernel module signature enforcement capability

**Stage / source classification:** `S2 / PARTIAL ENFORCEMENT EVIDENCE`

**Historical evidence:** Kernel supports module signing; original CONFIG_MODULE_SIG_FORCE was not set; lockdown state recorded.

**Identified weakness / gap:** Signature metadata and Secure Boot integrity do not automatically prove every module policy target; check effective enforcement separately if needed.

**Implementation task:** ENFORCEMENT ASSURANCE REVIEW

**Core checkpoints:** `KHAHP-14.05A`, `KHAHP-14.05B`, `KHAHP-14.05C`

**Source / evidence status:** 14-kernel-module-signing-dkms-20261012-163518.txt | PARTIAL ENFORCEMENT EVIDENCE

### 14.06 — MOK/enrolled certificate readiness

**Stage / source classification:** `S2 / SUPERSEDED BY LATER EVIDENCE`

**Historical evidence:** MOK utility and DKMS signing key paths were present; later Section 39 confirms enrolled signing chain.

**Identified weakness / gap:** MOK material itself must never enter commercial customer image.

**Implementation task:** CREDIT LATER MOK / EXCLUDE SECRETS

**Core checkpoints:** `KHAHP-14.06A`, `KHAHP-14.06B`, `KHAHP-14.06C`

**Source / evidence status:** 14-kernel-module-signing-dkms-20261012-163518.txt | SUPERSEDED BY LATER EVIDENCE

### 14.07 — Secure-Boot compatibility and unsigned-module exceptions

**Stage / source classification:** `S2 / SUPERSEDED BY LATER EVIDENCE`

**Historical evidence:** Original report had Secure Boot disabled and firmware Setup Mode; later Section 39 verifies Secure Boot enabled and SetupMode=0.

**Identified weakness / gap:** Remaining BIOS physical recovery limitations belong to Section 39, not repeated module signing fixes.

**Implementation task:** CREDIT LATER BOOT STATE

**Core checkpoints:** `KHAHP-14.07A`, `KHAHP-14.07B`, `KHAHP-14.07C`

**Source / evidence status:** 14-kernel-module-signing-dkms-20261012-163518.txt | SUPERSEDED BY LATER EVIDENCE

---

## 15 — AppArmor / Mandatory Access Control

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 15.01 — AppArmor kernel/module enablement

**Stage / source classification:** `S1 / ENFORCED SYSTEM LEVEL`

**Historical evidence:** Kernel AppArmor enabled and apparmor.service active in USER-mode report.

**Identified weakness / gap:** Service activity does not guarantee each app has enforced profile.

**Implementation task:** Retain the observed protection; link complete source/runtime/persistence proof and re-verify after changes.

**Core checkpoints:** `KHAHP-15.01A`, `KHAHP-15.01B`, `KHAHP-15.01C`

**Source / evidence status:** 15-apparmor-mandatory-access-control-user-20261012-165737.txt | ENFORCED SYSTEM LEVEL

### 15.02 — Profile inventory and parser status

**Stage / source classification:** `S1 / SOURCE CONFIRMED`

**Historical evidence:** apparmor_parser present; profile files inventoried, package attribution recorded.

**Identified weakness / gap:** Profile file presence does not prove it is loaded or in enforce mode.

**Implementation task:** RETAIN / TEST LABELS

**Core checkpoints:** `KHAHP-15.02A`, `KHAHP-15.02B`, `KHAHP-15.02C`

**Source / evidence status:** 15-apparmor-mandatory-access-control-user-20261012-165737.txt | SOURCE CONFIRMED

### 15.03 — Enforce/complain/unconfined process counts

**Stage / source classification:** `S1 / PRIVILEGED EVIDENCE GAP`

**Historical evidence:** USER was denied privileged aa-status profile counts; module remained loaded.

**Identified weakness / gap:** No authoritative full enforce/complain/unconfined count in this USER report.

**Implementation task:** SYSMAINT STATUS NEEDED

**Core checkpoints:** `KHAHP-15.03A`, `KHAHP-15.03B`, `KHAHP-15.03C`

**Source / evidence status:** 15-apparmor-mandatory-access-control-user-20261012-165737.txt | PRIVILEGED EVIDENCE GAP

### 15.04 — Tor and network-service profile enforcement

**Stage / source classification:** `S1 / MIXED ENFORCEMENT`

**Historical evidence:** tor process label system_tor (enforce), unbound label unbound (enforce); NetworkManager label unconfined.

**Identified weakness / gap:** NetworkManager unconfined and conservative Tor classifier require intentional policy review, not automatic fixes.

**Implementation task:** REVIEW DESIRED PROFILES

**Core checkpoints:** `KHAHP-15.04A`, `KHAHP-15.04B`, `KHAHP-15.04C`

**Source / evidence status:** 15-apparmor-mandatory-access-control-user-20261012-165737.txt | MIXED ENFORCEMENT

### 15.05 — Browser/application profile coverage

**Stage / source classification:** `S1 / OPEN SECURITY COVERAGE GAP`

**Historical evidence:** Fourteen Firefox-related processes reported label firefox (unconfined) despite profile source existing.

**Identified weakness / gap:** Confinement was NOT effective for these processes at report time. Changing package-owned profile can break browser.

**Implementation task:** PRIORITY TARGETED APPARMOR REMEDIATION

**Core checkpoints:** `KHAHP-15.05A`, `KHAHP-15.05B`, `KHAHP-15.05C`

**Source / evidence status:** 15-apparmor-mandatory-access-control-user-20261012-165737.txt | OPEN SECURITY COVERAGE GAP

### 15.06 — Denied-event review and false-positive handling

**Stage / source classification:** `S1 / LIMITED RUNTIME EVIDENCE`

**Historical evidence:** Zero accessible current-boot AppArmor DENIED events and false-positive handling policy documented.

**Identified weakness / gap:** Zero denial events cannot prove no bypass or full confinement.

**Implementation task:** RETAIN / TEST POLICY

**Core checkpoints:** `KHAHP-15.06A`, `KHAHP-15.06B`, `KHAHP-15.06C`

**Source / evidence status:** 15-apparmor-mandatory-access-control-user-20261012-165737.txt | LIMITED RUNTIME EVIDENCE

### 15.07 — USER versus SYSMAINT AppArmor behavior

**Stage / source classification:** `S1 / BOTH-MODE GAP`

**Historical evidence:** USER-side role process labels and source/persistence inventory captured.

**Identified weakness / gap:** SYSMAINT privileged profile counts and a second-boot comparison absent in this report.

**Implementation task:** PAIR WITH SYSMAINT EVIDENCE

**Core checkpoints:** `KHAHP-15.07A`, `KHAHP-15.07B`, `KHAHP-15.07C`

**Source / evidence status:** 15-apparmor-mandatory-access-control-user-20261012-165737.txt | BOTH-MODE GAP

---

## 16 — SUID / SGID / File Capabilities

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 16.01 — Complete SUID file inventory

**Stage / source classification:** `S3 / INVENTORY CONFIRMED`

**Historical evidence:** SUID regular-file inventory of scan-eligible local filesystems completed.

**Identified weakness / gap:** Inventory excludes pseudo-/non-eligible mounts and does not alone prove all allowed SUID files needed.

**Implementation task:** RETAIN / CHANGE BASELINE

**Core checkpoints:** `KHAHP-16.01A`, `KHAHP-16.01B`, `KHAHP-16.01C`

**Source / evidence status:** 16-suid-sgid-file-capabilities-sysmaint-20261012-191027.txt | INVENTORY CONFIRMED

### 16.02 — Complete SGID file inventory

**Stage / source classification:** `S3 / INVENTORY CONFIRMED`

**Historical evidence:** SGID regular-file inventory of scan-eligible local filesystems completed.

**Identified weakness / gap:** A dated snapshot needs package-update persistence comparison.

**Implementation task:** RETAIN / CHANGE BASELINE

**Core checkpoints:** `KHAHP-16.02A`, `KHAHP-16.02B`, `KHAHP-16.02C`

**Source / evidence status:** 16-suid-sgid-file-capabilities-sysmaint-20261012-191027.txt | INVENTORY CONFIRMED

### 16.03 — Package ownership of privileged binaries

**Stage / source classification:** `S3 / PACKAGE ATTRIBUTED`

**Historical evidence:** All discovered SUID/SGID files package-attributed; no tracked privileged-file md5 mismatches.

**Identified weakness / gap:** Hash check limited to available package metadata, not signed measured boot.

**Implementation task:** Retain the observed protection; link complete source/runtime/persistence proof and re-verify after changes.

**Core checkpoints:** `KHAHP-16.03A`, `KHAHP-16.03B`, `KHAHP-16.03C`

**Source / evidence status:** 16-suid-sgid-file-capabilities-sysmaint-20261012-191027.txt | PACKAGE ATTRIBUTED

### 16.04 — permission-hardener expected mode validation

**Stage / source classification:** `S3 / ENFORCED IN REPORT`

**Historical evidence:** permission-hardener present; all extant statoverride targets matched expected owner/group/mode.

**Identified weakness / gap:** Do not apply a broad chmod pass over dpkg-managed files.

**Implementation task:** RETAIN PACKAGE POLICY

**Core checkpoints:** `KHAHP-16.04A`, `KHAHP-16.04B`, `KHAHP-16.04C`

**Source / evidence status:** 16-suid-sgid-file-capabilities-sysmaint-20261012-191027.txt | ENFORCED IN REPORT

### 16.05 — File-capability inventory and package attribution

**Stage / source classification:** `S3 / PRIVILEGED SURFACE REVIEW`

**Historical evidence:** One package-owned file with capabilities: gstreamer gst-ptp-helper, cap_net_bind_service/cap_net_admin/cap_sys_nice.

**Identified weakness / gap:** Capability use/necessity not established; package ownership is not reason to remove cap automatically.

**Implementation task:** REVIEW NECESSITY OF CAPABILITIES

**Core checkpoints:** `KHAHP-16.05A`, `KHAHP-16.05B`, `KHAHP-16.05C`

**Source / evidence status:** 16-suid-sgid-file-capabilities-sysmaint-20261012-191027.txt | PRIVILEGED SURFACE REVIEW

### 16.06 — Unexpected privileged executable detection

**Stage / source classification:** `S3 / NO UNSAFE FILE DETECTED`

**Historical evidence:** No SUID/SGID regular file world/group-writable, in reviewed writable user/temp paths, or unowned.

**Identified weakness / gap:** No negative execution test; known file capability should be reviewed separately.

**Implementation task:** Retain the observed protection; link complete source/runtime/persistence proof and re-verify after changes.

**Core checkpoints:** `KHAHP-16.06A`, `KHAHP-16.06B`, `KHAHP-16.06C`

**Source / evidence status:** 16-suid-sgid-file-capabilities-sysmaint-20261012-191027.txt | NO UNSAFE FILE DETECTED

### 16.07 — Privilege-binary negative/compatibility review

**Stage / source classification:** `S3 / TEST-GAP ONLY`

**Historical evidence:** Privileged-mount semantics, USER/SYSMAINT hardener integration and passive verification recorded.

**Identified weakness / gap:** Report explicitly did not invoke privileged executables for negative test; persistence comparison elsewhere.

**Implementation task:** DEFER CONTROLLED NEGATIVE TEST

**Core checkpoints:** `KHAHP-16.07A`, `KHAHP-16.07B`, `KHAHP-16.07C`

**Source / evidence status:** 16-suid-sgid-file-capabilities-sysmaint-20261012-191027.txt | TEST-GAP ONLY

---

## 17 — Permissions / ACL / Umask

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 17.01 — System file ownership baseline

**Stage / source classification:** `S1 / PERMISSIONS PASS`

**Historical evidence:** Critical auth/privilege/boot files reviewed: root-owned and not group/world writable.

**Identified weakness / gap:** Source report is from 12 Oct and not current scan.

**Implementation task:** Retain the observed protection; link complete source/runtime/persistence proof and re-verify after changes.

**Core checkpoints:** `KHAHP-17.01A`, `KHAHP-17.01B`, `KHAHP-17.01C`

**Source / evidence status:** 17-permissions-acl-umask-sysmaint-20261012-202746.txt | PERMISSIONS PASS

### 17.02 — World-writable system path inventory

**Stage / source classification:** `S1 / OPEN DIRECTORY PERMISSION WARNING`

**Historical evidence:** No world-writable regular files; one directory /var/cache/setup-dist/status-files root:root mode 0777 lacked sticky bit.

**Identified weakness / gap:** Unattributed system cache path needs owner/consumer check and live recheck before chmod.

**Implementation task:** HIGH PRIORITY ATTRIBUTION & SAFE FIX

**Core checkpoints:** `KHAHP-17.02A`, `KHAHP-17.02B`, `KHAHP-17.02C`

**Source / evidence status:** 17-permissions-acl-umask-sysmaint-20261012-202746.txt | OPEN DIRECTORY PERMISSION WARNING

### 17.03 — Unexpected group-writable sensitive paths

**Stage / source classification:** `S1 / PERMISSIONS PASS`

**Historical evidence:** No unexpected group-writable (but not world-writable) sensitive paths in reviewed roots.

**Identified weakness / gap:** Coverage limited to listed roots.

**Implementation task:** Retain the observed protection; link complete source/runtime/persistence proof and re-verify after changes.

**Core checkpoints:** `KHAHP-17.03A`, `KHAHP-17.03B`, `KHAHP-17.03C`

**Source / evidence status:** 17-permissions-acl-umask-sysmaint-20261012-202746.txt | PERMISSIONS PASS

### 17.04 — ACL inventory on sensitive configuration

**Stage / source classification:** `S1 / ACL INVENTORY PASS`

**Historical evidence:** getfacl traversed high-sensitivity paths; no extended ACLs found there.

**Identified weakness / gap:** No ACLs observed does not prove all access-control requirements.

**Implementation task:** Retain the observed protection; link complete source/runtime/persistence proof and re-verify after changes.

**Core checkpoints:** `KHAHP-17.04A`, `KHAHP-17.04B`, `KHAHP-17.04C`

**Source / evidence status:** 17-permissions-acl-umask-sysmaint-20261012-202746.txt | ACL INVENTORY PASS

### 17.05 — Root and user umask policy

**Stage / source classification:** `S1 / BENCHMARK ALIGNMENT REVIEW`

**Historical evidence:** SYSMAINT invoking shell umask 0022; Kicksecure PAM umask fragments 027/022 recorded.

**Identified weakness / gap:** Not umask=077 for SYSMAINT; effective ordinary USER shell umask was not measured in this report.

**Implementation task:** POLICY/USER MODE REVIEW

**Core checkpoints:** `KHAHP-17.05A`, `KHAHP-17.05B`, `KHAHP-17.05C`

**Source / evidence status:** 17-permissions-acl-umask-sysmaint-20261012-202746.txt | BENCHMARK ALIGNMENT REVIEW

### 17.06 — Home and evidence-directory permissions

**Stage / source classification:** `S1 / PASS AT SNAPSHOT`

**Historical evidence:** Reviewed KHAHP and home dirs had no reported ownership/write exposure; KHAHP was mode 0700.

**Identified weakness / gap:** Home dirs 0750 at snapshot; later archive creation deliberately changed KHAHP ownership.

**Implementation task:** RECONCILE AGAINST LATER FILE OWNERSHIP

**Core checkpoints:** `KHAHP-17.06A`, `KHAHP-17.06B`, `KHAHP-17.06C`

**Source / evidence status:** 17-permissions-acl-umask-sysmaint-20261012-202746.txt | PASS AT SNAPSHOT

### 17.07 — Sticky-bit and shared-directory permission policy

**Stage / source classification:** `S1 / OPEN DIRECTORY PERMISSION WARNING`

**Historical evidence:** Canonical /tmp and /var/tmp shared dirs had sticky bit; same noncanonical cache dir lacked it.

**Identified weakness / gap:** 17.02 and 17.07 are two warnings for ONE underlying path, not two independent vulnerabilities.

**Implementation task:** SAME ACTION AS 17.02

**Core checkpoints:** `KHAHP-17.07A`, `KHAHP-17.07B`, `KHAHP-17.07C`

**Source / evidence status:** 17-permissions-acl-umask-sysmaint-20261012-202746.txt | OPEN DIRECTORY PERMISSION WARNING

---

## 18 — PAM / Login / Faillock

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 18.01 — PAM stack package provenance

**Stage / source classification:** `S3 / LOW`

**Historical evidence:** PAM packages present; common PAM files root-owned and protected; Kicksecure PAM fragments present.

**Identified weakness / gap:** Inventory and permissions do not prove every authentication path enforces these modules.

**Implementation task:** RETAIN; reconcile USER authentication paths

**Core checkpoints:** `KHAHP-18.01A`, `KHAHP-18.01B`, `KHAHP-18.01C`

**Source / evidence status:** 18-pam-login-faillock-sysmaint-20261012-205338.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 18.02 — password quality and hashing policy

**Stage / source classification:** `S3 / MEDIUM`

**Historical evidence:** pam_unix uses yescrypt and login.defs specifies YESCRYPT; pwquality package/config exists.

**Identified weakness / gap:** No active pam_pwquality/pam_passwdqc rule; pwquality settings in report are commented defaults.

**Implementation task:** TARGETED POLICY REVIEW: password quality / UX / installer

**Core checkpoints:** `KHAHP-18.02A`, `KHAHP-18.02B`, `KHAHP-18.02C`

**Source / evidence status:** 18-pam-login-faillock-sysmaint-20261012-205338.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 18.03 — faillock/brute-force lockout policy

**Stage / source classification:** `S3 / MEDIUM`

**Historical evidence:** Active common-auth pam_faillock hooks; deny=50, fail_interval=604800, unlock_time=never, even_deny_root.

**Identified weakness / gap:** Counters were read but no safe negative lockout experiment; lockout threshold and indefinite unlock merit usability/DoS review.

**Implementation task:** RETAIN; validate intended faillock policy and non-destructive test

**Core checkpoints:** `KHAHP-18.03A`, `KHAHP-18.03B`, `KHAHP-18.03C`

**Source / evidence status:** 18-pam-login-faillock-sysmaint-20261012-205338.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 18.04 — login delay and retry controls

**Stage / source classification:** `S3 / LOW`

**Historical evidence:** pam_faildelay sets 3,000,000 microseconds; LOGIN_RETRIES=5 and LOGIN_TIMEOUT=60.

**Identified weakness / gap:** FAIL_DELAY parsing unconfirmed; PAM vs login front-end behavior not exercised.

**Implementation task:** PRESERVE; verify interactive behavior only if necessary

**Core checkpoints:** `KHAHP-18.04A`, `KHAHP-18.04B`, `KHAHP-18.04C`

**Source / evidence status:** 18-pam-login-faillock-sysmaint-20261012-205338.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 18.05 — su/sudo/polkit PAM interaction

**Stage / source classification:** `S3 / LOW`

**Historical evidence:** su/sudo/polkit PAM files protected; sudo/pkexec restricted to SYSMAINT group with setuid mode 4750.

**Identified weakness / gap:** This report does not execute privilege-bypass tests; Section 03 supplied sudo denial evidence.

**Implementation task:** CREDIT SECTION 03; preserve USER/SYSMAINT split

**Core checkpoints:** `KHAHP-18.05A`, `KHAHP-18.05B`, `KHAHP-18.05C`

**Source / evidence status:** 18-pam-login-faillock-sysmaint-20261012-205338.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 18.06 — account aging and inactive-account policy High-Assurance Defense-in-Depth

**Stage / source classification:** `S3 / MEDIUM`

**Historical evidence:** root password locked; USER/SYSMAINT accounts active; PASS_MAX_DAYS=99999, PASS_MIN_DAYS=0; warn 7 days.

**Identified weakness / gap:** No password expiration/inactivity enforcement. Must resolve against intended user policy, not arbitrarily set password rotation.

**Implementation task:** POLICY / BENCHMARK APPLICABILITY REVIEW

**Core checkpoints:** `KHAHP-18.06A`, `KHAHP-18.06B`, `KHAHP-18.06C`

**Source / evidence status:** 18-pam-login-faillock-sysmaint-20261012-205338.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 18.07 — USER/SYSMAINT login regression tests

**Stage / source classification:** `S3 / LOW`

**Historical evidence:** Required accounts/homes/shells and login restrictions are present.

**Identified weakness / gap:** No real credential-login regression or post-update check performed in this report.

**Implementation task:** LINK USER/SYSMAINT LOGIN EVIDENCE; deferred functional test

**Core checkpoints:** `KHAHP-18.07A`, `KHAHP-18.07B`, `KHAHP-18.07C`

**Source / evidence status:** 18-pam-login-faillock-sysmaint-20261012-205338.txt | NOT SIGNED OFF AT ASSERTION LEVEL

---

## 19 — SSH Client / Server Security

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 19.01 — Local SSH server service/socket state

**Stage / source classification:** `S3 / LOW`

**Historical evidence:** On Oct 12, openssh-server binary/service absent; subsequent closeout shows ssh.service and ssh.socket masked.

**Identified weakness / gap:** Historical server absence no longer describes later package state; do not use Oct 12 server policy as current.

**Implementation task:** SUPERSEDED by Sections 42 and 39–43 closeout

**Core checkpoints:** `KHAHP-19.01A`, `KHAHP-19.01B`, `KHAHP-19.01C`

**Source / evidence status:** 19-ssh-client-server-security-sysmaint-20261012-210100.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 19.02 — sshd listener and inbound port absence

**Stage / source classification:** `S3 / LOW`

**Historical evidence:** No sshd process and no TCP/22 listener on Oct 12.

**Identified weakness / gap:** SYSMAINT current-boot observation; no external scan in this report.

**Implementation task:** CREDIT later SSH masked check

**Core checkpoints:** `KHAHP-19.02A`, `KHAHP-19.02B`, `KHAHP-19.02C`

**Source / evidence status:** 19-ssh-client-server-security-sysmaint-20261012-210100.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 19.03 — sshd_config security-misc policy if installed

**Stage / source classification:** `S3 / LOW`

**Historical evidence:** Kicksecure sshd_config.d/30_security-misc.conf present: password and keyboard-interactive auth disabled; root setting initially prohibit-password.

**Identified weakness / gap:** Server binary absent then; cannot equate source to effective policy. Later verifier checked PermitRootLogin no and key-only.

**Implementation task:** SUPERSEDED: later effective SSH policy PASS

**Core checkpoints:** `KHAHP-19.03A`, `KHAHP-19.03B`, `KHAHP-19.03C`

**Source / evidence status:** 19-ssh-client-server-security-sysmaint-20261012-210100.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 19.04 — SSH client configuration and host-key verification

**Stage / source classification:** `S3 / LOW`

**Historical evidence:** SSH client strict host checking=ask, HashKnownHosts=yes; Kicksecure client config attributed and protected.

**Identified weakness / gap:** ask is interactive confirmation, not a host-key pinning decision for every user workflow.

**Implementation task:** RETAIN; consider host-key enrollment guidance

**Core checkpoints:** `KHAHP-19.04A`, `KHAHP-19.04B`, `KHAHP-19.04C`

**Source / evidence status:** 19-ssh-client-server-security-sysmaint-20261012-210100.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 19.05 — Private-key ownership and permission baseline

**Stage / source classification:** `S3 / LOW`

**Historical evidence:** Checked SSH paths/private files had safe ownership/modes; no private SSH keys identified in original check.

**Identified weakness / gap:** Absent paths / no keys are not proofs of future key hygiene. Later Section 42 found authorized_keys empty and private modes.

**Implementation task:** CREDIT Section 42 SSH metadata; retest customer provisioning

**Core checkpoints:** `KHAHP-19.05A`, `KHAHP-19.05B`, `KHAHP-19.05C`

**Source / evidence status:** 19-ssh-client-server-security-sysmaint-20261012-210100.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 19.06 — Password-authentication and root- login policy for future server use

**Stage / source classification:** `S3 / LOW`

**Historical evidence:** Originally no server exposed; password auth no in source. Later effective sshd configuration keys-only with no root, and SSH masked.

**Identified weakness / gap:** Original source allowed prohibit-password for root, insufficient for desired no-root policy; later effective policy passed.

**Implementation task:** RESOLVED by later effective no-root SSH evidence

**Core checkpoints:** `KHAHP-19.06A`, `KHAHP-19.06B`, `KHAHP-19.06C`

**Source / evidence status:** 19-ssh-client-server-security-sysmaint-20261012-210100.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 19.07 — Known-hosts/key algorithm and crypto-policy review

**Stage / source classification:** `S3 / LOW`

**Historical evidence:** Effective client crypto list uses modern KEX, ed25519 and AEAD/ETM algorithms; no reviewed legacy algorithms active.

**Identified weakness / gap:** ssh -Q capability list is not active policy; individual server-specific overrides beyond dummy.invalid untested.

**Implementation task:** RETAIN; verify deployment-specific policy on commercial builds

**Core checkpoints:** `KHAHP-19.07A`, `KHAHP-19.07B`, `KHAHP-19.07C`

**Source / evidence status:** 19-ssh-client-server-security-sysmaint-20261012-210100.txt | NOT SIGNED OFF AT ASSERTION LEVEL

---

## 20 — Enabled / Running Service Audit

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 20.01 — Enabled systemd service inventory

**Stage / source classification:** `S3 / MEDIUM`

**Historical evidence:** Enabled/linked systemd services enumerated with provenance.

**Identified weakness / gap:** Inventory alone does not show every enabled service is approved for sale; USER boot differs.

**Implementation task:** MAINTAIN EXPLICIT SERVICE ALLOWLIST

**Core checkpoints:** `KHAHP-20.01A`, `KHAHP-20.01B`, `KHAHP-20.01C`

**Source / evidence status:** 20-enabled-running-service-audit-sysmaint-20261012-213111.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 20.02 — Running systemd service inventory

**Stage / source classification:** `S3 / LOW`

**Historical evidence:** Running systemd services enumerated; key Kicksecure services present.

**Identified weakness / gap:** SYSMAINT only; USER-mode service set must be assessed separately.

**Implementation task:** LINK later USER results and service baseline

**Core checkpoints:** `KHAHP-20.02A`, `KHAHP-20.02B`, `KHAHP-20.02C`

**Source / evidence status:** 20-enabled-running-service-audit-sysmaint-20261012-213111.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 20.03 — Socket/path/timer activated service inventory

**Stage / source classification:** `S3 / MEDIUM`

**Historical evidence:** Socket/path/timer activation inventory captured.

**Identified weakness / gap:** An inactive service can still be socket-activated; inventory requires allowlist review.

**Implementation task:** REVIEW ACTIVATION UNITS BEFORE RELEASE

**Core checkpoints:** `KHAHP-20.03A`, `KHAHP-20.03B`, `KHAHP-20.03C`

**Source / evidence status:** 20-enabled-running-service-audit-sysmaint-20261012-213111.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 20.04 — Kicksecure-required service attribution

**Stage / source classification:** `S3 / LOW`

**Historical evidence:** SYSMAINT service dependencies enumerated and package attribution recorded.

**Identified weakness / gap:** Package-owned does not mean mandatory or least-privileged.

**Implementation task:** RETAIN; operator-approved allowlist for nonessential units

**Core checkpoints:** `KHAHP-20.04A`, `KHAHP-20.04B`, `KHAHP-20.04C`

**Source / evidence status:** 20-enabled-running-service-audit-sysmaint-20261012-213111.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 20.05 — Unexpected or unnecessary service classification

**Stage / source classification:** `S3 / MEDIUM`

**Historical evidence:** 17 exposure-sensitive services/sockets checked inactive/not installed; ssh socket/service masked.

**Identified weakness / gap:** Unfamiliar remaining services not classified as safe or unsafe individually.

**Implementation task:** CLASSIFY ANY UNREVIEWED ACTIVE UNITS; do not mass disable

**Core checkpoints:** `KHAHP-20.05A`, `KHAHP-20.05B`, `KHAHP-20.05C`

**Source / evidence status:** 20-enabled-running-service-audit-sysmaint-20261012-213111.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 20.06 — Listener-to-service ownership correlation

**Stage / source classification:** `S3 / LOW`

**Historical evidence:** Only 127.0.0.1 Unbound:53 and Tor:9050 listeners; 0 non-loopback TCP and 0 TCP/22; all socket PID owners resolved.

**Identified weakness / gap:** Snapshot excludes later service changes, UDP external exposure and USER boot specifics.

**Implementation task:** RETAIN LOOPBACK POLICY; compare USER boot

**Core checkpoints:** `KHAHP-20.06A`, `KHAHP-20.06B`, `KHAHP-20.06C`

**Source / evidence status:** 20-enabled-running-service-audit-sysmaint-20261012-213111.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 20.07 — Reboot persistence and failed-service review

**Stage / source classification:** `S3 / LOW`

**Historical evidence:** No failed units; system running; state fingerprints saved.

**Identified weakness / gap:** A fingerprint in one boot does not prove persistence across boots/updates.

**Implementation task:** LINK Section 41 and 44 drift comparisons

**Core checkpoints:** `KHAHP-20.07A`, `KHAHP-20.07B`, `KHAHP-20.07C`

**Source / evidence status:** 20-enabled-running-service-audit-sysmaint-20261012-213111.txt | NOT SIGNED OFF AT ASSERTION LEVEL

---

## 21 — systemd Service Sandboxing

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 21.01 — systemd-analyze security baseline

**Stage / source classification:** `S3 / MEDIUM`

**Historical evidence:** systemd-analyze security scored all 26 running services; exposure scores recorded, not used as false pass.

**Identified weakness / gap:** Numerous EXPOSED/UNSAFE scores (e.g. unbound 9.6, udisks2 9.6, NetworkManager 7.8); scoring is heuristic, not direct exploit evidence.

**Implementation task:** SERVICE-BY-SERVICE HARDENING REVIEW, regression tested

**Core checkpoints:** `KHAHP-21.01A`, `KHAHP-21.01B`, `KHAHP-21.01C`

**Source / evidence status:** 21-systemd-service-sandboxing-sysmaint-20261012-214104.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 21.02 — NoNewPrivileges adoption

**Stage / source classification:** `S3 / MEDIUM`

**Historical evidence:** NoNewPrivileges=yes on 7 of 16 selected units; Tor/USBGuard/SDWDate supported.

**Identified weakness / gap:** NoNewPrivileges=no on security and privileged helpers (e.g. unbound, usbguard-dbus); may be necessary.

**Implementation task:** REVIEW UNIT-BY-UNIT FOR SAFE PRIVILEGE REDUCTION

**Core checkpoints:** `KHAHP-21.02A`, `KHAHP-21.02B`, `KHAHP-21.02C`

**Source / evidence status:** 21-systemd-service-sandboxing-sysmaint-20261012-214104.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 21.03 — ProtectSystem/ProtectHome restrictions

**Stage / source classification:** `S3 / MEDIUM`

**Historical evidence:** ProtectSystem/ProtectHome state measured; Tor full/yes, SDWDate strict/yes, USBGuard yes/yes.

**Identified weakness / gap:** Several units retain broad file visibility; root helper and network exceptions may be necessary.

**Implementation task:** TEST NARROW SANDBOX DROP-INS IN STAGING FIRST

**Core checkpoints:** `KHAHP-21.03A`, `KHAHP-21.03B`, `KHAHP-21.03C`

**Source / evidence status:** 21-systemd-service-sandboxing-sysmaint-20261012-214104.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 21.04 — PrivateTmp/PrivateDevices isolation

**Stage / source classification:** `S3 / LOW`

**Historical evidence:** PrivateTmp/PrivateDevices state measured for selected units; hardening in some units.

**Identified weakness / gap:** Service functions involving USB, network and devices cannot be blindly isolated.

**Implementation task:** TARGETED COMPATIBILITY REVIEW

**Core checkpoints:** `KHAHP-21.04A`, `KHAHP-21.04B`, `KHAHP-21.04C`

**Source / evidence status:** 21-systemd-service-sandboxing-sysmaint-20261012-214104.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 21.05 — CapabilityBoundingSet and ambient capabilities

**Stage / source classification:** `S3 / MEDIUM`

**Historical evidence:** Ambient capabilities empty for 13/16; reduced bounding sets on 7/16 selected services.

**Identified weakness / gap:** Capability set counts alone do not establish minimum privilege; not all capabilities safely removable.

**Implementation task:** TARGETED CAPABILITY REVIEW, no mass removal

**Core checkpoints:** `KHAHP-21.05A`, `KHAHP-21.05B`, `KHAHP-21.05C`

**Source / evidence status:** 21-systemd-service-sandboxing-sysmaint-20261012-214104.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 21.06 — RestrictNamespaces/ SystemCallFilter/address-family controls

**Stage / source classification:** `S3 / MEDIUM`

**Historical evidence:** Namespace/syscall/address-family controls inventoried and chosen services attributed.

**Identified weakness / gap:** No syscall-filter denial testing or post-hardening service regression in source.

**Implementation task:** TARGETED POLICY REVIEW FOR RISKIEST APPLICABLE SERVICES

**Core checkpoints:** `KHAHP-21.06A`, `KHAHP-21.06B`, `KHAHP-21.06C`

**Source / evidence status:** 21-systemd-service-sandboxing-sysmaint-20261012-214104.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 21.07 — Service-specific compatibility exceptions and regressions

**Stage / source classification:** `S3 / LOW`

**Historical evidence:** 64 sandbox directive lines found; 0 failed units; system running; Tor/Unbound/USBGuard/SDWDate active.

**Identified weakness / gap:** No drop-ins added or modified by this verifier; no staged before/after performance regression test.

**Implementation task:** PRESERVE HEALTH; staged changes only with rollback

**Core checkpoints:** `KHAHP-21.07A`, `KHAHP-21.07B`, `KHAHP-21.07C`

**Source / evidence status:** 21-systemd-service-sandboxing-sysmaint-20261012-214104.txt | NOT SIGNED OFF AT ASSERTION LEVEL

---

## 22 — System.map / Core Dumps / PStore

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 22.01 — System.map exposure and removal policy

**Stage / source classification:** `S3 / LOW`

**Historical evidence:** remove-system-map.service active; no System.map remains in checked policy paths.

**Identified weakness / gap:** Future new kernel installation must retain cleanup functionality.

**Implementation task:** RETAIN / VERIFY ON KERNEL UPDATE

**Core checkpoints:** `KHAHP-22.01A`, `KHAHP-22.01B`, `KHAHP-22.01C`

**Source / evidence status:** 22-systemmap-coredumps-pstore-sysmaint-20261012-215207.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 22.02 — systemd-coredump configuration

**Stage / source classification:** `S3 / LOW`

**Historical evidence:** Effective systemd-coredump Storage=none; policy package-owned.

**Identified weakness / gap:** Presence of unit/config does not equate to saved core files; no intentional dump test.

**Implementation task:** Retain the observed protection; link complete source/runtime/persistence proof and re-verify after changes.

**Core checkpoints:** `KHAHP-22.02A`, `KHAHP-22.02B`, `KHAHP-22.02C`

**Source / evidence status:** 22-systemmap-coredumps-pstore-sysmaint-20261012-215207.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 22.03 — kernel.core_pattern effective state

**Stage / source classification:** `S3 / LOW`

**Historical evidence:** kernel.core_pattern pipes to /bin/false.

**Identified weakness / gap:** Positive runtime suppression config; no negative core-generation test performed.

**Implementation task:** Retain the observed protection; link complete source/runtime/persistence proof and re-verify after changes.

**Core checkpoints:** `KHAHP-22.03A`, `KHAHP-22.03B`, `KHAHP-22.03C`

**Source / evidence status:** 22-systemmap-coredumps-pstore-sysmaint-20261012-215207.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 22.04 — fs.suid_dumpable effective state

**Stage / source classification:** `S3 / LOW`

**Historical evidence:** fs.suid_dumpable=0 observed at runtime.

**Identified weakness / gap:** Does not alone prove all possible application memory leakage routes.

**Implementation task:** Retain the observed protection; link complete source/runtime/persistence proof and re-verify after changes.

**Core checkpoints:** `KHAHP-22.04A`, `KHAHP-22.04B`, `KHAHP-22.04C`

**Source / evidence status:** 22-systemmap-coredumps-pstore-sysmaint-20261012-215207.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 22.05 — pstore retention/disable policy

**Stage / source classification:** `S3 / LOW`

**Historical evidence:** Effective systemd-pstore Storage=none; no current pstore archived records.

**Identified weakness / gap:** Storage=none does not necessarily disable pstore filesystem or all firmware persistence.

**Implementation task:** RETAIN; note privacy vs recovery evidence tradeoff

**Core checkpoints:** `KHAHP-22.05A`, `KHAHP-22.05B`, `KHAHP-22.05C`

**Source / evidence status:** 22-systemmap-coredumps-pstore-sysmaint-20261012-215207.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 22.06 — EFI pstore and ERST boot controls

**Stage / source classification:** `S3 / LOW`

**Historical evidence:** efi_pstore.pstore_disable=1 and erst_disable present in live kernel command line; ERST module absent.

**Identified weakness / gap:** Boot options observed, but no deliberate crash/firmware recovery test.

**Implementation task:** RETAIN; cross-link section 39 firmware

**Core checkpoints:** `KHAHP-22.06A`, `KHAHP-22.06B`, `KHAHP-22.06C`

**Source / evidence status:** 22-systemmap-coredumps-pstore-sysmaint-20261012-215207.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 22.07 — Crash-evidence privacy versus diagnostic requirements

**Stage / source classification:** `S3 / LOW`

**Historical evidence:** No reviewed crash artifacts, core dumps or accessible records; no System.map residual.

**Identified weakness / gap:** Crash-privacy tradeoff can hinder forensic troubleshooting; no crash simulation.

**Implementation task:** DOCUMENT DIAGNOSTIC POLICY / RETAIN

**Core checkpoints:** `KHAHP-22.07A`, `KHAHP-22.07B`, `KHAHP-22.07C`

**Source / evidence status:** 22-systemmap-coredumps-pstore-sysmaint-20261012-215207.txt | NOT SIGNED OFF AT ASSERTION LEVEL

---

## 23 — Journald / Logging / Logrotate

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 23.01 — journald security-misc configuration

**Stage / source classification:** `S3 / LOW`

**Historical evidence:** Kicksecure journald configuration present; ForwardToWall=no.

**Identified weakness / gap:** A config-file presence check is not a complete journald configuration audit.

**Implementation task:** RETAIN; tie to 23.04–23.06 policy

**Core checkpoints:** `KHAHP-23.01A`, `KHAHP-23.01B`, `KHAHP-23.01C`

**Source / evidence status:** 23-journald-logging-logrotate-sysmaint-20261012-215459.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 23.02 — Persistent versus volatile journal storage

**Stage / source classification:** `S3 / MEDIUM`

**Historical evidence:** Journal persisted under /var/log/journal: 101 journal files, roughly 511.7 MB.

**Identified weakness / gap:** Storage is default/auto, not pinned; retention/location may differ on clean builds.

**Implementation task:** DEFINE EXPLICIT STORAGE/RETENTION POLICY, compatibility tested

**Core checkpoints:** `KHAHP-23.02A`, `KHAHP-23.02B`, `KHAHP-23.02C`

**Source / evidence status:** 23-journald-logging-logrotate-sysmaint-20261012-215459.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 23.03 — Journal file permissions and ownership

**Stage / source classification:** `S3 / LOW`

**Historical evidence:** Journal files owned root:systemd-journal, mode 640 in sampled metadata; no unexpected mode/owner.

**Identified weakness / gap:** No claims about exhaustive access by all user groups beyond inspected metadata.

**Implementation task:** Retain the observed protection; link complete source/runtime/persistence proof and re-verify after changes.

**Core checkpoints:** `KHAHP-23.03A`, `KHAHP-23.03B`, `KHAHP-23.03C`

**Source / evidence status:** 23-journald-logging-logrotate-sysmaint-20261012-215459.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 23.04 — Rate limiting and size/retention policy

**Stage / source classification:** `S3 / MEDIUM`

**Historical evidence:** RateLimit and retention/size values unset; systemd default applies.

**Identified weakness / gap:** Defaults do not demonstrate capacity/retention decisions or behavior under log flood.

**Implementation task:** POLICY REVIEW: bounded retention, rate limits, disk exhaustion

**Core checkpoints:** `KHAHP-23.04A`, `KHAHP-23.04B`, `KHAHP-23.04C`

**Source / evidence status:** 23-journald-logging-logrotate-sysmaint-20261012-215459.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 23.05 — Forwarding/syslog integration state

**Stage / source classification:** `S3 / MEDIUM`

**Historical evidence:** ForwardToSyslog=yes while rsyslog/syslog-ng and syslog socket absent.

**Identified weakness / gap:** No external syslog consumer; no evidence of remote durable forwarding. May be intentional journald-only design.

**Implementation task:** DECIDE journald-only vs configured forwarding; avoid false remote-log claim

**Core checkpoints:** `KHAHP-23.05A`, `KHAHP-23.05B`, `KHAHP-23.05C`

**Source / evidence status:** 23-journald-logging-logrotate-sysmaint-20261012-215459.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 23.06 — logrotate configuration and sensitive- log modes

**Stage / source classification:** `S3 / MEDIUM`

**Historical evidence:** Logrotate snippets root-owned and protected; sensitive lastlog/wtmp/btmp modes acceptable.

**Identified weakness / gap:** logrotate binary and timer/service absent: existing snippets are not evidence they execute; rotation may be handled by other services.

**Implementation task:** REVIEW LEGACY LOG GROWTH / ROTATION; install only if needed

**Core checkpoints:** `KHAHP-23.06A`, `KHAHP-23.06B`, `KHAHP-23.06C`

**Source / evidence status:** 23-journald-logging-logrotate-sysmaint-20261012-215459.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 23.07 — Log integrity, time coherence and reboot persistence

**Stage / source classification:** `S3 / LOW`

**Historical evidence:** journalctl --verify succeeded; sdwdate and journald active; multiple boot records.

**Identified weakness / gap:** Journal integrity verification is not tamper-evident off-host storage; drift after updates not tested here.

**Implementation task:** RETAIN, LINK SECURE TIME AND AUDITD

**Core checkpoints:** `KHAHP-23.07A`, `KHAHP-23.07B`, `KHAHP-23.07C`

**Source / evidence status:** 23-journald-logging-logrotate-sysmaint-20261012-215459.txt | NOT SIGNED OFF AT ASSERTION LEVEL

---

## 24 — Panic / Recovery / Emergency Shutdown

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 24.01 — kernel panic-on-oops policy

**Stage / source classification:** `S2 / HIGH`

**Historical evidence:** panic-on-oops helper/unit present; runtime oops_limit=10000 and warn_limit=0 in SYSMAINT; service disabled/inactive.

**Identified weakness / gap:** Differs from helper intended 1/1; may be deliberate SYSMAINT split or operational choice.

**Implementation task:** PRIORITY TARGETED REVIEW: USER and SYSMAINT policy before any change

**Core checkpoints:** `KHAHP-24.01A`, `KHAHP-24.01B`, `KHAHP-24.01C`

**Source / evidence status:** 24-panic-recovery-emergency-shutdown-sysmaint-20261012-220203.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 24.02 — panic timeout and fail-closed behavior

**Stage / source classification:** `S2 / LOW`

**Historical evidence:** kernel.panic=-1 observed (immediate reboot after panic).

**Identified weakness / gap:** No deliberate kernel panic triggered; DoS/recovery behavior only inferred from policy.

**Implementation task:** RETAIN; safety-reviewed recovery test only

**Core checkpoints:** `KHAHP-24.02A`, `KHAHP-24.02B`, `KHAHP-24.02C`

**Source / evidence status:** 24-panic-recovery-emergency-shutdown-sysmaint-20261012-220203.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 24.03 — emerg-shutdown.service provenance and state

**Stage / source classification:** `S2 / MEDIUM`

**Historical evidence:** emerg-shutdown service package-owned and active/enabled in SYSMAINT; udev keyboard hooks present.

**Identified weakness / gap:** No trigger test; unexpected physical event must not brick customer systems.

**Implementation task:** RETAIN with recovery/physical tests

**Core checkpoints:** `KHAHP-24.03A`, `KHAHP-24.03B`, `KHAHP-24.03C`

**Source / evidence status:** 24-panic-recovery-emergency-shutdown-sysmaint-20261012-220203.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 24.04 — rescue/emergency target restrictions

**Stage / source classification:** `S2 / LOW`

**Historical evidence:** Rescue/emergency target overrides set SYSTEMD_SULOGIN_FORCE=1; root password locked.

**Identified weakness / gap:** Emergency target admission not tested; avoid entering emergency.target on live hardware.

**Implementation task:** RETAIN; controlled recovery validation

**Core checkpoints:** `KHAHP-24.04A`, `KHAHP-24.04B`, `KHAHP-24.04C`

**Source / evidence status:** 24-panic-recovery-emergency-shutdown-sysmaint-20261012-220203.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 24.05 — rd.emergency=halt and rd.shell=0 behavior

**Stage / source classification:** `S2 / LOW`

**Historical evidence:** GRUB_DISABLE_RECOVERY=true; rd.emergency=halt and rd.shell=0 present in live boot args.

**Identified weakness / gap:** Source/boot tokens tested, not all physical bypass scenarios.

**Implementation task:** RETAIN / CROSS-LINK BOOT CONTROLS

**Core checkpoints:** `KHAHP-24.05A`, `KHAHP-24.05B`, `KHAHP-24.05C`

**Source / evidence status:** 24-panic-recovery-emergency-shutdown-sysmaint-20261012-220203.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 24.06 — Magic SysRq and recovery-surface policy

**Stage / source classification:** `S2 / LOW`

**Historical evidence:** kernel.sysrq=0 effective; no rescue/emergency argument in current boot.

**Identified weakness / gap:** No intentional SysRq crash invoked.

**Implementation task:** RETAIN; no destructive test without recovery plan

**Core checkpoints:** `KHAHP-24.06A`, `KHAHP-24.06B`, `KHAHP-24.06C`

**Source / evidence status:** 24-panic-recovery-emergency-shutdown-sysmaint-20261012-220203.txt | NOT SIGNED OFF AT ASSERTION LEVEL

### 24.07 — Controlled failure/recovery evidence and rollback

**Stage / source classification:** `S2 / MEDIUM`

**Historical evidence:** Rollback source components inventoried; current boot running with 0 failed units.

**Identified weakness / gap:** Full destructive recovery/restore behavior deferred; needs backup, media, physical access.

**Implementation task:** DOCUMENT CONTROLLED RECOVERY EXCEPTION/TEST PLAN

**Core checkpoints:** `KHAHP-24.07A`, `KHAHP-24.07B`, `KHAHP-24.07C`

**Source / evidence status:** 24-panic-recovery-emergency-shutdown-sysmaint-20261012-220203.txt | NOT SIGNED OFF AT ASSERTION LEVEL

---

## 25 — RAM Wipe

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 25.01 — ram-wipe package provenance and version

**Stage / source classification:** `S2 / P3`

**Historical evidence:** ram-wipe 3:4.6-1 and attributable hooks present; package state only.

**Identified weakness / gap:** Record package/version in image build manifest; test update impact.

**Implementation task:** Record package/version in image build manifest; test update impact.

**Core checkpoints:** `KHAHP-25.01A`, `KHAHP-25.01B`, `KHAHP-25.01C`

**Source / evidence status:** 25-ram-wipe-sysmaint-20261012-221816.txt:L43-L60 | RETAIN / regression

### 25.02 — GRUB ram-wipe fragment presence

**Stage / source classification:** `S2 / P3`

**Historical evidence:** GRUB fragment present, wiperam=skip commented out; live skip absent.

**Identified weakness / gap:** Preserve fragment; test resulting installed image, not merely source.

**Implementation task:** Preserve fragment; test resulting installed image, not merely source.

**Core checkpoints:** `KHAHP-25.02A`, `KHAHP-25.02B`, `KHAHP-25.02C`

**Source / evidence status:** 25-ram-wipe-sysmaint-20261012-221816.txt:L63-L81 | RETAIN / regression

### 25.03 — init_on_alloc/init_on_free correlation

**Stage / source classification:** `S2 / P3`

**Historical evidence:** Both init_on_alloc=1 and init_on_free=1 present on running cmdline; no unknown-param warnings.

**Identified weakness / gap:** Keep with kernel upgrade regression; boot flags are not complete memory-wipe proof.

**Implementation task:** Keep with kernel upgrade regression; boot flags are not complete memory-wipe proof.

**Core checkpoints:** `KHAHP-25.03A`, `KHAHP-25.03B`, `KHAHP-25.03C`

**Source / evidence status:** 25-ram-wipe-sysmaint-20261012-221816.txt:L84-L92 | RETAIN / regression

### 25.04 — Shutdown/reboot wipe service or hook inventory

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Dracut ram-wipe hooks are listed in current initramfs, but actual shutdown execution is unobserved.

**Identified weakness / gap:** Use controlled staging reboot with console evidence and recovery readiness.

**Implementation task:** Use controlled staging reboot with console evidence and recovery readiness.

**Core checkpoints:** `KHAHP-25.04A`, `KHAHP-25.04B`, `KHAHP-25.04C`

**Source / evidence status:** 25-ram-wipe-sysmaint-20261012-221816.txt:L95-L137 | RETEST MANUAL

### 25.05 — Swap/LUKS interaction during shutdown

**Stage / source classification:** `S2 / P3`

**Historical evidence:** Root LUKS mapping and swap file on encrypted root observed; shutdown hook checks for crypt mappings.

**Identified weakness / gap:** Preserve encrypted swap; do not equate hooks with measured memory sanitization.

**Implementation task:** Preserve encrypted swap; do not equate hooks with measured memory sanitization.

**Core checkpoints:** `KHAHP-25.05A`, `KHAHP-25.05B`, `KHAHP-25.05C`

**Source / evidence status:** 25-ram-wipe-sysmaint-20261012-221816.txt:L140-L160 | RETAIN / verify

### 25.06 — Controlled reboot/shutdown persistence test

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Previous-boot RAM-wipe messages = 0; no controlled shutdown test executed.

**Identified weakness / gap:** Perform supervised test only with owner authorization; not an automatic remediation.

**Implementation task:** Perform supervised test only with owner authorization; not an automatic remediation.

**Core checkpoints:** `KHAHP-25.06A`, `KHAHP-25.06B`, `KHAHP-25.06C`

**Source / evidence status:** 25-ram-wipe-sysmaint-20261012-221816.txt:L163-L182 | RETEST MANUAL

### 25.07 — Limitations of software RAM wiping and cold-boot scope

**Stage / source classification:** `S2 / P3`

**Historical evidence:** Report explicitly limits cold-boot claims; sudden loss, device RAM, live keys are not covered.

**Identified weakness / gap:** Publish hardware/physical attack limitations in release threat model.

**Implementation task:** Publish hardware/physical attack limitations in release threat model.

**Core checkpoints:** `KHAHP-25.07A`, `KHAHP-25.07B`, `KHAHP-25.07C`

**Source / evidence status:** 25-ram-wipe-sysmaint-20261012-221816.txt:L184-L209 | DOCUMENT EXCEPTION

---

## 26 — USBGuard / Peripheral Security

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 26.01 — usbguard daemon and DBus service state

**Stage / source classification:** `S3 / P3`

**Historical evidence:** USBGuard and D-Bus services active and enabled in SYSMAINT and USER.

**Identified weakness / gap:** Preserve active service; add real physical insertion test.

**Implementation task:** Preserve active service; add real physical insertion test.

**Core checkpoints:** `KHAHP-26.01A`, `KHAHP-26.01B`, `KHAHP-26.01C`

**Source / evidence status:** 26-usbguard-peripheral-security-sysmaint-20261012-224526.txt:L36-L60 | 26-usbguard-peripheral-security-user-20261012- 225114.txt:L31-L56 | RETAIN / test

### 26.02 — Policy files and rule provenance

**Stage / source classification:** `S3 / P1`

**Historical evidence:** Root-only USBGuard policy files 0600, 32 effective rules reported, yet allow/block/reject rule counters all 0.

**Identified weakness / gap:** Reconcile list-rules output format/counting; do not infer rules absent or enforcement complete.

**Implementation task:** Reconcile list-rules output format/counting; do not infer rules absent or enforcement complete.

**Core checkpoints:** `KHAHP-26.02A`, `KHAHP-26.02B`, `KHAHP-26.02C`

**Source / evidence status:** 26-usbguard-peripheral-security-sysmaint-20261012-224526.txt:L62-L110 | REVIEW PARSER

### 26.03 — ImplicitPolicyTarget and device-policy settings

**Stage / source classification:** `S3 / P1`

**Historical evidence:** Configured implicit block, inserted apply-policy, authorized default none; present-device policy is allow.

**Identified weakness / gap:** Test daemon restart with pre-attached forbidden devices; decide startup policy and rollback.

**Implementation task:** Test daemon restart with pre-attached forbidden devices; decide startup policy and rollback.

**Core checkpoints:** `KHAHP-26.03A`, `KHAHP-26.03B`, `KHAHP-26.03C`

**Source / evidence status:** 26-usbguard-peripheral-security-sysmaint-20261012-224526.txt:L99-L127 | RISK REVIEW

### 26.04 — Allowed keyboard/mouse/audio/video/storage classes

**Stage / source classification:** `S3 / P1`

**Historical evidence:** Class allow rules include mouse, keyboard, audio, video, storage, hub; keyboard is not blanket- blocked.

**Identified weakness / gap:** Confirm whether keyboard allowances conflict with requirement to reject unauthorized external keyboards; physically test.

**Implementation task:** Confirm whether keyboard allowances conflict with requirement to reject unauthorized external keyboards; physically test.

**Core checkpoints:** `KHAHP-26.04A`, `KHAHP-26.04B`, `KHAHP-26.04C`

**Source / evidence status:** 26-usbguard-peripheral-security-sysmaint-20261012-224526.txt:L126-L158 | POLICY DECISION

### 26.05 — Rejected HID+extra and RNDIS/network-device patterns

**Stage / source classification:** `S3 / P1`

**Historical evidence:** Reject patterns for mixed HID+other and ef:04:* were found in source; USB Ethernet/phone coverage not proven universally.

**Identified weakness / gap:** Test representative phone/RNDIS/USB-Ethernet and composite devices; verify actual reject decisions.

**Implementation task:** Test representative phone/RNDIS/USB-Ethernet and composite devices; verify actual reject decisions.

**Core checkpoints:** `KHAHP-26.05A`, `KHAHP-26.05B`, `KHAHP-26.05C`

**Source / evidence status:** 26-usbguard-peripheral-security-sysmaint-20261012-224526.txt:L159-L195 | RETEST MANUAL

### 26.06 — IPC authorization/notifier behavior

**Stage / source classification:** `S3 / P2`

**Historical evidence:** USER cannot list rules but can list devices; notifier active; SYSMAINT root/plugdev IPC permissions exist.

**Identified weakness / gap:** Review whether USER device visibility and plugdev/sudo ACLs match threat model.

**Implementation task:** Review whether USER device visibility and plugdev/sudo ACLs match threat model.

**Core checkpoints:** `KHAHP-26.06A`, `KHAHP-26.06B`, `KHAHP-26.06C`

**Source / evidence status:** 26-usbguard-peripheral-security-user-20261012-225114.txt:L72-L130 | 26-usbguard-peripheral-security-sysmaint-20261012- 224526.txt:L196-L223 | LEAST-PRIVILEGE REVIEW

### 26.07 — Hot-plug negative tests and reboot persistence

**Stage / source classification:** `S3 / P1`

**Historical evidence:** No physical hot-plug denial test or post-reboot insertion validation performed in either context.

**Identified weakness / gap:** Test USB keyboard, mouse, storage, phone, network adapter and composite device; retest after reboot.

**Implementation task:** Test USB keyboard, mouse, storage, phone, network adapter and composite device; retest after reboot.

**Core checkpoints:** `KHAHP-26.07A`, `KHAHP-26.07B`, `KHAHP-26.07C`

**Source / evidence status:** 26-usbguard-peripheral-security-sysmaint-20261012-224526.txt:L224-L257 | 26-usbguard-peripheral-security-user-20261012- 225114.txt:L131-L169 | RETEST MANUAL

---

## 27 — NetworkManager / Wi-Fi / MAC / DHCP

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 27.01 — NetworkManager package/service state

**Stage / source classification:** `S4 / P3`

**Historical evidence:** NetworkManager installed, active and enabled in USER.

**Identified weakness / gap:** Keep; apply privacy profiles on clean build and after updates.

**Implementation task:** Keep; apply privacy profiles on clean build and after updates.

**Core checkpoints:** `KHAHP-27.01A`, `KHAHP-27.01B`, `KHAHP-27.01C`

**Source / evidence status:** 27-networkmanager-wifi-mac-dhcp-user-20261012-230746.txt:L25-L30 | RETAIN / regression

### 27.02 — Saved Wi-Fi profile inventory and autoconnect

**Stage / source classification:** `S4 / P2`

**Historical evidence:** Two saved Wi-Fi profiles both have autoconnect=yes.

**Identified weakness / gap:** Choose privacy/usability behavior; prevent exporting these profiles to commercial image.

**Implementation task:** Choose privacy/usability behavior; prevent exporting these profiles to commercial image.

**Core checkpoints:** `KHAHP-27.02A`, `KHAHP-27.02B`, `KHAHP-27.02C`

**Source / evidence status:** 27-networkmanager-wifi-mac-dhcp-user-20261012-230746.txt:L54-L60 | POLICY DECISION

### 27.03 — Wi-Fi cloned-MAC randomization

**Stage / source classification:** `S4 / P3`

**Historical evidence:** Both Wi-Fi profiles explicitly use cloned-mac-address=random.

**Identified weakness / gap:** Verify effective address across fresh reconnects without recording raw MACs.

**Implementation task:** Verify effective address across fresh reconnects without recording raw MACs.

**Core checkpoints:** `KHAHP-27.03A`, `KHAHP-27.03B`, `KHAHP-27.03C`

**Source / evidence status:** 27-networkmanager-wifi-mac-dhcp-user-20261012-230746.txt:L63-L69 | RETAIN / test

### 27.04 — Scan MAC randomization

**Stage / source classification:** `S4 / P1`

**Historical evidence:** Effective config dump contains wifi.scan-rand-mac-address=yes and device-31-mac-addr-change=no; verifier simply reports yes.

**Identified weakness / gap:** Determine which setting applies to wlan0/scans; do not claim scan privacy fully proven yet.

**Implementation task:** Determine which setting applies to wlan0/scans; do not claim scan privacy fully proven yet.

**Core checkpoints:** `KHAHP-27.04A`, `KHAHP-27.04B`, `KHAHP-27.04C`

**Source / evidence status:** 27-networkmanager-wifi-mac-dhcp-user-20261012-230746.txt:L33-L51 | 27-networkmanager-wifi-mac-dhcp-user-20261012- 230746.txt:L72-L75 | CONFIG CONFLICT REVIEW

### 27.05 — Ethernet MAC randomization policy

**Stage / source classification:** `S4 / P2`

**Historical evidence:** Global Ethernet randomized MAC policy is set, but no saved Ethernet profile exists.

**Identified weakness / gap:** Test after Ethernet adapter added; ensure USBGuard and NM policies agree.

**Implementation task:** Test after Ethernet adapter added; ensure USBGuard and NM policies agree.

**Core checkpoints:** `KHAHP-27.05A`, `KHAHP-27.05B`, `KHAHP-27.05C`

**Source / evidence status:** 27-networkmanager-wifi-mac-dhcp-user-20261012-230746.txt:L78-L82 | NEEDS RUNTIME TEST

### 27.06 — Runtime MAC versus permanent hardware MAC

**Stage / source classification:** `S4 / P2`

**Historical evidence:** Runtime MAC was captured as hash; permanent hardware MAC unavailable; addr_assign_type=3 reported.

**Identified weakness / gap:** Compare actual policy without exposing identifiers; cannot prove runtime differs from permanent by this report.

**Implementation task:** Compare actual policy without exposing identifiers; cannot prove runtime differs from permanent by this report.

**Core checkpoints:** `KHAHP-27.06A`, `KHAHP-27.06B`, `KHAHP-27.06C`

**Source / evidence status:** 27-networkmanager-wifi-mac-dhcp-user-20261012-230746.txt:L85-L89 | NEEDS RUNTIME TEST

### 27.07 — DHCP client identifier and profile persistence

**Stage / source classification:** `S4 / P2`

**Historical evidence:** Both DHCP client-id settings unset; no explicit permanent-MAC ID, but server-visible ID and hostname not captured.

**Identified weakness / gap:** Verify default DHCP semantics and reconnect variability on test network.

**Implementation task:** Verify default DHCP semantics and reconnect variability on test network.

**Core checkpoints:** `KHAHP-27.07A`, `KHAHP-27.07B`, `KHAHP-27.07C`

**Source / evidence status:** 27-networkmanager-wifi-mac-dhcp-user-20261012-230746.txt:L92-L107 | PRIVACY POLICY REVIEW

---

## 28 — IPv6 Elimination

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 28.01 — ipv6.disable=1 boot parameter

**Stage / source classification:** `S4 / P3`

**Historical evidence:** Kernel ipv6.disable=1 configured and present in both roles.

**Identified weakness / gap:** Verify physical and VM image each apply same deliberate IPv6 policy.

**Implementation task:** Verify physical and VM image each apply same deliberate IPv6 policy.

**Core checkpoints:** `KHAHP-28.01A`, `KHAHP-28.01B`, `KHAHP-28.01C`

**Source / evidence status:** 28-ipv6-elimination-user-20261012-231413.txt:L25-L36 | 28-ipv6-elimination-sysmaint-20261012-231704.txt:L25-L36 | RETAIN / build gate

### 28.02 — Absence of IPv6 addresses

**Stage / source classification:** `S4 / P3`

**Historical evidence:** Zero IPv6 addresses in both context reports.

**Identified weakness / gap:** Regression after interface and kernel changes.

**Implementation task:** Regression after interface and kernel changes.

**Core checkpoints:** `KHAHP-28.02A`, `KHAHP-28.02B`, `KHAHP-28.02C`

**Source / evidence status:** 28-ipv6-elimination-user-20261012-231413.txt:L39-L43 | 28-ipv6-elimination-sysmaint-20261012-231704.txt:L39-L43 | RETAIN / regression

### 28.03 — Absence of IPv6 routes

**Stage / source classification:** `S4 / P3`

**Historical evidence:** Zero IPv6 routes in both contexts.

**Identified weakness / gap:** Retest image/new network profiles.

**Implementation task:** Retest image/new network profiles.

**Core checkpoints:** `KHAHP-28.03A`, `KHAHP-28.03B`, `KHAHP-28.03C`

**Source / evidence status:** 28-ipv6-elimination-user-20261012-231413.txt:L46-L49 | 28-ipv6-elimination-sysmaint-20261012-231704.txt:L46-L49 | RETAIN / regression

### 28.04 — NetworkManager IPv6 method/state

**Stage / source classification:** `S4 / P2`

**Historical evidence:** Both saved Wi-Fi profiles retain ipv6.method=auto while IPv6 disabled at kernel level.

**Identified weakness / gap:** Consider defense-in-depth profile policy if kernel flag is ever lost; no present IPv6 exposure shown.

**Implementation task:** Consider defense-in-depth profile policy if kernel flag is ever lost; no present IPv6 exposure shown.

**Core checkpoints:** `KHAHP-28.04A`, `KHAHP-28.04B`, `KHAHP-28.04C`

**Source / evidence status:** 28-ipv6-elimination-user-20261012-231413.txt:L52-L58 | FALLBACK CONFIG REVIEW

### 28.05 — Resolver absence of IPv6 nameservers

**Stage / source classification:** `S4 / P3`

**Historical evidence:** No IPv6 resolver nameserver; NM IP6.DNS empty in both roles.

**Identified weakness / gap:** Retest on new networks/profiles.

**Implementation task:** Retest on new networks/profiles.

**Core checkpoints:** `KHAHP-28.05A`, `KHAHP-28.05B`, `KHAHP-28.05C`

**Source / evidence status:** 28-ipv6-elimination-user-20261012-231413.txt:L61-L67 | RETAIN / regression

### 28.06 — IPv6 listener/socket exposure

**Stage / source classification:** `S4 / P3`

**Historical evidence:** No IPv6 listener; IPv6 sysctl tree absent in both roles.

**Identified weakness / gap:** Check after kernel/bootloader updates.

**Implementation task:** Check after kernel/bootloader updates.

**Core checkpoints:** `KHAHP-28.06A`, `KHAHP-28.06B`, `KHAHP-28.06C`

**Source / evidence status:** 28-ipv6-elimination-user-20261012-231413.txt:L70-L74 | RETAIN / regression

### 28.07 — Reboot persistence and DNS/HTTPS regression test

**Stage / source classification:** `S4 / P2`

**Historical evidence:** Kernel source/runtime agrees between two boot roles; USER DNS and HTTPS work.

**Identified weakness / gap:** Do not treat retained boot-count alone as a two-boot drift comparison.

**Implementation task:** Do not treat retained boot-count alone as a two-boot drift comparison.

**Core checkpoints:** `KHAHP-28.07A`, `KHAHP-28.07B`, `KHAHP-28.07C`

**Source / evidence status:** 28-ipv6-elimination-user-20261012-231413.txt:L77-L86 | 28-ipv6-elimination-sysmaint-20261012-231704.txt:L77-L84 | PERSISTENCE EVIDENCE REVIEW

---

## 29 — Unbound / Local DNS Architecture

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 29.01 — Unbound package/service state

**Stage / source classification:** `S4 / P3`

**Historical evidence:** Unbound active and enabled in USER; Section 30 also explicitly found Unbound active in SYSMAINT.

**Identified weakness / gap:** Prior summary describing SYSMAINT as inactive is not accurate for this recorded snapshot.

**Implementation task:** Prior summary describing SYSMAINT as inactive is not accurate for this recorded snapshot.

**Core checkpoints:** `KHAHP-29.01A`, `KHAHP-29.01B`, `KHAHP-29.01C`

**Source / evidence status:** 29-unbound-local-dns-architecture-user-20261013-000557.txt:L26-L37 | 30-dnssec-dot-dns-leak-prevention-sysmaint-20261013- 001818.txt:L26-L30 | RETAIN / regression

### 29.02 — 127.0.0.1:53 UDP/TCP listener

**Stage / source classification:** `S4 / P3`

**Historical evidence:** UDP/TCP Unbound listeners on 127.0.0.1:53; no nonloopback port 53 endpoints.

**Identified weakness / gap:** Test application paths and other DNS transports separately.

**Implementation task:** Test application paths and other DNS transports separately.

**Core checkpoints:** `KHAHP-29.02A`, `KHAHP-29.02B`, `KHAHP-29.02C`

**Source / evidence status:** 29-unbound-local-dns-architecture-user-20261013-000557.txt:L40-L47 | RETAIN / test

### 29.03 — resolv.conf local-resolver wiring

**Stage / source classification:** `S4 / P3`

**Historical evidence:** USER /etc/resolv.conf nameserver exclusively 127.0.0.1.

**Identified weakness / gap:** Retest after DHCP lease/reconnect to avoid leak regressions.

**Implementation task:** Retest after DHCP lease/reconnect to avoid leak regressions.

**Core checkpoints:** `KHAHP-29.03A`, `KHAHP-29.03B`, `KHAHP-29.03C`

**Source / evidence status:** 29-unbound-local-dns-architecture-user-20261013-000557.txt:L50-L54 | RETAIN / reconnect test

### 29.04 — NetworkManager DNS assignment

**Stage / source classification:** `S4 / P3`

**Historical evidence:** USER NetworkManager IP4.DNS solely 127.0.0.1.

**Identified weakness / gap:** Test when different network hands out DNS.

**Implementation task:** Test when different network hands out DNS.

**Core checkpoints:** `KHAHP-29.04A`, `KHAHP-29.04B`, `KHAHP-29.04C`

**Source / evidence status:** 29-unbound-local-dns-architecture-user-20261013-000557.txt:L57-L61 | RETAIN / reconnect test

### 29.05 — Unbound configuration include tree

**Stage / source classification:** `S4 / P3`

**Historical evidence:** Unbound-checkconf succeeds; 4 includes listed.

**Identified weakness / gap:** Review package include update semantics/anchors, not blanket reconfigure.

**Implementation task:** Review package include update semantics/anchors, not blanket reconfigure.

**Core checkpoints:** `KHAHP-29.05A`, `KHAHP-29.05B`, `KHAHP-29.05C`

**Source / evidence status:** 29-unbound-local-dns-architecture-user-20261013-000557.txt:L64-L73 | RETAIN / config review

### 29.06 — Quad9 forward-zone and TLS hostname configuration

**Stage / source classification:** `S4 / P3`

**Historical evidence:** TLS forward upstream configured with two Quad9 endpoints, direct and system queries pass.

**Identified weakness / gap:** Does not alone prove forbidden fallback impossible; cross-check Section 30.

**Implementation task:** Does not alone prove forbidden fallback impossible; cross-check Section 30.

**Core checkpoints:** `KHAHP-29.06A`, `KHAHP-29.06B`, `KHAHP-29.06C`

**Source / evidence status:** 29-unbound-local-dns-architecture-user-20261013-000557.txt:L76-L82 | RETAIN / denial test

### 29.07 — USER/SYSMAINT service behavior and persistence

**Stage / source classification:** `S4 / P2`

**Historical evidence:** SYSMAINT WantedBy override exists; contemporaneous Section 30 SYSMAINT report says Unbound active.

**Identified weakness / gap:** Clarify exact expected SYSMAINT behavior at approved baseline; no service change from stale assumption.

**Implementation task:** Clarify exact expected SYSMAINT behavior at approved baseline; no service change from stale assumption.

**Core checkpoints:** `KHAHP-29.07A`, `KHAHP-29.07B`, `KHAHP-29.07C`

**Source / evidence status:** 29-unbound-local-dns-architecture-user-20261013-000557.txt:L85-L95 | 30-dnssec-dot-dns-leak-prevention-sysmaint-20261013- 001818.txt:L26-L30 | ROLE RECONCILIATION

---

## 30 — DNSSEC / DoT / DNS Leak Prevention

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 30.01 — DNSSEC positive validation test

**Stage / source classification:** `S4 / P3`

**Historical evidence:** AD flag=1 in both USER and SYSMAINT for signed-domain probe.

**Identified weakness / gap:** Maintain combined positive and negative validator tests.

**Implementation task:** Maintain combined positive and negative validator tests.

**Core checkpoints:** `KHAHP-30.01A`, `KHAHP-30.01B`, `KHAHP-30.01C`

**Source / evidence status:** 30-dnssec-dot-dns-leak-prevention-user-20261013-001519.txt:L44-L47 | 30-dnssec-dot-dns-leak-prevention-sysmaint-20261013- 001818.txt:L44-L47 | RETAIN / regression

### 30.02 — Broken-DNSSEC negative test

**Stage / source classification:** `S4 / P1`

**Historical evidence:** USER negative test returned status=none after TCP retry; SYSMAINT got SERVFAIL.

**Identified weakness / gap:** Different role/boot outcome; USER still inconclusive, not a confirmed DNSSEC bypass.

**Implementation task:** Different role/boot outcome; USER still inconclusive, not a confirmed DNSSEC bypass.

**Core checkpoints:** `KHAHP-30.02A`, `KHAHP-30.02B`, `KHAHP-30.02C`

**Source / evidence status:** 30-dnssec-dot-dns-leak-prevention-user-20261013-001519.txt:L50-L54 | 30-dnssec-dot-dns-leak-prevention-sysmaint-20261013- 001818.txt:L50-L53 | USER RETEST

### 30.03 — DoT TCP/853 forwarder reachability

**Stage / source classification:** `S4 / P1`

**Historical evidence:** SYSMAINT passed both Quad9 DoT endpoints; USER passed 149.112.112.112 but failed 9.9.9.9.

**Identified weakness / gap:** Diagnose route/forwarder reachability before changing upstreams.

**Implementation task:** Diagnose route/forwarder reachability before changing upstreams.

**Core checkpoints:** `KHAHP-30.03A`, `KHAHP-30.03B`, `KHAHP-30.03C`

**Source / evidence status:** 30-dnssec-dot-dns-leak-prevention-user-20261013-001519.txt:L56-L59 | 30-dnssec-dot-dns-leak-prevention-sysmaint-20261013- 001818.txt:L56-L59 | USER CONNECTIVITY REVIEW

### 30.04 — Plaintext external UDP/53 block

**Stage / source classification:** `S4 / P2`

**Historical evidence:** External UDP/53 query to 8.8.8.8 got no reply in both roles and SYSMAINT nft source blocks it.

**Identified weakness / gap:** A single blocked path is not blanket prevention of all DNS leaks.

**Implementation task:** A single blocked path is not blanket prevention of all DNS leaks.

**Core checkpoints:** `KHAHP-30.04A`, `KHAHP-30.04B`, `KHAHP-30.04C`

**Source / evidence status:** 30-dnssec-dot-dns-leak-prevention-user-20261013-001519.txt:L67-L70 | 30-dnssec-dot-dns-leak-prevention-sysmaint-20261013- 001818.txt:L63-L74 | RETAIN / extended bypass test

### 30.05 — Plaintext external TCP/53 block

**Stage / source classification:** `S4 / P2`

**Historical evidence:** External TCP/53 query to 8.8.8.8 got no reply in both roles and SYSMAINT nft source blocks it.

**Identified weakness / gap:** DoH over 443 or alternative transports remain outside this negative test.

**Implementation task:** DoH over 443 or alternative transports remain outside this negative test.

**Core checkpoints:** `KHAHP-30.05A`, `KHAHP-30.05B`, `KHAHP-30.05C`

**Source / evidence status:** 30-dnssec-dot-dns-leak-prevention-user-20261013-001519.txt:L72-L75 | 30-dnssec-dot-dns-leak-prevention-sysmaint-20261013- 001818.txt:L63-L79 | RETAIN / extended bypass test

### 30.06 — Local DNS functionality after firewall enforcement

**Stage / source classification:** `S4 / P3`

**Historical evidence:** Local UDP/TCP DNS and IPv4 HTTPS continue working in both roles.

**Identified weakness / gap:** Add browser DoH and direct DNS application bypass tests where relevant.

**Implementation task:** Add browser DoH and direct DNS application bypass tests where relevant.

**Core checkpoints:** `KHAHP-30.06A`, `KHAHP-30.06B`, `KHAHP-30.06C`

**Source / evidence status:** 30-dnssec-dot-dns-leak-prevention-user-20261013-001519.txt:L77-L88 | 30-dnssec-dot-dns-leak-prevention-sysmaint-20261013- 001818.txt:L82-L87 | RETAIN / application test

### 30.07 — DNS leak/bypass and reboot- persistence testing

**Stage / source classification:** `S4 / P1`

**Historical evidence:** Only loopback resolver/NM wiring and boot history verified; no full browser DoH/VPN/Tor DNS leak coverage.

**Identified weakness / gap:** Define app-specific leak tests and customer-image network isolation limits.

**Implementation task:** Define app-specific leak tests and customer-image network isolation limits.

**Core checkpoints:** `KHAHP-30.07A`, `KHAHP-30.07B`, `KHAHP-30.07C`

**Source / evidence status:** 30-dnssec-dot-dns-leak-prevention-user-20261013-001519.txt:L91-L100 | 31-nftables-firewall-sysmaint-20261013-002330.txt:L93-L97 | NEGATIVE TEST GAP

---

## 31 — nftables Firewall

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 31.01 — nftables package/service state

**Stage / source classification:** `S4 / P3`

**Historical evidence:** nftables installed and enabled and active in SYSMAINT.

**Identified weakness / gap:** Verify USER live rule state for acceptance.

**Implementation task:** Verify USER live rule state for acceptance.

**Core checkpoints:** `KHAHP-31.01A`, `KHAHP-31.01B`, `KHAHP-31.01C`

**Source / evidence status:** 31-nftables-firewall-sysmaint-20261013-002330.txt:L29-L42 | RETAIN / regression

### 31.02 — Dedicated inet kicksecure_hardening table

**Stage / source classification:** `S4 / P2`

**Historical evidence:** inet kicksecure_hardening table and base chains exist.

**Identified weakness / gap:** Assess interplay with other nftables tables and output chains in both roles.

**Implementation task:** Assess interplay with other nftables tables and output chains in both roles.

**Core checkpoints:** `KHAHP-31.02A`, `KHAHP-31.02B`, `KHAHP-31.02C`

**Source / evidence status:** 31-nftables-firewall-sysmaint-20261013-002330.txt:L45-L52 | RETAIN / full ruleset review

### 31.03 — Input default-drop policy

**Stage / source classification:** `S4 / P3`

**Historical evidence:** Input base-chain policy drop.

**Identified weakness / gap:** Staged ingress packet-test after interface changes.

**Implementation task:** Staged ingress packet-test after interface changes.

**Core checkpoints:** `KHAHP-31.03A`, `KHAHP-31.03B`, `KHAHP-31.03C`

**Source / evidence status:** 31-nftables-firewall-sysmaint-20261013-002330.txt:L55-L59 | RETAIN / negative test

### 31.04 — Forward default-drop policy

**Stage / source classification:** `S4 / P3`

**Historical evidence:** Forward base-chain policy drop.

**Identified weakness / gap:** VM bridge/NAT networking must have separately tested policy.

**Implementation task:** VM bridge/NAT networking must have separately tested policy.

**Core checkpoints:** `KHAHP-31.04A`, `KHAHP-31.04B`, `KHAHP-31.04C`

**Source / evidence status:** 31-nftables-firewall-sysmaint-20261013-002330.txt:L62-L66 | RETAIN / VM PROFILE

### 31.05 — Loopback, established/related and invalid handling

**Stage / source classification:** `S4 / P3`

**Historical evidence:** Loopback and established accepted, invalid dropped, 127/8 anti-spoof.

**Identified weakness / gap:** Test effect from interfaces not just rule-text matching.

**Implementation task:** Test effect from interfaces not just rule-text matching.

**Core checkpoints:** `KHAHP-31.05A`, `KHAHP-31.05B`, `KHAHP-31.05C`

**Source / evidence status:** 31-nftables-firewall-sysmaint-20261013-002330.txt:L69-L78 | RETAIN / negative test

### 31.06 — DHCP/ICMP and required inbound exceptions

**Stage / source classification:** `S4 / P2`

**Historical evidence:** DHCP and ICMP inbound allowances present.

**Identified weakness / gap:** Validate necessary allowances and safe update on external network.

**Implementation task:** Validate necessary allowances and safe update on external network.

**Core checkpoints:** `KHAHP-31.06A`, `KHAHP-31.06B`, `KHAHP-31.06C`

**Source / evidence status:** 31-nftables-firewall-sysmaint-20261013-002330.txt:L81-L91 | EXCEPTION REVIEW

### 31.07 — Safe reload, no global flush and reboot persistence

**Stage / source classification:** `S4 / P1`

**Historical evidence:** No global flush in local override, nft config syntax good, but output chain policy accept and live reload untested.

**Identified weakness / gap:** Define outbound policy targets, DoH limits, and controlled reload+rollback before edits.

**Implementation task:** Define outbound policy targets, DoH limits, and controlled reload+rollback before edits.

**Core checkpoints:** `KHAHP-31.07A`, `KHAHP-31.07B`, `KHAHP-31.07C`

**Source / evidence status:** 31-nftables-firewall-sysmaint-20261013-002330.txt:L93-L97 | 31-nftables-firewall-sysmaint-20261013-002330.txt:L100-L175 | HIGH-PRIORITY POLICY REVIEW

---

## 32 — LAN Discovery / Multicast / LLMNR / mDNS

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 32.01 — Avahi/mDNS daemon state

**Stage / source classification:** `S4 / LOW`

**Historical evidence:** Avahi package absent and service/socket inactive/not-found in USER and SYSMAINT.

**Identified weakness / gap:** No active multicast probes from a second host.

**Implementation task:** Retest when new network packages are installed.

**Core checkpoints:** `KHAHP-32.01A`, `KHAHP-32.01B`, `KHAHP-32.01C`

**Source / evidence status:** 32-lan-discovery-multicast-llmnr-mdns-sysmaint-20261013-004401.txt:L40-L52; 32-lan-discovery-multicast-llmnr-mdns-user- 20261013-004424.txt:L40-L52 | OBSERVED_PROTECTION

### 32.02 — LLMNR/resolved multicast name- resolution state

**Stage / source classification:** `S4 / MEDIUM`

**Historical evidence:** systemd-resolved inactive; two NetworkManager profiles have no explicit yes for mDNS/LLMNR (both -1).

**Identified weakness / gap:** No packet capture of unsolicited name requests; -1 is not an explicit deny override.

**Implementation task:** Confirm effective NetworkManager defaults and negative LAN response from test host.

**Core checkpoints:** `KHAHP-32.02A`, `KHAHP-32.02B`, `KHAHP-32.02C`

**Source / evidence status:** 32-lan-discovery-multicast-llmnr-mdns-sysmaint-20261013-004401.txt:L48-L60; 32-lan-discovery-multicast-llmnr-mdns-user- 20261013-004424.txt:L48-L60 | PARTIAL_VERIFICATION

### 32.03 — wsdd/Samba discovery state

**Stage / source classification:** `S4 / LOW`

**Historical evidence:** wsdd, wsdd2, SMB/Samba discovery/sharing units inactive/not-found in both roles.

**Identified weakness / gap:** Future installation/activation could alter the condition.

**Implementation task:** Add regression after package updates.

**Core checkpoints:** `KHAHP-32.03A`, `KHAHP-32.03B`, `KHAHP-32.03C`

**Source / evidence status:** 32-lan-discovery-multicast-llmnr-mdns-sysmaint-20261013-004401.txt:L58-L70; 32-lan-discovery-multicast-llmnr-mdns-user- 20261013-004424.txt:L58-L70 | OBSERVED_PROTECTION

### 32.04 — rpcbind/minidlna/UPnP service state

**Stage / source classification:** `S4 / LOW`

**Historical evidence:** rpcbind socket/service, miniDLNA and UPnP services inactive/not-found in both roles.

**Identified weakness / gap:** Reviewed named services, not every possible multicast responder.

**Implementation task:** Maintain service allowlist.

**Core checkpoints:** `KHAHP-32.04A`, `KHAHP-32.04B`, `KHAHP-32.04C`

**Source / evidence status:** 32-lan-discovery-multicast-llmnr-mdns-sysmaint-20261013-004401.txt:L70-L82; 32-lan-discovery-multicast-llmnr-mdns-user- 20261013-004424.txt:L70-L82 | OBSERVED_PROTECTION

### 32.05 — Multicast/broadcast listener inventory

**Stage / source classification:** `S4 / MEDIUM`

**Historical evidence:** Zero listeners on mDNS 5353, LLMNR 5355, SSDP 1900, WSD 3702, NetBIOS 137/138, SMB 445, rpcbind 111 and miniDLNA 8200 in both roles.

**Identified weakness / gap:** Listener snapshot cannot prove silence on all protocols across reconnections.

**Implementation task:** Perform a controlled LAN negative probe and capture; repeat after normal boot.

**Core checkpoints:** `KHAHP-32.05A`, `KHAHP-32.05B`, `KHAHP-32.05C`

**Source / evidence status:** 32-lan-discovery-multicast-llmnr-mdns-sysmaint-20261013-004401.txt:L80-L92; 32-lan-discovery-multicast-llmnr-mdns-user- 20261013-004424.txt:L80-L92 | PARTIAL_VERIFICATION

### 32.06 — Firewall exposure of discovery ports

**Stage / source classification:** `S4 / MEDIUM`

**Historical evidence:** SYSMAINT nftables input default-drop; no discovery-port accept rule; USER report correctly defers privileged firewall inspection.

**Identified weakness / gap:** Firewall policy and listener inventory are not equivalent to packet-level drop proof.

**Implementation task:** Compare effective nftables in normal USER boot using approved privileged probe or external traffic tests.

**Core checkpoints:** `KHAHP-32.06A`, `KHAHP-32.06B`, `KHAHP-32.06C`

**Source / evidence status:** 32-lan-discovery-multicast-llmnr-mdns-sysmaint-20261013-004401.txt:L95-L107; 32-lan-discovery-multicast-llmnr-mdns-user- 20261013-004424.txt:L95-L107 | PARTIAL_VERIFICATION

### 32.07 — Negative LAN discovery and reboot- persistence test

**Stage / source classification:** `S4 / MEDIUM`

**Historical evidence:** Source records 26/49 retained boots with no failed units and current zero discovery listeners.

**Identified weakness / gap:** No active negative LAN discovery probes or same-role reboot regression were performed; marked MANUAL.

**Implementation task:** From controlled peer test each named discovery protocol and re-test after reboot.

**Core checkpoints:** `KHAHP-32.07A`, `KHAHP-32.07B`, `KHAHP-32.07C`

**Source / evidence status:** 32-lan-discovery-multicast-llmnr-mdns-sysmaint-20261013-004401.txt:L103-L115; 32-lan-discovery-multicast-llmnr-mdns-user- 20261013-004424.txt:L100-L112 | MANUAL_ACCEPTANCE

---

## 33 — Tor / SOCKS / Tor DNS Isolation

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 33.01 — Tor package/service state

**Stage / source classification:** `S4 / LOW`

**Historical evidence:** Tor and tor@default.service installed, active in USER, enabled/enabled-runtime.

**Identified weakness / gap:** Tor operation does not imply mandatory use by applications.

**Implementation task:** Recheck after upgrades.

**Core checkpoints:** `KHAHP-33.01A`, `KHAHP-33.01B`, `KHAHP-33.01C`

**Source / evidence status:** 33-tor-socks-dns-isolation-user-20261013-153231.txt:L30-L42 | OBSERVED_PROTECTION

### 33.02 — SOCKS listener 127.0.0.1:9050

**Stage / source classification:** `S4 / LOW`

**Historical evidence:** TCP SOCKS port 9050 on 127.0.0.1 only, non-loopback 9050 count=0.

**Identified weakness / gap:** No other Tor listener exposure checked beyond documented port.

**Implementation task:** Verify unchanged network binding in customer image.

**Core checkpoints:** `KHAHP-33.02A`, `KHAHP-33.02B`, `KHAHP-33.02C`

**Source / evidence status:** 33-tor-socks-dns-isolation-user-20261013-153231.txt:L55-L67 | OBSERVED_PROTECTION

### 33.03 — Tor configuration provenance

**Stage / source classification:** `S4 / LOW`

**Historical evidence:** /etc/tor/torrc and /etc/tor/torsocks.conf are package-owned root:root mode 644 with hashes; no observed unowned config.

**Identified weakness / gap:** Configuration contents not audited for all effective directives or per-application intent.

**Implementation task:** Audit effective Tor config for specific approved use modes without exposing secrets.

**Core checkpoints:** `KHAHP-33.03A`, `KHAHP-33.03B`, `KHAHP-33.03C`

**Source / evidence status:** 33-tor-socks-dns-isolation-user-20261013-153231.txt:L63-L75 | PARTIAL_VERIFICATION

### 33.04 — Application proxy routing where intended

**Stage / source classification:** `S4 / HIGH`

**Historical evidence:** Bounded HTTPS request via socks5-hostname Tor succeeded in USER.

**Identified weakness / gap:** No Tor Browser-like process active; no named application proxy-policy matrix; persistence MANUAL.

**Implementation task:** Identify Tor-required applications and test real app behavior and profile persistence.

**Core checkpoints:** `KHAHP-33.04A`, `KHAHP-33.04B`, `KHAHP-33.04C`

**Source / evidence status:** 33-tor-socks-dns-isolation-user-20261013-153231.txt:L75-L87 | PARTIAL_VERIFICATION

### 33.05 — Tor DNS isolation behavior

**Stage / source classification:** `S4 / MEDIUM`

**Historical evidence:** Tor Check identified the SOCKS hostname route as Tor; remote hostname resolution over SOCKS succeeded.

**Identified weakness / gap:** Proves this controlled route, not every application's DNS isolation.

**Implementation task:** Verify DNS behavior for each Tor-designated application.

**Core checkpoints:** `KHAHP-33.05A`, `KHAHP-33.05B`, `KHAHP-33.05C`

**Source / evidence status:** 33-tor-socks-dns-isolation-user-20261013-153231.txt:L84-L96 | PARTIAL_VERIFICATION

### 33.06 — Clearnet bypass detection for Tor- mode applications

**Stage / source classification:** `S4 / HIGH`

**Historical evidence:** Report explicitly observed a direct HTTPS clearnet/non-Tor path; general host intentionally retains clearnet.

**Identified weakness / gap:** No assertion that all apps are Tor-only is justified; no forced Tor-only bypass-blocking test.

**Implementation task:** Define Tor-only application allowlist and test fail-closed when Tor is unavailable in staging.

**Core checkpoints:** `KHAHP-33.06A`, `KHAHP-33.06B`, `KHAHP-33.06C`

**Source / evidence status:** 33-tor-socks-dns-isolation-user-20261013-153231.txt:L91-L103 | MANUAL_ACCEPTANCE

### 33.07 — Bootstrap, circuit, restart and failure- mode behavior

**Stage / source classification:** `S4 / MEDIUM`

**Historical evidence:** Tor is usable and showed no failed units; retained reboot history present; NRestarts=0.

**Identified weakness / gap:** Stop/restart, bootstrap failure and circuit failure behavior NOT induced.

**Implementation task:** Test Tor outage and restart on disposable VM without weakening reference laptop.

**Core checkpoints:** `KHAHP-33.07A`, `KHAHP-33.07B`, `KHAHP-33.07C`

**Source / evidence status:** 33-tor-socks-dns-isolation-user-20261013-153231.txt:L101-L113 | MANUAL_ACCEPTANCE

---

## 34 — sdwdate / Secure Time / Boot Clock

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 34.01 — sdwdate package/service state

**Stage / source classification:** `S4 / LOW`

**Historical evidence:** sdwdate installed and active with persistent activation in both USER and SYSMAINT.

**Identified weakness / gap:** No independent absolute authenticated-time assessment.

**Implementation task:** Check service on future boots.

**Core checkpoints:** `KHAHP-34.01A`, `KHAHP-34.01B`, `KHAHP-34.01C`

**Source / evidence status:** 34-sdwdate-secure-time-boot-clock-sysmaint-20261013-153748.txt:L28-L40; 34-sdwdate-secure-time-boot-clock-user-20261013- 153514.txt:L28-L40 | OBSERVED_PROTECTION

### 34.02 — timesanitycheck state

**Stage / source classification:** `S4 / LOW`

**Historical evidence:** timesanitycheck.service loaded and completed successfully in both contexts.

**Identified weakness / gap:** Does not show induced failure response.

**Implementation task:** Consider controlled test on disposable VM.

**Core checkpoints:** `KHAHP-34.02A`, `KHAHP-34.02B`, `KHAHP-34.02C`

**Source / evidence status:** 34-sdwdate-secure-time-boot-clock-sysmaint-20261013-153748.txt:L38-L50; 34-sdwdate-secure-time-boot-clock-user-20261013- 153514.txt:L38-L50 | OBSERVED_PROTECTION

### 34.03 — bootclockrandomization state

**Stage / source classification:** `S4 / LOW`

**Historical evidence:** bootclockrandomization.service loaded and completed successfully in both contexts.

**Identified weakness / gap:** Randomization distribution/quality was not evaluated.

**Implementation task:** Preserve Kicksecure integration.

**Core checkpoints:** `KHAHP-34.03A`, `KHAHP-34.03B`, `KHAHP-34.03C`

**Source / evidence status:** 34-sdwdate-secure-time-boot-clock-sysmaint-20261013-153748.txt:L44-L56; 34-sdwdate-secure-time-boot-clock-user-20261013- 153514.txt:L44-L56 | OBSERVED_PROTECTION

### 34.04 — System clock sanity at boot

**Stage / source classification:** `S4 / MEDIUM`

**Historical evidence:** Current clock plausible; uptime and boot-age difference zero in both reports.

**Identified weakness / gap:** Timedatectl NTPSynchronized=no despite active sdwdate; not necessarily a defect and cannot establish trusted wall-clock truth.

**Implementation task:** Validate sdwdate sync/health indicators and time-error tolerance after offline use.

**Core checkpoints:** `KHAHP-34.04A`, `KHAHP-34.04B`, `KHAHP-34.04C`

**Source / evidence status:** 34-sdwdate-secure-time-boot-clock-sysmaint-20261013-153748.txt:L50-L62; 34-sdwdate-secure-time-boot-clock-user-20261013- 153514.txt:L50-L62 | PARTIAL_VERIFICATION

### 34.05 — NTP/systemd-timesyncd conflicts

**Stage / source classification:** `S4 / LOW`

**Historical evidence:** No active/enabled competing timesyncd, chrony, ntp, ntpsec or openntpd in either context.

**Identified weakness / gap:** Future packages may introduce conflicting time sync.

**Implementation task:** Service regression after update.

**Core checkpoints:** `KHAHP-34.05A`, `KHAHP-34.05B`, `KHAHP-34.05C`

**Source / evidence status:** 34-sdwdate-secure-time-boot-clock-sysmaint-20261013-153748.txt:L66-L78; 34-sdwdate-secure-time-boot-clock-user-20261013- 153514.txt:L66-L78 | OBSERVED_PROTECTION

### 34.06 — USER versus SYSMAINT time-source behavior

**Stage / source classification:** `S4 / LOW`

**Historical evidence:** Both USER and SYSMAINT report active sdwdate; SYSMAINT target requests expected services.

**Identified weakness / gap:** Different boots/contexts observed; no controlled time-source failure test.

**Implementation task:** Keep both-role versioned evidence.

**Core checkpoints:** `KHAHP-34.06A`, `KHAHP-34.06B`, `KHAHP-34.06C`

**Source / evidence status:** 34-sdwdate-secure-time-boot-clock-sysmaint-20261013-153748.txt:L80-L92; 34-sdwdate-secure-time-boot-clock-user-20261013- 153514.txt:L80-L92 | OBSERVED_PROTECTION

### 34.07 — Time rollback/jump detection and log coherence

**Stage / source classification:** `S4 / MEDIUM`

**Historical evidence:** No rollback/error keywords in small reviewed secure-time journal; logs/reboot history available.

**Identified weakness / gap:** No actual backwards clock manipulation or jump injection; journal only 1 line in USER snapshot.

**Implementation task:** Run time-jump resilience test only in isolated VM; do not change host RTC.

**Core checkpoints:** `KHAHP-34.07A`, `KHAHP-34.07B`, `KHAHP-34.07C`

**Source / evidence status:** 34-sdwdate-secure-time-boot-clock-sysmaint-20261013-153748.txt:L90-L102; 34-sdwdate-secure-time-boot-clock-user-20261013- 153514.txt:L90-L102 | MANUAL_ACCEPTANCE

---

## 35 — Entropy / RNG / haveged / jitterentropy

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 35.01 — Kernel RNG readiness at boot

**Stage / source classification:** `S4 / LOW`

**Historical evidence:** entropy_avail=256; current-boot RNG readiness messages; no explicit RNG init failure.

**Identified weakness / gap:** Entropy availability is not proof of cryptographic quality.

**Implementation task:** Preserve readiness checks in first boot.

**Core checkpoints:** `KHAHP-35.01A`, `KHAHP-35.01B`, `KHAHP-35.01C`

**Source / evidence status:** 35-entropy-rng-haveged-jitterentropy-sysmaint-20261013-154326.txt:L29-L41 | OBSERVED_PROTECTION

### 35.02 — haveged package/service state

**Stage / source classification:** `S4 / LOW`

**Historical evidence:** haveged installed and active, enabled, with package-owned unit evidence.

**Identified weakness / gap:** Extra daemon presence does not independently prove security improvement.

**Implementation task:** Retain only if supported and appropriate for kernel architecture.

**Core checkpoints:** `KHAHP-35.02A`, `KHAHP-35.02B`, `KHAHP-35.02C`

**Source / evidence status:** 35-entropy-rng-haveged-jitterentropy-sysmaint-20261013-154326.txt:L42-L54 | OBSERVED_PROTECTION

### 35.03 — jitterentropy-rngd package/service state

**Stage / source classification:** `S4 / LOW`

**Historical evidence:** jitterentropy-rngd installed; jitterentropy.service active/enabled and package-owned.

**Identified weakness / gap:** No daemon-failure injection or quality characterization.

**Implementation task:** Check compatibility and service health in ISO/VM builds.

**Core checkpoints:** `KHAHP-35.03A`, `KHAHP-35.03B`, `KHAHP-35.03C`

**Source / evidence status:** 35-entropy-rng-haveged-jitterentropy-sysmaint-20261013-154326.txt:L52-L64 | OBSERVED_PROTECTION

### 35.04 — random.trust_cpu boot policy

**Stage / source classification:** `S4 / LOW`

**Historical evidence:** random.trust_cpu explicitly set off in boot policy.

**Identified weakness / gap:** Policy is attested as configured, not a measurement of CPU entropy-source integrity.

**Implementation task:** Document hardware/VM threat-model choice.

**Core checkpoints:** `KHAHP-35.04A`, `KHAHP-35.04B`, `KHAHP-35.04C`

**Source / evidence status:** 35-entropy-rng-haveged-jitterentropy-sysmaint-20261013-154326.txt:L63-L75 | OBSERVED_PROTECTION

### 35.05 — random.trust_bootloader boot policy

**Stage / source classification:** `S4 / LOW`

**Historical evidence:** random.trust_bootloader explicitly set off in boot policy.

**Identified weakness / gap:** Cannot infer complete VM entropy readiness or source diversity.

**Implementation task:** Decide host vs guest entropy source policy separately.

**Core checkpoints:** `KHAHP-35.05A`, `KHAHP-35.05B`, `KHAHP-35.05C`

**Source / evidence status:** 35-entropy-rng-haveged-jitterentropy-sysmaint-20261013-154326.txt:L69-L81 | OBSERVED_PROTECTION

### 35.06 — Entropy source and /dev/random behavior

**Stage / source classification:** `S4 / LOW`

**Historical evidence:** /dev/random and /dev/urandom are character devices; bounded 32-byte reads succeeded without disclosure.

**Identified weakness / gap:** Functionality test is not statistical validation.

**Implementation task:** Retain bounded health test, no random byte dumps.

**Core checkpoints:** `KHAHP-35.06A`, `KHAHP-35.06B`, `KHAHP-35.06C`

**Source / evidence status:** 35-entropy-rng-haveged-jitterentropy-sysmaint-20261013-154326.txt:L76-L88 | OBSERVED_PROTECTION

### 35.07 — Early-boot entropy persistence and regression evidence

**Stage / source classification:** `S4 / HIGH`

**Historical evidence:** systemd-random-seed completed; seed present 32 bytes, root:root mode 600; no boot error.

**Identified weakness / gap:** No induced entropy-starvation test; image publication must not duplicate developer random seed.

**Implementation task:** Exclude development seed from artifacts; generate distinct customer seed after first boot/import.

**Core checkpoints:** `KHAHP-35.07A`, `KHAHP-35.07B`, `KHAHP-35.07C`

**Source / evidence status:** 35-entropy-rng-haveged-jitterentropy-sysmaint-20261013-154326.txt:L88-L100 | IMAGE_RELEASE_GATE

---

## 36 — Browser DoH / WebRTC / Telemetry

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 36.01 — Browser DNS-over-HTTPS/TRR setting

**Stage / source classification:** `S4 / MEDIUM`

**Historical evidence:** Firefox mapped user.js and prefs.js both show network.trr.mode=5.

**Identified weakness / gap:** No direct runtime packet proof of browser DoH being disabled on all browser profiles.

**Implementation task:** Inspect effective Firefox policy and perform DNS leak test for mapped profile.

**Core checkpoints:** `KHAHP-36.01A`, `KHAHP-36.01B`, `KHAHP-36.01C`

**Source / evidence status:** 36-browser-state-verification-user-20261013-162652.txt:L59-L79 | PARTIAL_VERIFICATION

### 36.02 — Browser proxy DNS routing behavior

**Stage / source classification:** `S4 / MEDIUM`

**Historical evidence:** Firefox profile and privacy preferences inventoried, but no explicit configured browser-proxy execution test appears.

**Identified weakness / gap:** Proxy DNS behavior of actual browser was not exercised; not equivalent to Section 33's curl- through-Tor proof.

**Implementation task:** Test browser-specific routing and DNS for approved Tor/clearnet modes.

**Core checkpoints:** `KHAHP-36.02A`, `KHAHP-36.02B`, `KHAHP-36.02C`

**Source / evidence status:** 36-browser-state-verification-user-20261013-162652.txt:L39-L46 | UNTESTED_BEHAVIOR

### 36.03 — WebRTC/STUN local/public IP exposure

**Stage / source classification:** `S4 / MEDIUM`

**Historical evidence:** media.peerconnection.enabled=false recorded in user.js and prefs.js for running mapped Firefox profile.

**Identified weakness / gap:** No actual browser WebRTC/STUN leak test executed.

**Implementation task:** Perform controlled STUN/WebRTC leak test in mapped Firefox and separate Mullvad profile.

**Core checkpoints:** `KHAHP-36.03A`, `KHAHP-36.03B`, `KHAHP-36.03C`

**Source / evidence status:** 36-browser-state-verification-user-20261013-162652.txt:L61-L79 | PARTIAL_VERIFICATION

### 36.04 — Telemetry and crash-report settings

**Stage / source classification:** `S4 / MEDIUM`

**Historical evidence:** Most telemetry/crash reporting preferences agree between user.js and prefs.js; toolkit.telemetry.enabled=false in user.js but absent in prefs.js.

**Identified weakness / gap:** Absent prefs.js entry alone does not prove telemetry enabled; actual effective setting not independently checked.

**Implementation task:** Check about:config/policies effective value, startup processing and locked-policy overrides; change only if wrong.

**Core checkpoints:** `KHAHP-36.04A`, `KHAHP-36.04B`, `KHAHP-36.04C`

**Source / evidence status:** 36-browser-state-verification-user-20261013-162652.txt:L63-L92 | PARTIAL_VERIFICATION

### 36.05 — Safe browsing/prediction/background network features

**Stage / source classification:** `S4 / MEDIUM`

**Historical evidence:** KHAHP user.js disables speculative connections, DNS prefetch, prediction and prefetch; corresponding prefs.js values found.

**Identified weakness / gap:** Safe Browsing policy and real network-background activity not comprehensively inventoried.

**Implementation task:** Confirm required Safe Browsing tradeoff, background traffic and policy enforcement.

**Core checkpoints:** `KHAHP-36.05A`, `KHAHP-36.05B`, `KHAHP-36.05C`

**Source / evidence status:** 36-browser-state-verification-user-20261013-162652.txt:L70-L92 | PARTIAL_VERIFICATION

### 36.06 — Extension/add-on inventory and trust

**Stage / source classification:** `S4 / MEDIUM`

**Historical evidence:** One additional Firefox profile with KHAHP user.js; Mullvad Browser profile inventoried and intentionally not modified.

**Identified weakness / gap:** Extension/add-on inventory and trust/signed-extension evidence are absent from this verifier.

**Implementation task:** Inventory enabled add-ons and extension permissions per profile without modifying Mullvad policies.

**Core checkpoints:** `KHAHP-36.06A`, `KHAHP-36.06B`, `KHAHP-36.06C`

**Source / evidence status:** 36-browser-state-verification-user-20261013-162652.txt:L125-L139 | UNTESTED_BEHAVIOR

### 36.07 — Browser update, profile persistence and leak tests

**Stage / source classification:** `S4 / MEDIUM`

**Historical evidence:** Running Firefox used installation-mapped profile; user.js restrictive mode 600; managed values matched; Mullvad separate.

**Identified weakness / gap:** Live effective preference proof incomplete and update/relaunch/leak regression not shown.

**Implementation task:** Reconfirm effective prefs and leak behavior after browser restart/update.

**Core checkpoints:** `KHAHP-36.07A`, `KHAHP-36.07B`, `KHAHP-36.07C`

**Source / evidence status:** 36-browser-state-verification-user-20261013-162652.txt:L142-L152 | PARTIAL_VERIFICATION

---

## 37 — Application / File / Metadata Privacy

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 37.01 — Desktop search/indexing services

**Stage / source classification:** `S1 / LOW`

**Historical evidence:** Known indexer packages and services absent/inactive; zero matching USER indexer/autostart processes.

**Identified weakness / gap:** Does not audit every application-specific search indexer.

**Implementation task:** Monitor process and autostart changes.

**Core checkpoints:** `KHAHP-37.01A`, `KHAHP-37.01B`, `KHAHP-37.01C`

**Source / evidence status:** 37-application-file-metadata-privacy-user-20261013-165726.txt:L30-L42 | OBSERVED_PROTECTION

### 37.02 — Thumbnail and preview cache behavior

**Stage / source classification:** `S1 / LOW`

**Historical evidence:** Thumbnail cache mode 700, zero cached files/bytes; tumblerd not running/not installed.

**Identified weakness / gap:** Verifier deliberately did not provoke automatic thumbnail generation/cleanup.

**Implementation task:** Controlled synthetic document open/close and retention test if privacy goal requires it.

**Core checkpoints:** `KHAHP-37.02A`, `KHAHP-37.02B`, `KHAHP-37.02C`

**Source / evidence status:** 37-application-file-metadata-privacy-user-20261013-165726.txt:L55-L67 | PARTIAL_VERIFICATION

### 37.03 — Recent-files/history and clipboard retention

**Stage / source classification:** `S1 / LOW`

**Historical evidence:** No GTK recent-file database or known clipboard-manager process/autostart; clipboard contents never read.

**Identified weakness / gap:** Does not establish every app's private history/clipboard memory retention.

**Implementation task:** Assess targeted applications with synthetic data only.

**Core checkpoints:** `KHAHP-37.03A`, `KHAHP-37.03B`, `KHAHP-37.03C`

**Source / evidence status:** 37-application-file-metadata-privacy-user-20261013-165726.txt:L70-L82 | PARTIAL_VERIFICATION

### 37.04 — Document/image metadata handling

**Stage / source classification:** `S1 / MEDIUM`

**Historical evidence:** mat2 and ExifTool installed; no user documents inspected.

**Identified weakness / gap:** Tool availability does not prove actual metadata removal from real customer file types.

**Implementation task:** Use synthetic samples across supported formats; optional owner-reviewed real files.

**Core checkpoints:** `KHAHP-37.04A`, `KHAHP-37.04B`, `KHAHP-37.04C`

**Source / evidence status:** 37-application-file-metadata-privacy-user-20261013-165726.txt:L81-L93 | PARTIAL_VERIFICATION

### 37.05 — Temporary-file and application-cache exposure

**Stage / source classification:** `S1 / LOW`

**Historical evidence:** XDG runtime and cache roots mode 700; /tmp USER files had zero world-exposure hits; private group explains group-read bits.

**Identified weakness / gap:** Group-readable cache files exist behind private parent; /tmp/world permissions require application-specific examination.

**Implementation task:** No blanket chmod from group bits; targeted leakage test.

**Core checkpoints:** `KHAHP-37.05A`, `KHAHP-37.05B`, `KHAHP-37.05C`

**Source / evidence status:** 37-application-file-metadata-privacy-user-20261013-165726.txt:L96-L108 | OBSERVED_PROTECTION

### 37.06 — Sandboxed versus unsandboxed application inventory

**Stage / source classification:** `S1 / HIGH`

**Historical evidence:** Of 48 assessed USER processes, 0 labeled non-unconfined AppArmor; 48 unconfined/unknown; 4 had seccomp-filter mode 2.

**Identified weakness / gap:** Generic verifier's label method and process scope require confirmation; explicitly cannot claim USER applications generally confined.

**Implementation task:** Crosscheck /proc/<pid>/attr/current per intended app against aa-status and Section 15; add compatible enforced profiles where viable.

**Core checkpoints:** `KHAHP-37.06A`, `KHAHP-37.06B`, `KHAHP-37.06C`

**Source / evidence status:** 37-application-file-metadata-privacy-user-20261013-165726.txt:L118-L140 | HARDENING_REVIEW

### 37.07 — Metadata-removal workflow and regression testing

**Stage / source classification:** `S1 / MEDIUM`

**Historical evidence:** Synthetic PNG marker removed by mat2 with successful exit; no real user files touched.

**Identified weakness / gap:** Real-document workflow and repeated roundtrip test remain manual.

**Implementation task:** Add format-specific synthetic regression corpus and safe customer documentation.

**Core checkpoints:** `KHAHP-37.07A`, `KHAHP-37.07B`, `KHAHP-37.07C`

**Source / evidence status:** 37-application-file-metadata-privacy-user-20261013-165726.txt:L143-L155 | PARTIAL_VERIFICATION

---

## 38 — Camera / Microphone / Power / Screen Lock

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 38.01 — Camera hardware/device exposure

**Stage / source classification:** `S3 / MEDIUM`

**Historical evidence:** Two video devices with mode 0 denied USER; no USER camera FDs open.

**Identified weakness / gap:** No physical capture attempt/seat ACL regression performed.

**Implementation task:** Controlled camera negative test before claiming deny-by-default.

**Core checkpoints:** `KHAHP-38.01A`, `KHAHP-38.01B`, `KHAHP-38.01C`

**Source / evidence status:** 38-camera-microphone-power-screenlock-user-20261013-174938.txt:L34-L46; 38-lxqt-lock-power-diagnostic-user-20261013- 172045.txt | PARTIAL_VERIFICATION

### 38.02 — Microphone hardware/device exposure

**Stage / source classification:** `S3 / MEDIUM`

**Historical evidence:** Capture ALSA node denied; no non-monitor pactl capture source; all 4 playback nodes USER accessible.

**Identified weakness / gap:** No real microphone app recording negative test.

**Implementation task:** Validate capture denial and playback retention using safe synthetic/app test.

**Core checkpoints:** `KHAHP-38.02A`, `KHAHP-38.02B`, `KHAHP-38.02C`

**Source / evidence status:** 38-camera-microphone-power-screenlock-user-20261013-174938.txt:L44-L56; 38-lxqt-lock-power-diagnostic-user-20261013- 172045.txt | PARTIAL_VERIFICATION

### 38.03 — Bluetooth/rfkill interaction with peripherals

**Stage / source classification:** `S3 / LOW`

**Historical evidence:** Bluetooth inactive; 2 rfkill controllers soft-blocked in USER observation.

**Identified weakness / gap:** Physical toggle/reboot persistence not exercised.

**Implementation task:** Try authorized physical enable and verify policy persists after reboot.

**Core checkpoints:** `KHAHP-38.03A`, `KHAHP-38.03B`, `KHAHP-38.03C`

**Source / evidence status:** 38-camera-microphone-power-screenlock-user-20261013-174938.txt:L57-L69; 38-lxqt-lock-power-diagnostic-user-20261013- 172045.txt | PARTIAL_VERIFICATION

### 38.04 — Screen-lock timeout and authentication

**Stage / source classification:** `S3 / MEDIUM`

**Historical evidence:** Later 17:49 report shows root-managed swayidle autostart, 2 running swayidle processes and a 300- second swaylock command.

**Identified weakness / gap:** Earlier 17:20 generic diagnostic missed explicit idle policy; actual unattended lock and authentication weren't exercised.

**Implementation task:** Perform timed idle lock and unlock authentication check with owner present.

**Core checkpoints:** `KHAHP-38.04A`, `KHAHP-38.04B`, `KHAHP-38.04C`

**Source / evidence status:** 38-camera-microphone-power-screenlock-user-20261013-174938.txt:L65-L80; 38-lxqt-lock-power-diagnostic-user-20261013- 172045.txt:L106-L114 | PARTIAL_VERIFICATION

### 38.05 — Suspend/lock-on-lid and idle behavior

**Stage / source classification:** `S3 / HIGH`

**Historical evidence:** 17:20 diagnostic shows logind inhibitor 'handle-lid-switch' by lxqt-powermanagement and pre-sleep inhibitor; later 17:49 verifier shows pre-sleep=1 but lid_handler_inhibitor=0.

**Identified weakness / gap:** Reports disagree, possibly matcher/timing; neither performed physical lid-close/resume lock test.

**Implementation task:** Inspect current loginctl inhibit/LXQt handling without changing settings, then test lid close/resume lock and repair only if bypass reproduced.

**Core checkpoints:** `KHAHP-38.05A`, `KHAHP-38.05B`, `KHAHP-38.05C`

**Source / evidence status:** 38-lxqt-lock-power-diagnostic-user-20261013-172045.txt:L94-L114; 38-camera-microphone-power-screenlock-user-20261013- 174938.txt:L82-L90 | HARDENING_REVIEW

### 38.06 — Hibernation configuration and encrypted-swap implications

**Stage / source classification:** `S3 / MEDIUM`

**Historical evidence:** Kernel advertises hibernation; no resume cmdline or resume config detected; active swap=1 with Section 06 encryption cross-reference.

**Identified weakness / gap:** No hibernate/resume performed; no proven supported encrypted resume arrangement.

**Implementation task:** Document whether hibernation unsupported/disabled or securely provisioned, then test on disposable setup.

**Core checkpoints:** `KHAHP-38.06A`, `KHAHP-38.06B`, `KHAHP-38.06C`

**Source / evidence status:** 38-camera-microphone-power-screenlock-user-20261013-174938.txt:L92-L98 | MANUAL_ACCEPTANCE

### 38.07 — Shutdown-versus-suspend operational policy

**Stage / source classification:** `S3 / MEDIUM`

**Historical evidence:** ram-wipe installed; shutdown for transport/unattended is documented high-assurance policy.

**Identified weakness / gap:** No shutdown/suspend recovery or zeroization test performed; suspend retains RAM secrets.

**Implementation task:** Validate real shutdown/lock behaviors and customer operating guide when safe.

**Core checkpoints:** `KHAHP-38.07A`, `KHAHP-38.07B`, `KHAHP-38.07C`

**Source / evidence status:** 38-camera-microphone-power-screenlock-user-20261013-174938.txt:L99-L107 | MANUAL_ACCEPTANCE

---

## 39 — Firmware / BIOS / Secure Boot / TPM

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 39.01 — BIOS/UEFI vendor, model and firmware version

**Stage / source classification:** `S2 / P2`

**Historical evidence:** UEFI platform and BIOS revision inventoried; no serial or machine UUID copied into report.

**Identified weakness / gap:** Firmware latest/supported status not established.

**Implementation task:** Compare installed BIOS with authenticated ASUS release and advisories; avoid blind firmware update.

**Core checkpoints:** `KHAHP-39.01A`, `KHAHP-39.01B`, `KHAHP-39.01C`

**Source / evidence status:** 39-postenable-final-sysmaint-20261014-212049.txt:24-35 | INVENTORY_CONFIRMED

### 39.02 — fwupd device/security-attribute inventory

**Stage / source classification:** `S2 / P1`

**Historical evidence:** fwupd reported HSI:1!; UEFI memory protection and pre-boot DMA protection disabled; kernel tainted; BootGuard, SPI lock and IOMMU positive.

**Identified weakness / gap:** May be firmware/hardware-limited. No BIOS or platform remediation proven.

**Implementation task:** Prioritize verified firmware security-capability review; record vendor/hardware limitations and mitigations; do not promise HSI improvement.

**Core checkpoints:** `KHAHP-39.02A`, `KHAHP-39.02B`, `KHAHP-39.02C`

**Source / evidence status:** 39-postenable-final-sysmaint-20261014-212049.txt:38-62 | POTENTIAL_HARDENING_GAP

### 39.03 — Secure Boot state and Setup Mode

**Stage / source classification:** `S2 / P2`

**Historical evidence:** SecureBoot=1, SetupMode=0; PK, KEK and db present; later independent mokutil confirms Secure Boot.

**Identified weakness / gap:** No post-update/recovery persistence proof.

**Implementation task:** Retain existing working enrollment; verify after future approved firmware/kernel changes.

**Core checkpoints:** `KHAHP-39.03A`, `KHAHP-39.03B`, `KHAHP-39.03C`

**Source / evidence status:** 39-postenable-final-sysmaint-20261014-212049.txt:64-77;39-mok-resolution-v1.3-sysmaint-20261014-212851.txt:7-10 | ENFORCEMENT_OBSERVED

### 39.04 — TPM presence, version and ownership state

**Stage / source classification:** `S2 / P2`

**Historical evidence:** TPM 2.0 enumerated and permanent attributes readable; lockoutAuthSet=1; disableClear=0.

**Identified weakness / gap:** TPM owner/hierarchy, tamper recovery and disk-binding policy not validated.

**Implementation task:** Review permitted TPM operations, ownership and safe recovery; do not clear TPM.

**Core checkpoints:** `KHAHP-39.04A`, `KHAHP-39.04B`, `KHAHP-39.04C`

**Source / evidence status:** 39-postenable-final-sysmaint-20261014-212049.txt:79-99 | PARTIAL_RUNTIME

### 39.05 — BIOS/UEFI administrator password manual check

**Stage / source classification:** `S2 / P1`

**Historical evidence:** Firmware administrator password test explicitly deferred to owner.

**Identified weakness / gap:** No evidence unauthorized BIOS changes require valid administrator authentication.

**Implementation task:** Owner-only firmware-screen negative check without recording password.

**Core checkpoints:** `KHAHP-39.05A`, `KHAHP-39.05B`, `KHAHP-39.05C`

**Source / evidence status:** 39-postenable-final-sysmaint-20261014-212049.txt:101-108;39-43-targeted-sysmaint-v1.3-20261015-013719.txt:11-11 | MANUAL_REQUIRED

### 39.06 — PXE/CSM/external-boot/manual boot- order policy

**Stage / source classification:** `S2 / P1`

**Historical evidence:** UEFI BootOrder inventoried; no obvious network/removable boot entry labels.

**Identified weakness / gap:** CSM, PXE, one-time boot and physical bypass restrictions not tested.

**Implementation task:** Manually check external boot and boot-menu bypass under controlled conditions; document limitations.

**Core checkpoints:** `KHAHP-39.06A`, `KHAHP-39.06B`, `KHAHP-39.06C`

**Source / evidence status:** 39-postenable-final-sysmaint-20261014-212049.txt:110-120 | MANUAL_REQUIRED

### 39.07 — Firmware update, DKMS/MOK and Secure-Boot readiness

**Stage / source classification:** `S2 / P2`

**Historical evidence:** Kernel image signed; lockdown active; 197/197 file-backed loaded modules had signature metadata; tirdad loaded. Initial mokutil exit-code false failure later corrected: output says certificate already enrolled.

**Identified weakness / gap:** Firmware recovery and future signed DKMS upgrades untested; third-party kernel module taint recorded.

**Implementation task:** Keep signing configuration; regression test module load after kernel update; document firmware recovery.

**Core checkpoints:** `KHAHP-39.07A`, `KHAHP-39.07B`, `KHAHP-39.07C`

**Source / evidence status:** 39-postenable-final-sysmaint-20261014-212049.txt:122-146;39-mok-resolution-v1.3-sysmaint-20261014-212851.txt:7-26 | HISTORICAL_FINDING_RESOLVED

---

## 40 — Auditd / AIDE / Integrity Monitoring

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 40.01 — auditd package/service state

**Stage / source classification:** `S5 / P2`

**Historical evidence:** auditd installed/enabled; SYSMAINT service inactive as expected for its boot context; later USER- mode privileged probe shows active auditd, lost=0.

**Identified weakness / gap:** USER boot persistence and audit loss under controlled log pressure not fully verified.

**Implementation task:** Retain current services; test USER logging continuity and after-boot state.

**Core checkpoints:** `KHAHP-40.01A`, `KHAHP-40.01B`, `KHAHP-40.01C`

**Source / evidence status:** 39-43-closeout-sysmaint-v1.1-20261015-011541.txt:18-23;39-43-targeted-user-probe-v1.3-20261015-015154.txt:1-10 | ENFORCEMENT_OBSERVED

### 40.02 — Audit rule inventory and immutable/finalize policy

**Stage / source classification:** `S5 / P1`

**Historical evidence:** Five staged rule keys built with augenrules; later USER-mode audit probe confirms all five loaded in kernel.

**Identified weakness / gap:** Independent event-generation with matching audit records unperformed.

**Implementation task:** Create harmless monitored event and verify corresponding USER audit event; do not reinstall one- shot probe.

**Core checkpoints:** `KHAHP-40.02A`, `KHAHP-40.02B`, `KHAHP-40.02C`

**Source / evidence status:** 39-43-targeted-sysmaint-v1.3-20261015-013719.txt:15-20;39-43-targeted-user-probe-v1.3-20261015-015154.txt:1-10 | ENFORCEMENT_OBSERVED

### 40.03 — Privileged-command and identity- change audit coverage

**Stage / source classification:** `S5 / P1`

**Historical evidence:** Identity, privilege, SSH policy, auditing and persistence watch keys present in USER kernel.

**Identified weakness / gap:** Presence alone does not prove each watched change generates searchable audit event.

**Implementation task:** Execute controlled harmless event test for representative rule keys; verify key, timestamp and result.

**Core checkpoints:** `KHAHP-40.03A`, `KHAHP-40.03B`, `KHAHP-40.03C`

**Source / evidence status:** 40-audit-rules-remediation-v1.1-sysmaint-20261015-000238.txt:18-40;39-43-targeted-user-probe-v1.3-20261015-015154.txt:1-10 | PARTIAL_RUNTIME

### 40.04 — AIDE package/database/configuration state

**Stage / source classification:** `S5 / P2`

**Historical evidence:** AIDE 0.19.1 baseline pair byte-identical; config rules cover /etc/shadow, /etc/audit/auditd.conf and /etc/ssh/sshd_config. Earlier exit 17 arose from missing --config invocation; separate operator screenshot later indicated correct command exit 0.

**Identified weakness / gap:** Corrected exit-0 screenshot is not in this tar archive; full scan and trusted baseline custody require independent acceptance.

**Implementation task:** Do NOT reinitialize AIDE. Preserve baseline; attach correct --config check evidence and validate alert on harmless isolated fixture.

**Core checkpoints:** `KHAHP-40.04A`, `KHAHP-40.04B`, `KHAHP-40.04C`

**Source / evidence status:** 39-40-41-combined-final-verifier-v1.0-sysmaint-20261014-234903.txt:315-355;39-43-targeted-sysmaint-v1.3-20261015-013719.txt:21- 27 | HISTORICAL_VERIFIER_ERROR

### 40.05 — File-integrity baseline and scheduled checks

**Stage / source classification:** `S5 / P2`

**Historical evidence:** Daily AIDE timer enabled and active in SYSMAINT and USER snapshots.

**Identified weakness / gap:** Timer active is not proof of successful full AIDE verification over time.

**Implementation task:** Inspect permitted recent service results; verify controlled alert lifecycle and post-boot recurrence.

**Core checkpoints:** `KHAHP-40.05A`, `KHAHP-40.05B`, `KHAHP-40.05C`

**Source / evidence status:** 39-40-41-combined-final-verifier-v1.0-sysmaint-20261014-234903.txt:342-356;39-43-targeted-user-probe-v1.3-20261015- 015154.txt:10-11 | PARTIAL_RUNTIME

### 40.06 — Audit-log ownership, rotation and tamper resistance

**Stage / source classification:** `S5 / P2`

**Historical evidence:** Audit log directory permissions assessed; auditd log infrastructure and metadata inventoried.

**Identified weakness / gap:** Retention, rotation, disk-pressure and event availability not fully demonstrated in USER role.

**Implementation task:** Test log access restrictions, rotation thresholds and loss behavior on non-destructive test workload.

**Core checkpoints:** `KHAHP-40.06A`, `KHAHP-40.06B`, `KHAHP-40.06C`

**Source / evidence status:** 39-43-closeout-sysmaint-v1.1-20261015-011541.txt:27-31;40-baseline-sysmaint-20261014-213426.txt:21-40 | CONFIG_INVENTORIED

### 40.07 — CIS/DISA accountability-gap analysis

**Stage / source classification:** `S5 / P2`

**Historical evidence:** Auditd, AIDE, staged rule sources, timers and missing-test inventory captured.

**Identified weakness / gap:** No comprehensive negative/independent evidence coverage or alert response chain accepted.

**Implementation task:** Cross-map each Section40 family A/B/C with event evidence, AIDE alert and recovery; keep documented exceptions.

**Core checkpoints:** `KHAHP-40.07A`, `KHAHP-40.07B`, `KHAHP-40.07C`

**Source / evidence status:** 39-43-targeted-user-probe-v1.3-20261015-015154.txt:1-14;39-43-closeout-sysmaint-v1.1-20261015-011541.txt:18-31 | PARTIAL_RUNTIME

---

## 41 — Cron / Timers / Persistence / Supply Chain

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 41.01 — cron/anacron job inventory

**Stage / source classification:** `S5 / P2`

**Historical evidence:** Cron-related directories inventoried; cron/anacron units absent and multiple package-owned scripts identified.

**Identified weakness / gap:** Job-level allowlist and ownership trust assessment not completed; the absence of daemon does not mean malicious persistence impossible.

**Implementation task:** Classify each scheduled script and executable by owner, origin, content hash and actual execution mechanism.

**Core checkpoints:** `KHAHP-41.01A`, `KHAHP-41.01B`, `KHAHP-41.01C`

**Source / evidence status:** 41-targeted-verification-v1.2-sysmaint-20261014-233434-qkayOV.txt:8-47 | INVENTORY_ONLY

### 41.02 — systemd timer inventory

**Stage / source classification:** `S5 / P2`

**Historical evidence:** Several systemd timers including AIDE and APT update timers documented with next and last timestamps.

**Identified weakness / gap:** Lists contain active/inactive timers; timer inventory is not allowlist; last execution result not uniform.

**Implementation task:** Record full timer source→trigger→service→binary, ownership and last success.

**Core checkpoints:** `KHAHP-41.02A`, `KHAHP-41.02B`, `KHAHP-41.02C`

**Source / evidence status:** 41-targeted-verification-v1.2-sysmaint-20261014-233434-qkayOV.txt:89-151 | INVENTORY_ONLY

### 41.03 — User autostart and desktop persistence inventory

**Stage / source classification:** `S5 / P1`

**Historical evidence:** USER startup .desktop entries enumerated from SYSMAINT; khahp-idle-lock.desktop recorded.

**Identified weakness / gap:** No authenticated USER runtime autostart and two-boot comparison in archive; USER agent ports not classified.

**Implementation task:** Review effective USER autostart and authorized entries during normal login, then compare on next normal boot.

**Core checkpoints:** `KHAHP-41.03A`, `KHAHP-41.03B`, `KHAHP-41.03C`

**Source / evidence status:** 41-targeted-verification-v1.2-sysmaint-20261014-233434-qkayOV.txt:151-223;39-43-targeted-sysmaint-v1.3-20261015-013719.txt:35- 35 | PARTIAL_INVENTORY

### 41.04 — Package repository and signing-key provenance

**Stage / source classification:** `S5 / P1`

**Historical evidence:** APT source/keyring path inventories gathered, installed dpkg database healthy.

**Identified weakness / gap:** Repository key lineage, unsigned local overrides and third-party key policy not fully validated.

**Implementation task:** Validate source origins, signed-by, key ownership, permitted distributions and repository trust decisions.

**Core checkpoints:** `KHAHP-41.04A`, `KHAHP-41.04B`, `KHAHP-41.04C`

**Source / evidence status:** 41-targeted-verification-v1.2-sysmaint-20261014-233434-qkayOV.txt:225-332;39-43-targeted-sysmaint-v1.3-20261015-013719.txt:37- 37 | PROVENANCE_REVIEW

### 41.05 — APT pinning/holds and update-policy review

**Stage / source classification:** `S5 / P2`

**Historical evidence:** No held packages and dpkg --audit empty; APT update timers exist.

**Identified weakness / gap:** No full package-update/rollback and unattended update regression measured.

**Implementation task:** Record pinned package baseline and safe upgrade/rollback regression.

**Core checkpoints:** `KHAHP-41.05A`, `KHAHP-41.05B`, `KHAHP-41.05C`

**Source / evidence status:** 41-targeted-verification-v1.2-sysmaint-20261014-233434-qkayOV.txt:333-390 | PARTIAL_RUNTIME

### 41.06 — Unexpected startup scripts/services/modules

**Stage / source classification:** `S5 / P2`

**Historical evidence:** Service/module inventories and failed-unit status collected; no failed services reported.

**Identified weakness / gap:** Not all startup entries individually attributed; some links are unowned by dpkg but may be intentional local policy.

**Implementation task:** Build an explicit approved startup allowlist; review package-owned and local override units.

**Core checkpoints:** `KHAHP-41.06A`, `KHAHP-41.06B`, `KHAHP-41.06C`

**Source / evidence status:** 41-targeted-verification-v1.2-sysmaint-20261014-233434-qkayOV.txt:391-555 | PROVENANCE_REVIEW

### 41.07 — Supply-chain drift and reboot- persistence evidence

**Stage / source classification:** `S5 / P1`

**Historical evidence:** Source inventory and hash manifests exist with a boot ID.

**Identified weakness / gap:** No signed diff from TWO distinct normal USER boots, no drift decision or approved-change history.

**Implementation task:** Capture separated USER boot snapshots; compare exact hashes and classify changes without leaking identity.

**Core checkpoints:** `KHAHP-41.07A`, `KHAHP-41.07B`, `KHAHP-41.07C`

**Source / evidence status:** 41-targeted-verification-v1.2-sysmaint-20261014-233434-qkayOV.txt:1-7;39-43-targeted-sysmaint-v1.3-20261015-013719.txt:35-36 | PERSISTENCE_UNTESTED

---

## 42 — Credentials / SSH Keys / Secrets / Backup

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 42.01 — SSH private-key inventory and permissions

**Stage / source classification:** `S6 / P2`

**Historical evidence:** root and USER SSH dirs mode 700; authorized_keys 600; keys-only/no-root effective sshd policy; SSH service/socket masked.

**Identified weakness / gap:** Customer images require regenerated keys, not copying developer key material.

**Implementation task:** Retain SSH restrictions; test release image for zero inherited host keys and personal credentials.

**Core checkpoints:** `KHAHP-42.01A`, `KHAHP-42.01B`, `KHAHP-42.01C`

**Source / evidence status:** 42-credentials-secrets-backup-baseline-v1.0-sysmaint-20261015-001435.txt:7-16;39-43-targeted-sysmaint-v1.3-20261015- 013719.txt:39-42 | ENFORCEMENT_OBSERVED

### 42.02 — API/token/secret storage locations

**Stage / source classification:** `S6 / P1`

**Historical evidence:** Common secret location modes inventoried; NetworkManager connection files mode-restricted; credential-release-gate script created.

**Identified weakness / gap:** No complete filesystem secret content scan; no clean release artifact exists to run gate on.

**Implementation task:** Run approved nonleaking secret scanner on freshly built customer root only; inspect reports before sharing.

**Core checkpoints:** `KHAHP-42.02A`, `KHAHP-42.02B`, `KHAHP-42.02C`

**Source / evidence status:** 42-credentials-secrets-backup-baseline-v1.0-sysmaint-20261015-001435.txt:17-27;42-safe-remediation-and-image-gate-v1.1- sysmaint-20261015-003431.txt:12-20 | INVENTORY_ONLY

### 42.03 — Password-manager selection and vault policy

**Stage / source classification:** `S6 / P2`

**Historical evidence:** KeePassXC installed, policy file prepared.

**Identified weakness / gap:** Actual vault unlock/backup/integration tests and operator policy decisions not performed.

**Implementation task:** Decide supported customer vault policy; test protected vault creation/unlock/recovery separately.

**Core checkpoints:** `KHAHP-42.03A`, `KHAHP-42.03B`, `KHAHP-42.03C`

**Source / evidence status:** 42-credentials-secrets-backup-baseline-v1.0-sysmaint-20261015-001435.txt:28-36;42-safe-remediation-and-image-gate-v1.1- sysmaint-20261015-003431.txt:31-31 | POLICY_PREPARED

### 42.04 — FIDO2/YubiKey readiness and hardware-backed keys

**Stage / source classification:** `S6 / P2`

**Historical evidence:** FIDO2/cryptenroll tooling available.

**Identified weakness / gap:** No physical token enrollment, loss/recovery or customer hardware test.

**Implementation task:** Test with consent on designated spare hardware; record capability not token secrets.

**Core checkpoints:** `KHAHP-42.04A`, `KHAHP-42.04B`, `KHAHP-42.04C`

**Source / evidence status:** 42-credentials-secrets-backup-baseline-v1.0-sysmaint-20261015-001435.txt:37-43;42-safe-remediation-and-image-gate-v1.1- sysmaint-20261015-003431.txt:32-32 | MANUAL_REQUIRED

### 42.05 — Recovery-code generation and offline storage

**Stage / source classification:** `S6 / P1`

**Historical evidence:** Offline recovery policy prepared; existing backup directory metadata inventoried.

**Identified weakness / gap:** No custodian attestation, key rotation or offline-recovery drill recorded.

**Implementation task:** Define and owner-approve recovery custody; test recovery without writing codes into reports.

**Core checkpoints:** `KHAHP-42.05A`, `KHAHP-42.05B`, `KHAHP-42.05C`

**Source / evidence status:** 42-credentials-secrets-backup-baseline-v1.0-sysmaint-20261015-001435.txt:44-48;42-safe-remediation-and-image-gate-v1.1- sysmaint-20261015-003431.txt:33-33 | MANUAL_REQUIRED

### 42.06 — Encrypted backup creation and retention

**Stage / source classification:** `S6 / P1`

**Historical evidence:** GPG available; disposable AES256 encrypted/decrypted fixture passed; dpkg backup timer present.

**Identified weakness / gap:** No genuine encrypted backup repository, designated target, retention/rotation or test data restored.

**Implementation task:** Obtain owner-approved destination; implement encrypted backup with read-after-write verification and recovery isolation.

**Core checkpoints:** `KHAHP-42.06A`, `KHAHP-42.06B`, `KHAHP-42.06C`

**Source / evidence status:** 42-credentials-secrets-backup-baseline-v1.0-sysmaint-20261015-001435.txt:49-68;42-safe-remediation-and-image-gate-v1.1- sysmaint-20261015-003431.txt:22-35 | BACKUP_UNTESTED

### 42.07 — Restore test, key recovery and disaster-recovery evidence

**Stage / source classification:** `S6 / P1`

**Historical evidence:** Disposable fixture proves crypto tool can encrypt/decrypt a test object.

**Identified weakness / gap:** No real laptop backup restoration, disaster-recovery recovery-time estimate or secret custody evidence.

**Implementation task:** Perform isolated restore from actual approved encrypted backup and verify integrity/ownership; no production overwrite.

**Core checkpoints:** `KHAHP-42.07A`, `KHAHP-42.07B`, `KHAHP-42.07C`

**Source / evidence status:** 42-safe-remediation-and-image-gate-v1.1-sysmaint-20261015-003431.txt:22-37;42-credentials-secrets-backup-baseline-v1.0- sysmaint-20261015-001435.txt:70-78 | RESTORE_UNTESTED

---

## 43 — CIS Debian 13 L2 + DISA GPOS + KSPP Mapping

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 43.01 — CIS Debian 13 Level 2 applicability mapping

**Stage / source classification:** `S7 / P1`

**Historical evidence:** CIS Debian 13 v1.1.0 parsed: 332 primary entries, 328 cumulative workstation L2; 10 explicit checks PASS in classifier.

**Identified weakness / gap:** v1.2 leaves 304 EVIDENCE_REVIEW, 12 APPLICABILITY_REVIEW, 1 EXCEPTION_PROPOSED, 1 REVIEW; four other entries outside cumulative L2. Not 304 security failures.

**Implementation task:** Attach exact dated evidence and applicability to every primary control; verify profile membership.

**Core checkpoints:** `KHAHP-43.01A`, `KHAHP-43.01B`, `KHAHP-43.01C`

**Source / evidence status:** 43-standards-control-validation-v1.2-sysmaint-20261015-023110.txt:1-13;43-standards-control-validation-v1.2-sysmaint-20261015- 023110.tsv:2-10 | MAPPING_INCOMPLETE

### 43.02 — DISA GPOS/SRG objective mapping

**Stage / source classification:** `S7 / P1`

**Historical evidence:** CIS Debian 11 STIG-oriented 356 recommendation titles inventoried.

**Identified weakness / gap:** Historical CIS document is not an authoritative Debian13 DISA STIG; direct GPOS/SRG control- ID mapping absent.

**Implementation task:** Use authoritative published DISA GPOS/SRG identifiers and applicability; never claim DISA certification.

**Core checkpoints:** `KHAHP-43.02A`, `KHAHP-43.02B`, `KHAHP-43.02C`

**Source / evidence status:** 43-standards-evidence-mapping-v1.0-sysmaint-20261015-004246.txt:79-87;43-standards-control-validation-v1.2-sysmaint-20261015- 023110.txt:1-10 | MAPPING_INCOMPLETE

### 43.03 — KSPP/kernel-self-protection mapping

**Stage / source classification:** `S7 / P2`

**Historical evidence:** Kernel control candidates linked to earlier section reports.

**Identified weakness / gap:** No item-by-item KSPP recommendation to build/runtime result with kernel feature evidence.

**Implementation task:** Map current KSPP features with exact kernel config and effective runtime proof.

**Core checkpoints:** `KHAHP-43.03A`, `KHAHP-43.03B`, `KHAHP-43.03C`

**Source / evidence status:** 43-standards-evidence-mapping-v1.0-sysmaint-20261015-004246.txt:79-87;39-43-targeted-sysmaint-v1.3-20261015-013719.txt:50-53 | MAPPING_INCOMPLETE

### 43.04 — Kicksecure-native equivalent control mapping

**Stage / source classification:** `S7 / P2`

**Historical evidence:** Kicksecure-native component families and custom additions listed as candidates.

**Identified weakness / gap:** No full inherited-policy vs KHAHP-extension attribution and functional equivalence check.

**Implementation task:** Link package owners/source policy to live settings and label deviations per edition.

**Core checkpoints:** `KHAHP-43.04A`, `KHAHP-43.04B`, `KHAHP-43.04C`

**Source / evidence status:** 43-standards-evidence-mapping-v1.0-sysmaint-20261015-004246.txt:79-89;39-43-targeted-sysmaint-v1.3-20261015-013719.txt:53-54 | PROVENANCE_REVIEW

### 43.05 — Project-extension control mapping

**Stage / source classification:** `S7 / P1`

**Historical evidence:** All prior sections have report file counts and candidate source references.

**Identified weakness / gap:** A file name candidate is not exact assertion-to-control runtime proof.

**Implementation task:** Map each asserted extension to exact output lines, dates, and ongoing enforcement tests.

**Core checkpoints:** `KHAHP-43.05A`, `KHAHP-43.05B`, `KHAHP-43.05C`

**Source / evidence status:** 43-standards-evidence-mapping-v1.0-sysmaint-20261015-004246.txt:35-88;43-standards-control-validation-v1.2-sysmaint-20261015- 023110.txt:1-11 | EVIDENCE_REVIEW

### 43.06 — Exception/N-A/manual-control rationale

**Stage / source classification:** `S7 / P1`

**Historical evidence:** Known applicability cases include USB storage retained, LXQt, Wi-Fi, local Unbound and nftables; proposed exceptions enumerated.

**Identified weakness / gap:** Signed risk-owner approvals and compensating controls not documented.

**Implementation task:** Approve or reject specific N/A/deviation rationales with owner, severity and compensating evidence.

**Core checkpoints:** `KHAHP-43.06A`, `KHAHP-43.06B`, `KHAHP-43.06C`

**Source / evidence status:** 43-standards-control-validation-v1.2-sysmaint-20261015-023110.txt:9-11;39-43-targeted-sysmaint-v1.3-20261015-013719.txt:54-56 | EXCEPTION_REVIEW

### 43.07 — Evidence citation and no-certification disclaimer

**Stage / source classification:** `S7 / P1`

**Historical evidence:** Historical report hash manifest checked and no-certification disclaimer present.

**Identified weakness / gap:** Hashes alone do not mean every source controls map to A/B/C test evidence; no independent validation.

**Implementation task:** Produce signed citation index with assertion ID, report line, checksum, reviewer and decision.

**Core checkpoints:** `KHAHP-43.07A`, `KHAHP-43.07B`, `KHAHP-43.07C`

**Source / evidence status:** 39-43-targeted-sysmaint-v1.3-20261015-013719.txt:48-56;43-standards-evidence-mapping-v1.0-sysmaint-20261015-004246.txt:90- 100 | PARTIAL_EVIDENCE

---

## 44 — Final Acceptance / POC Evidence / Scoring

**Scope:** 7 control families · 21 A/B/C checkpoints.

### 44.01 — Full reboot persistence acceptance

**Stage / source classification:** `S8 / P1`

**Historical evidence:** Original Section 44 verifier script exists outside the archive; NO execution output included in provided archive.

**Identified weakness / gap:** Full reboot-persistence acceptance cannot be assumed from historical boot checks.

**Implementation task:** Run explicitly authorized final acceptance after remediation; compare distinct boots and boot roles.

**Core checkpoints:** `KHAHP-44.01A`, `KHAHP-44.01B`, `KHAHP-44.01C`

**Source / evidence status:** NO_SECTION_44_EXECUTION_REPORT | NO_EXECUTION_REPORT

### 44.02 — USER-mode regression acceptance

**Stage / source classification:** `S8 / P1`

**Historical evidence:** Historic USER tests exist in earlier sections, not a final post-remediation USER regression.

**Identified weakness / gap:** Final USER session behavior and negative tests not accepted.

**Implementation task:** Perform final normal USER boot regression after changes, with agreed safe tests.

**Core checkpoints:** `KHAHP-44.02A`, `KHAHP-44.02B`, `KHAHP-44.02C`

**Source / evidence status:** NO_SECTION_44_EXECUTION_REPORT | NO_EXECUTION_REPORT

### 44.03 — SYSMAINT-mode regression acceptance

**Stage / source classification:** `S8 / P1`

**Historical evidence:** Historic SYSMAINT tests exist in earlier sections, not final post-remediation SYSMAINT regression.

**Identified weakness / gap:** Final SYSMAINT boot-role regression missing.

**Implementation task:** Perform final SYSMAINT read-only regression after changes; no unapproved reboot.

**Core checkpoints:** `KHAHP-44.03A`, `KHAHP-44.03B`, `KHAHP-44.03C`

**Source / evidence status:** NO_SECTION_44_EXECUTION_REPORT | NO_EXECUTION_REPORT

### 44.04 — Network/DNS/firewall/Tor/USB negative-test acceptance

**Stage / source classification:** `S8 / P1`

**Historical evidence:** Earlier USB/DNS/Tor/firewall tests and snapshots exist but are not a single final negative-test suite.

**Identified weakness / gap:** Final fail-closed cross-context behavior and physical peripheral checks unproven.

**Implementation task:** Execute safe non-disruptive negative-test matrix across both roles and physical devices as authorized.

**Core checkpoints:** `KHAHP-44.04A`, `KHAHP-44.04B`, `KHAHP-44.04C`

**Source / evidence status:** NO_SECTION_44_EXECUTION_REPORT | NO_EXECUTION_REPORT

### 44.05 — Recovery/rollback/backup acceptance

**Stage / source classification:** `S8 / P1`

**Historical evidence:** Section42 plan/fixture exists, but no real backup/restore acceptance.

**Identified weakness / gap:** No full recoverable encrypted backup, isolated restore and rollback proof.

**Implementation task:** Close 42.06–42.07 before final acceptance, then record exact recovery outcomes.

**Core checkpoints:** `KHAHP-44.05A`, `KHAHP-44.05B`, `KHAHP-44.05C`

**Source / evidence status:** NO_SECTION_44_EXECUTION_REPORT | BLOCKED_BY_SECTION42

### 44.06 — Evidence completeness, hashes and chain-of-custody bundle

**Stage / source classification:** `S8 / P1`

**Historical evidence:** Archive has many partial SHA256 manifests and audit logs.

**Identified weakness / gap:** No immutable, signed assertion-indexed final 924-assertion bundle.

**Implementation task:** Consolidate source files, hashes, decisions and signatures without customer secrets.

**Core checkpoints:** `KHAHP-44.06A`, `KHAHP-44.06B`, `KHAHP-44.06C`

**Source / evidence status:** NO_SECTION_44_EXECUTION_REPORT | NO_EXECUTION_REPORT

### 44.07 — Final scorecard, residual risk and operator sign-off

**Stage / source classification:** `S8 / P1`

**Historical evidence:** Earlier section status summaries exist, but no final risk-owner acceptance scorecard.

**Identified weakness / gap:** No signed accepted/rejected/N-A decision for every KHAHP assertion and exception.

**Implementation task:** Prepare final attestation only after evidence, remediations and risk decisions; never assert 924 PASS from inventories.

**Core checkpoints:** `KHAHP-44.07A`, `KHAHP-44.07B`, `KHAHP-44.07C`

**Source / evidence status:** NO_SECTION_44_EXECUTION_REPORT | NO_EXECUTION_REPORT

---

## Commercial release annex — 60 proposed validation tests

**Not executed in the source PDF.** The release suites are **R0 / Common (20)**, **R1 / Physical ISO (20)**, **R2 / KVM QCOW2 (10)** and **R3 / VirtualBox OVA (10)**.

### R0 — Common release controls

#### `KHAHP-REL-COM-01` — Reproducible upstream source

**Release risk / evidence:** Source lockfile, build manifest, repeat-build comparison

**Required test:** Record pinned Derivative-Maker commit and build dependencies; second build on clean worker matches documented inputs.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-COM-02` — Package provenance

**Release risk / evidence:** Signed repository inventory and SBOM

**Required test:** Verify signed repositories and record complete package versions and origins.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-COM-03` — Build isolation

**Release risk / evidence:** Build-worker attestation and mounts log

**Required test:** Build in a clean isolated environment without personal home directories.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-COM-04` — Credential exclusion

**Release risk / evidence:** Negative secret-scan report

**Required test:** Scan image for private SSH keys, tokens, Wi-Fi connections, browser profiles and developer secrets; fail on any find.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-COM-05` — Unique machine identity

**Release risk / evidence:** Two-instance comparison

**Required test:** Install/import twice; confirm distinct machine IDs and random state.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-COM-06` — Unique SSH host keys

**Release risk / evidence:** Fingerprint comparison with private keys withheld

**Required test:** Confirm fresh host key generation only when SSH is provisioned, and no developer keys embedded.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-COM-07` — SSH access policy

**Release risk / evidence:** Effective sshd -T and unit-state evidence

**Required test:** Confirm sshd disabled by default, no root login, password/KbdInteractive disabled, public-key access only if activated.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-COM-08` — Privileges and boot-role separation

**Release risk / evidence:** USER negative test and SYSMAINT positive test

**Required test:** Normal USER has no sudo escalation; SYSMAINT maintenance pathway preserved.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-COM-09` — Default firewall

**Release risk / evidence:** Ruleset inventory and approved traffic test

**Required test:** Verify nftables ruleset loads with intended inbound/outbound policy after boot.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-COM-10` — DNS resolver protection

**Release risk / evidence:** Resolver, packet-path and DNS leak tests

**Required test:** Verify Unbound/DNSSEC and permitted upstream policy; test unwanted resolver bypass.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-COM-11` — Network privacy behavior

**Release risk / evidence:** Protocol and policy evidence

**Required test:** Verify LAN discovery suppression and chosen IPv4/IPv6 modes without breaking needed networking.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-COM-12` — MAC and device privacy

**Release risk / evidence:** Effective NetworkManager policy

**Required test:** Verify MAC-randomization policy applies on compatible adapters without retaining developer profiles.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-COM-13` — Mandatory access controls

**Release risk / evidence:** aa-status + negative confinement test

**Required test:** Confirm AppArmor profiles and expected confinement outcomes; document exemptions.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-COM-14` — Kernel hardening

**Release risk / evidence:** Config and runtime comparison

**Required test:** Validate selected kernel compile configuration, cmdline and effective sysctls.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-COM-15` — Audit visibility

**Release risk / evidence:** auditctl and ausearch event evidence

**Required test:** Confirm auditd starts, required watch rules load, and a harmless test event is recorded.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-COM-16` — File integrity monitoring

**Release risk / evidence:** Baseline and controlled mismatch

**Required test:** Generate customer-specific AIDE database after provision and demonstrate a detected test change.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-COM-17` — Upgrade safety

**Release risk / evidence:** Before/after security diff

**Required test:** Apply a supported security update; check protections and configuration drift afterward.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-COM-18` — Backup and restoration

**Release risk / evidence:** Encrypted archive and restore hash evidence

**Required test:** Create encrypted test backup and perform an actual tested restore to disposable target.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-COM-19` — Release signing

**Release risk / evidence:** sha256sum and signature verification outputs

**Required test:** Create checksum, detached signature and validate both on a separate machine.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-COM-20` — Customer documentation and licensing

**Release risk / evidence:** Reviewed release pack and legal sign-off

**Required test:** Include installation, first-boot recovery, limitations, attribution, GPL/source obligations, pricing and support scope.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

### R1 — Physical ISO

#### `KHAHP-REL-ISO-01` — UEFI USB boot

**Release risk / evidence:** Boot logs and installation checklist

**Required test:** Boot media on more than one compliant UEFI implementation.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-ISO-02` — Installer storage detection

**Release risk / evidence:** Installer test log

**Required test:** Detect SATA/NVMe disks correctly and require explicit destructive-write confirmation.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-ISO-03` — Fresh encrypted installation

**Release risk / evidence:** LUKS header metadata and first-boot test

**Required test:** Configure unique LUKS volume and customer-generated unlock material.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-ISO-04` — Encryption recovery

**Release risk / evidence:** Documented recovery exercise

**Required test:** Recover a controlled installation using a separately stored recovery method.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-ISO-05` — Secure Boot enrollment

**Release risk / evidence:** Firmware/MOK and boot logs

**Required test:** Validate signing/MOK strategy on target hardware without sharing build signing keys.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-ISO-06` — Firmware Setup Mode

**Release risk / evidence:** UEFI variable evidence

**Required test:** Check Secure Boot operational state and firmware Setup Mode on capable devices.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-ISO-07` — TPM optional path

**Release risk / evidence:** Capable/noncapable hardware tests

**Required test:** Verify TPM 2.0 discovery and optional enrollment; cleanly handle absence.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-ISO-08` — Intel and AMD support

**Release risk / evidence:** Two hardware test matrices

**Required test:** Install and run acceptance suite on representative Intel and AMD platforms.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-ISO-09` — Graphics and desktop

**Release risk / evidence:** Desktop session tests

**Required test:** Validate LXQt login, graphics drivers, suspend/resume and screen locking.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-ISO-10` — Wireless networking

**Release risk / evidence:** Wi-Fi connection and image scan evidence

**Required test:** Connect using customer-created profile; no developer SSID/profile remains.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-ISO-11` — Ethernet and hotplug

**Release risk / evidence:** Adapter / firewall behavior log

**Required test:** Verify Ethernet and safe network-adapter handling within firewall policy.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-ISO-12` — USBGuard defaults

**Release risk / evidence:** Controlled physical hotplug matrix

**Required test:** Test approved USB storage and mouse against unknown keyboards, phones and NICs per policy.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-ISO-13` — Installer device safety

**Release risk / evidence:** Abort test evidence

**Required test:** Check wrong-target protection, cancellation and recovery from interrupted installation.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-ISO-14` — DMA/IOMMU capabilities

**Release risk / evidence:** Per-device IOMMU evidence

**Required test:** Verify IOMMU claims on platforms that expose them; document hardware exclusions.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-ISO-15` — Signed module lifecycle

**Release risk / evidence:** Module signer and update logs

**Required test:** Verify required DKMS modules load and remain signed through kernel update.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-ISO-16` — Physical webcam/microphone

**Release risk / evidence:** Consent-based device test

**Required test:** Verify privacy/device access controls on actual peripherals.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-ISO-17` — Power and RAM-wipe process

**Release risk / evidence:** Controlled restart/power evidence

**Required test:** Exercise safe shutdown behavior and log any untestable memory-erasure claims.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-ISO-18` — BIOS recovery restrictions

**Release risk / evidence:** Operator checklist signed off

**Required test:** Check firmware password, external boot policy and recovery pathway without capturing password.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-ISO-19` — Multi-boot/firmware resilience

**Release risk / evidence:** Recovery and firmware update report

**Required test:** Verify normal boot after firmware update or recovery event on test hardware.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-ISO-20` — Fresh-install two-device comparison

**Release risk / evidence:** Cross-install differential report

**Required test:** Compare secrets/identities and security results across separate clean physical installations.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

### R2 — KVM QCOW2

#### `KHAHP-REL-KVM-01` — QCOW2 import and boot

**Release risk / evidence:** Import and boot evidence

**Required test:** Import into supported QEMU/KVM/libvirt and boot using documented virtual firmware.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-KVM-02` — Fresh clone identity

**Release risk / evidence:** Instance fingerprints comparison

**Required test:** Clone twice, verify unique guest identity and optional SSH host keys.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-KVM-03` — Virtual firmware choice

**Release risk / evidence:** OVMF/firmware settings and boot logs

**Required test:** Document and verify UEFI or legacy guest boot requirement.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-KVM-04` — Virtual TPM support

**Release risk / evidence:** vTPM test matrix

**Required test:** Check vTPM-compatible profile or documented nonavailability without claiming physical TPM.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-KVM-05` — Host-guest firewall isolation

**Release risk / evidence:** Traffic negative tests

**Required test:** Verify guest nftables policy and host NAT/bridged network restrictions.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-KVM-06` — Guest disk encryption

**Release risk / evidence:** Key uniqueness and recovery test

**Required test:** Verify per-guest LUKS provisioning where promised or an explicit host-only encryption limitation.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-KVM-07` — Virtio device support

**Release risk / evidence:** Virtio compatibility checklist

**Required test:** Test storage, network, entropy and guest drivers without unnecessary privileges.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-KVM-08` — KVM snapshot and restore

**Release risk / evidence:** Snapshot and hash comparison

**Required test:** Restore snapshot on isolated test host and verify integrity after rollback.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-KVM-09` — KVM version regression

**Release risk / evidence:** Version matrix and results

**Required test:** Run tests on minimum and current supported QEMU/KVM versions.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-KVM-10` — QCOW2 sanitized release

**Release risk / evidence:** Archive/metadata and secret-scan gate

**Required test:** Confirm no build-host paths, cached IDs, snapshots or writable shared resources ship.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

### R3 — VirtualBox OVA

#### `KHAHP-REL-OVA-01` — OVA packaging and import

**Release risk / evidence:** Import checklist and log

**Required test:** Import OVA on supported VirtualBox host editions.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-OVA-02` — Unique identity on import

**Release risk / evidence:** Two-import comparison

**Required test:** Perform two independent imports; ensure fresh machine and SSH identities.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-OVA-03` — Clipboard and drag-drop

**Release risk / evidence:** VBox configuration inspection

**Required test:** Verify disabled by default unless customer explicitly opts in.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-OVA-04` — Shared-folder isolation

**Release risk / evidence:** Host/guest negative test

**Required test:** Verify shared folders absent and host filesystem not exposed.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-OVA-05` — USB passthrough restriction

**Release risk / evidence:** VirtualBox USB policy and test

**Required test:** Verify no unauthorized automatic host USB attachment.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-OVA-06` — VirtualBox networking

**Release risk / evidence:** Network path and DNS checks

**Required test:** Check NAT/bridging policy, blocked inbound traffic and resolver behavior.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-OVA-07` — Guest addition safety

**Release risk / evidence:** Module and service inventory

**Required test:** Review installed guest integration modules and least-privilege behavior.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-OVA-08` — Virtual disk recovery

**Release risk / evidence:** Restore integrity report

**Required test:** Restore test appliance snapshot/disk backup without repeating machine keys.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-OVA-09` — Supported host matrix

**Release risk / evidence:** Host compatibility matrix

**Required test:** Test supported Windows, Linux and macOS host combinations as stated in release notes.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

#### `KHAHP-REL-OVA-10` — OVA clean release gate

**Release risk / evidence:** OVA scanner and signing result

**Required test:** Inspect OVA contents for identifiers, credentials and dangerous VM defaults.

**Status in source:** PLANNED / NOT EXECUTED • KHAHP v0.9 proposed release suite

---

## Final acceptance and evidence custody

Acceptance requires traceable decisions for all applicable A/B/C assertions, controlled verification in both USER and SYSMAINT contexts, tested rollback and backup recovery, a reproducible package and artifact manifest, approved exceptions, and documented owner sign-off. The commercial releases require additional independent fresh-install and virtual-platform verification.

**This Markdown is a faithful technical conversion and reformatting of the supplied PDF; it is not a new security assessment.** No operational configuration has been changed and no new product build has been executed in creating these files.
