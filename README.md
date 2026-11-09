# Awesome-Software-Update-Patch-Management

# Awesome Software Update & Patch Management

> A curated list of top Software Update and Patch Management platforms — both SaaS/Hosted commercial solutions and open-source alternatives for centrally deploying updates, enforcing compliance, and securing endpoint fleets.
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [ManageEngine Patch Manager Plus](#manageengine-patch-manager-plus)
  - [Automox](#automox)
  - [Action1](#action1)
  - [PDQ Deploy](#pdq-deploy)
  - [Ivanti Patch Management](#ivanti-patch-management)
  - [NinjaOne Patching](#ninjaone-patching)
  - [GFI LanGuard](#gfi-langyard)
  - [Microsoft Intune Patching](#microsoft-intune-patching)
  - [SolarWinds Patch Manager](#solarwinds-patch-manager)
- [Open-Source Software](#-open-source-software)
  - [PatchMon](#patchmon)
  - [Tactical RMM](#tactical-rmm)
  - [Wazuh](#wazuh)
  - [mustra](#mustra)
  - [Cimian](#cimian)
  - [Windows Update Automation Ansible](#windows-update-automation-ansible)
  - [ec2patcher](#ec2patcher)
  - [wesng](#wesng)
- [Comparison at a Glance](#-comparison-at-a-glance)
- [Contributing](#-contributing)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted Software Update and Patch Management platforms. These are not open-source but are included as reference points for feature comparison.

### ManageEngine Patch Manager Plus
**Type:** Comprehensive patch management for mixed OS fleets
Patch Manager Plus provides automated patch deployment for Windows, macOS, Linux, and third-party applications, with support for both cloud and on-premises deployment. It offers patch testing, approval workflows, and compliance reporting, targeting mid-market IT teams.

### Automox
**Type:** Cloud-native patch management with automation
Automox provides agent-based patch management for Windows, macOS, and Linux, with automated patching policies, third-party software updates, and real-time compliance visibility. Positioned for IT teams wanting to eliminate manual patching workflows.

### Action1
**Type:** Cloud-based patch management and endpoint security
Action1 offers patch management, remote access, and endpoint security from a single cloud console, with a free tier for up to 200 endpoints. Suited for small to mid-sized organizations wanting automated patching without on-premises infrastructure.

### PDQ Deploy
**Type:** On-premises software deployment for Windows
PDQ Deploy provides software deployment and patch management for Windows environments, with a library of pre-built packages and custom deployment capabilities. Often paired with PDQ Inventory for asset management.

### Ivanti Patch Management
**Type:** Enterprise patch management within Ivanti suite
Ivanti provides patch management as part of its broader endpoint security and IT service management suite, covering Windows, macOS, and Linux with third-party application patching and compliance reporting.

### NinjaOne Patching
**Type:** Unified RMM with patch management
NinjaOne combines RMM with automated patching, covering Windows, macOS, and Linux, with patch approval policies, third-party software updates, and compliance dashboards. Suited for MSPs and IT teams wanting unified endpoint management.

### GFI LanGuard
**Type:** Network security scanner and patch management
GFI LanGuard provides vulnerability scanning and patch management for Windows environments, with network discovery, missing patch detection, and remediation capabilities.

### Microsoft Intune Patching
**Type:** Windows Update for Business management
Microsoft Intune provides Windows Update for Business policies, enabling IT to control update rings, deferrals, and deadlines for Windows endpoints. Deeply integrated with Microsoft 365 and Entra ID.

### SolarWinds Patch Manager
**Type:** Patch management within SolarWinds IT portfolio
SolarWinds Patch Manager extends Microsoft WSUS with third-party patching, reporting, and automation, targeting organizations already using SolarWinds for IT management.

---

## 🟩 Open-Source Software

Self-hosted, community-driven Software Update and Patch Management tools. The open-source ecosystem has matured significantly, led by PatchMon for Linux fleet patching and Tactical RMM for mixed-OS endpoint management.

### PatchMon
**Stack:** Go / Docker / React | **License:** AGPL-3.0
PatchMon is the most purpose-built open-source patch management platform for Linux fleets, with FreeBSD and Windows agent support. It provides a **single pane of glass** for monitoring, patching, and securing servers, with an outbound-only agent (no inbound ports required) and a single Go binary with embedded React UI . Key capabilities include **dry-run validation** (preview the exact package transaction before touching production), **approve and execute** with per-host audit trails, **scheduled patching** (immediate, maintenance window, or delayed rollout), **live patch streaming** over WebSocket, **selective patching** (specific packages, security-only, or full upgrade), and **patch history and audit** . It also offers package inventory, repository tracking, Docker monitoring, OpenSCAP compliance scanning, RBAC, OIDC SSO, and a web SSH terminal with AI assistant . Deploys via Docker Compose or Proxmox LXC, with minimum specs of 2 vCPU and 2 GB RAM . A managed cloud option is available with a 14-day trial .
**Best for:** IT and operations teams wanting a self-hosted, Linux-first patch management platform with genuine approval workflows, dry-run validation, and audit trails, without per-endpoint licensing.

### Tactical RMM
**Stack:** Python / Django / Go / MeshCentral | **License:** Open Source (per project)
Tactical RMM is an open-source remote monitoring and management platform with **Windows patch management** as a core feature, alongside remote desktop control, remote shell, file browser, script execution, and software deployment via Chocolatey . It supports Windows 7 through 11 and Server 2008R2 through 2022, plus Linux and Mac agents . The update process is script-managed with explicit warnings against manual intervention or cron automation . **Trade-off:** Windows patch management is the primary tested path; Linux and Mac patching are less mature .
**Best for:** IT teams and MSPs wanting a self-hosted RMM with Windows patching and broad remote management capabilities, accepting the operational overhead of the full platform.

### Wazuh
**Stack:** C++ / OpenSearch | **License:** GPL-2.0
Wazuh is an open-source SIEM and XDR platform with a **Vulnerability Detector** module that integrates NVD, OVAL, MSU, and Canonical feeds to identify vulnerable software across monitored endpoints . It uses Syscollector to inventory installed software and correlate versions against CVE databases, generating SOC-style alerts with CVSS scores, severity, and exploit availability . **Important distinction:** Wazuh **detects** vulnerabilities and missing patches but does not execute patching—it provides the visibility layer that informs patch management workflows . Active response can trigger scripted remediation, but automated patching is not a built-in feature.
**Best for:** Security teams wanting open-source vulnerability detection and CVE correlation to prioritize patching, often paired with a dedicated patching tool.

### mustra
**Stack:** Go / NATS | **License:** AGPL-3.0
mustra is an open-source fleet management and endpoint operations platform with a lightweight Go agent, NATS as the outbound-only message backbone, and a web console for live inventory, **patch management**, and vulnerability data . It is explicitly designed for endpoint operations at scale, with the Go agent minimizing resource footprint and NATS providing reliable outbound communication. **Note:** The project is newer and the PyPI package exists primarily for name reservation; verify maturity and documentation before production deployment .
**Best for:** Teams wanting a lightweight, Go-based fleet management platform with patch management capabilities and minimal agent overhead.

### Cimian
**Stack:** C# | **License:** Open Source (per repository)
Cimian is a managed software deployment system for Windows, supporting `.msi`, `.msix`, `.exe`, `.nupkg`, and PowerShell scripts . It provides a `managedsoftwareupdate` CLI with flags for auto-updates, cache validation, check-only mode, selective item installation, pre/post-flight scripts, and self-update management . It is a **software deployment and update** tool rather than a full patch management platform, but it fills the gap for Windows software distribution and update orchestration.
**Best for:** Windows administrators wanting a managed software deployment system for `.msi`/`.exe` packages and PowerShell scripts, with CLI-driven automation and self-update support.

### Windows Update Automation Ansible
**Stack:** Ansible / PowerShell | **License:** Open Source (per repository)
An Ansible playbook for automated patch management on Windows 10/11 endpoints, supporting third-party updates via Chocolatey and Windows Updates via `PSWindowsUpdate` . It includes endpoint configuration (WinRM/SSH setup), scheduled execution via cron (every Sunday at 11:30 PM by default), and logging for auditing . **Trade-off:** It is a playbook, not a platform—you manage inventory, scheduling, and execution yourself.
**Best for:** Ansible-centric teams wanting a scriptable, version-controlled approach to Windows patch automation without adopting a dedicated patch management platform.

### ec2patcher
**Stack:** Python | **License:** Open Source (per PyPI)
ec2patcher is a lightweight CLI tool for patching Ubuntu EC2 instances based on Canonical CVE advisories. It analyzes APT candidates and CVE applicability on a workstation, builds a patch plan with exact versions and SHA256 hashes, then executes approved patches via SSH with validation at each step (drift detection, checksum verification, simulation before install) . It supports Ubuntu releases with APT; Amazon Linux 2023 is analyzed but not patchable . **Trade-off:** Ubuntu-only, CLI-driven, no web UI or fleet dashboard.
**Best for:** Teams running Ubuntu on EC2 wanting a scriptable, safety-focused patching CLI with approval gates and no agent installation.

### wesng
**Stack:** Python | **License:** Open Source (per repository)
wesng (Windows Exploit Suggester - Next Generation) is a set of utilities for Windows vulnerability assessment and patch management auditing . It analyzes installed updates against a consolidated vulnerability database to identify missing security patches and recommend publicly available exploits . It maintains accuracy by synchronizing remote security bulletins into a local database and cross-referencing identified gaps against official update catalogs . **Focus:** Auditing and exploit mapping rather than patching execution.
**Best for:** Security assessors and penetration testers wanting to audit Windows patch levels and map missing patches to known exploits.

---

## 📊 Comparison at a Glance

| Software | License | Stack | Patching Execution | Vulnerability Detection | Fleet Dashboard | Self-Hosted | Best For |
|----------|---------|-------|--------------------|--------------------------|-----------------|-------------|----------|
| **ManageEngine** | Proprietary | Cloud/On-prem | ✅ | ✅ | ✅ | (On-prem) | Mixed OS enterprise |
| **Automox** | Proprietary | Cloud | ✅ | ✅ | ✅ | ❌ | Cloud-native automation |
| **Action1** | Proprietary | Cloud | ✅ | ✅ | ✅ | ❌ | SMB (200 free endpoints) |
| **PDQ Deploy** | Proprietary | On-prem | ✅ | (Inventory) | ✅ | (On-prem) | Windows software deployment |
| **NinjaOne** | Proprietary | Cloud | ✅ | ✅ | ✅ | ❌ | Unified RMM + patching |
| **Intune** | Proprietary | Cloud | ✅ (Windows) | (Compliance) | ✅ | ❌ | Microsoft 365 estates |
| **PatchMon** | AGPL-3.0 | Go/Docker | ✅ (Dry-run + approve) | ✅ (Inventory) | ✅ | ✅ | Linux-first fleet patching |
| **Tactical RMM** | Open Source | Python/Go | ✅ (Windows) | (Via checks) | ✅ | ✅ | Windows RMM + patching |
| **Wazuh** | GPL-2.0 | C++/OpenSearch | ❌ (Detect only) | ✅ (CVE feeds) | ✅ | ✅ | Vulnerability detection + prioritization |
| **mustra** | AGPL-3.0 | Go/NATS | ✅ | ✅ | ✅ | ✅ | Lightweight Go fleet mgmt |
| **Cimian** | Open Source | C# | ✅ (Windows software) | ❌ | (Check) | ✅ | Windows software deployment |
| **ec2patcher** | Open Source | Python | ✅ (Ubuntu EC2) | ✅ (CVE plan) | ❌ (CLI) | ✅ | Scriptable Ubuntu patching |
| **wesng** | Open Source | Python | ❌ (Audit only) | ✅ (Exploit mapping) | ❌ | ✅ | Windows patch auditing |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source Software Update or Patch Management tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source. Note that the open-source ecosystem **splits** between dedicated patching platforms (PatchMon, Tactical RMM), vulnerability detection engines (Wazuh), and scriptable automation tools (ec2patcher, Ansible playbook, Cimian). **PatchMon** is currently the most purpose-built open-source patch management platform, with genuine dry-run validation, approval workflows, and audit trails that commercial tools charge per-endpoint for [citation:8][citation:9]. **Wazuh** is the strongest choice for vulnerability detection and CVE prioritization to inform patching decisions [citation:6]. For Windows-centric teams, **Tactical RMM** provides patching within a broader RMM platform [citation:12].

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
