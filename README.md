# 🦉 ONomadX

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OScan-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-orange?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **ONomadX** — HashiCorp Nomad Security Auditor

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

ONomadX is an offline, read-only HashiCorp Nomad security auditor for agent HCL/JSON configs, job specs, and ACL policies. It uses a stdlib HCL-subset parser, merges `/etc/nomad.d` directories, scans for secrets (masked), and checks ACL, TLS/mTLS, gossip, drivers, volumes, Vault, templates, and permissions. Reports export to TXT, MD, JSON, CSV, or SARIF.

---

## ✨ Features

- Offline audit of Nomad agent configs, job specs, and ACL policies — no API calls or modifications
- Stdlib HCL-subset parser (blocks, labels, heredocs, comments) plus JSON agent/job/ACL normalisation
- Directory-merge semantics for `/etc/nomad.d/*.hcl` with absence checks on the merged view
- 90+ rules covering ACL, TLS/mTLS, gossip, UI, drivers, host volumes, Vault, tasks, templates, artifacts, workload identity
- Secret scanning (tokens, PEM keys) with masking; optional `--root` permission checks for TLS keys and data_dir
- Severity/CWE/ATT&CK/remediation per rule; score/grade; multi-format export; `--demo` and fail-on gates

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./ONomadX --scan
./ONomadX /etc/nomad.d job.json --format sarif -o nomad.sarif --fail-on high
./ONomadX --demo --list-rules
./ONomadX --help
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
sudo strace -f -e trace=network ./ONomadX --help   # watch every network call
firejail --net=none ./ONomadX --help               # deny the network entirely
```

Release signing, GPL compliance and vulnerability reporting:
[**TRUST.md**](https://github.com/owlsecx/owl-os/blob/main/TRUST.md)
