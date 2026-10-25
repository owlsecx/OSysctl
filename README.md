# 🦉 OSysctl

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OCore-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
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

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
