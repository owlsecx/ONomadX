# 🦉 ONomadX

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OScan-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **ONomadX** — HashiCorp Nomad Security Auditor

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

HashiCorp Nomad offline security auditor (agent configs, job specs, ACL policies)

---

## ✨ Features

- Offline, strictly read-only auditor for Nomad only (agent configs, job specs, ACL policies) — no API calls, no network, nothing is ever modified
- Stdlib HCL-subset parser — blocks, labels, attributes, lists, maps/objects, heredocs (<<EOF / <<-EOF), comments (#, //, /* */), interpolation kept verbatim
- JSON agent configs + `nomad job inspect` JSON + `nomad acl policy info -json` normalisation
- Directory-merge semantics for /etc/nomad.d/*.hcl (absence checks evaluated on the merged agent view)
- 90+ rules — ACL, TLS/mTLS, gossip, listeners, UI, drivers, host volumes, Vault, tasks, images, resources, templates, artifacts, workload identity, ACL policies
- Secret scanning (Nomad/Vault tokens, PEM keys) with masking everywhere — reports never carry secrets
- File-permission checks (TLS keys, certs, data_dir, plugin_dir) with optional --root for offline images
- Every rule carries severity, CWE, MITRE ATT&CK and remediation; weighted score + A+…F grade
- Exports TXT / MD / JSON / CSV / SARIF 2.1.0
- --fail-on (exit 2), --demo self-test (exit 3), --list-rules, --explain, hardened templates

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./ONomadX
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
