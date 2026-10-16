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

Offline Linux kernel sysctl hardening auditor (CIS / STIG / KSPP)

---

## ✨ Features

- Tolerant sysctl.conf / sysctl.d parser — comments, '-' ignore-failure prefix, '/' or '.' key syntax, glob keys (net.ipv4.conf.*.rp_filter), bad lines recorded instead of crashing
- systemd-sysctl / procps load-order emulation — /etc > /run > /usr/local/lib > /usr/lib > /lib, lexical drop-in ordering, /dev/null masking, symlink de-duplication, /etc/sysctl.conf last
- Offline --root support for collected filesystem trees (forensic images, containers, golden images)
- Live /proc/sys snapshot reader + `sysctl -a` dump import; live-vs-persistent drift detection
- 60+ hardening rules — IPv4, IPv6, memory, ASLR, kernel pointer leaks, BPF, ptrace, userns, fs links, core dumps, TTY line disciplines, io_uring
- Three baselines: CIS, DISA STIG, KSPP (+ strictest)
- Duplicate / conflicting / weakening override map across every drop-in, with file:line provenance
- Per-interface override semantics (AND / OR / MAX) for net.ipv4.conf.<iface>.* keys
- Config file permission checks (owner / writable)
- A+…F grade, per-category subscores, CWE + MITRE
- Remediation drop-in generator with exact lines
- Export TXT / MD / JSON / CSV / SARIF 2.1.0
- Snapshot + regression diff, CI gates (--fail-on)
- --demo self-test with synthetic sysctl.d tree

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OSysctl
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
