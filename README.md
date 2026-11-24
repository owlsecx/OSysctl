# 🦉 OSysctl

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OCore-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-orange?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **OSysctl** — Kernel sysctl Hardening Auditor

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview


OSysctl is an offline, strictly read-only Linux kernel sysctl hardening auditor that parses sysctl.conf and sysctl.d with full load-order emulation. It compares live /proc/sys values against persistent configuration to detect drift, applies 60+ hardening rules benchmarked against CIS, DISA STIG and KSPP, and maps duplicate/conflicting overrides with file:line provenance. It produces an A+ to F grade, a remediation drop-in generator, and TXT/MD/JSON/CSV/SARIF exports.

---

## ✨ Features


- Tolerant sysctl.conf / sysctl.d parser (ignore-failure prefix, / or . key syntax, glob keys, bad-line capture)
- systemd-sysctl / procps load-order emulation with drop-in precedence, /dev/null masking and symlink dedup
- Live /proc/sys snapshot and sysctl -a import with live-vs-persistent drift detection
- 60+ rules across IPv4/IPv6, memory, ASLR, BPF, ptrace, userns, fs links and core dumps
- CIS, DISA STIG and KSPP baselines, with a duplicate/conflicting override map and file:line provenance
- A+..F grade, remediation drop-in generator, snapshot/regression diff and TXT/MD/JSON/CSV/SARIF export

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage


```bash
./OSysctl --scan --baseline kspp --format sarif -o sysctl.sarif
./OSysctl --live --diff --fix
./OSysctl --root /mnt/image --fail-on high --matrix
./OSysctl --demo
./OSysctl --help
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 275+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

Proprietary — © 2026 Owlsec LLC. All rights reserved.

*Tools are distributed as pre-built executables. Source code is proprietary.*

---

## 🔍 Verification & Transparency

This tool is closed-source. These files let you see exactly what is inside it,
without the source:

- [`SBOM.cdx.json`](SBOM.cdx.json) — CycloneDX inventory: SHA-256 of this
  binary, bundled CPython version, and every bundled library with its exact
  version and license. Feed it to Grype, Trivy or Dependency-Track to audit
  our dependencies for CVEs yourself.
- [`THIRD-PARTY-NOTICES.md`](THIRD-PARTY-NOTICES.md) — the full license text
  of every third-party component, extracted from this binary.

**No telemetry, no analytics, no licence check-in.** This tool does not phone
home. Verify that claim yourself:

```bash
sudo strace -f -e trace=network ./OSysctl --help   # watch every network call
firejail --net=none ./OSysctl --help               # deny the network entirely
```

Release signing, GPL compliance and vulnerability reporting:
[**TRUST.md**](https://github.com/owlsecx/owl-os/blob/main/TRUST.md)
