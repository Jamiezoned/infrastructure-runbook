# infrastructure-runbook
Laptop imaging, domain join, and GPO verification procedure – step-by-step IT deployment guide.
**Goal:** Standardized procedure for laptop imaging, domain join, and post-deployment verification in small business or field environments.

---

## 🧩 Tools Used
- **Clonezilla** – for base image deployment  
- **Windows 10/11** – endpoint OS  
- **Active Directory (AD)** – domain join and GPO application  
- **PowerShell** – post-install automation  
- **WSUS** – patch management  
- **BitLocker & Defender** – endpoint protection  

---

## ⚙️ Procedure Overview

### 1️⃣ Imaging
1. Boot target device via **USB (Clonezilla)**  
2. Select the appropriate base image and restore to disk  
3. Reboot and verify driver installation + network connectivity  

### 2️⃣ Domain Join
1. Log in as local admin  
2. Run post-install PowerShell script:  
   - Rename device (naming convention: SITE-DEVICE#)  
   - Join domain (`Add-Computer -DomainName corp.local -Restart`)  
   - Set NTP sync and verify DNS records  

### 3️⃣ Verification Checklist
- ✅ `gpupdate /force` runs without error  
- ✅ Computer appears under correct OU in AD  
- ✅ Defender is active and up-to-date  
- ✅ WSUS shows recent contact  
- ✅ User login via domain credentials works  

---

## 📋 Example File Structure
infrastructure-runbook/
├─ README.md
├─ screenshots/
│ ├─ 00-usb-boot.png
│ ├─ 10-domain-join.png
│ └─ 20-gpupdate.png
├─ scripts/
│ └─ PostInstall.ps1
└─ checklists/
├─ pre-deployment-checklist.md
└─ post-deployment-verification.md

yaml
Kopiera kod

---

## 📸 Screenshots (coming soon)
_Add screenshots of Clonezilla, post-install PowerShell window, and GPO verification._

---

## 🧠 Notes
This runbook was created to demonstrate hands-on understanding of:
- System imaging and configuration standardization  
- Active Directory and Group Policy basics  
- Preventive maintenance mindset (zero-downtime focus)  

---

## 🪪 License
MIT License – free for educational and professional reference.

## 🗓️ Project Timeline & History

- **Concept & field testing** — Aug 2024 – Jun 2025  
  Initial lab runs for imaging processes and post-install checks during on-site shifts.

- **Documentation & runbook authoring** — Oct 2025  
  Consolidated step-by-step imaging guide, post-install PowerShell steps, and pre/post checklists.

- **Current state** — Ongoing  
  Continual improvements: adding screenshots, sample logs, and packaging for quick deployment in field environments.

