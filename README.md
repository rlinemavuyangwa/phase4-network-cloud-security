**Title:** Network and Cloud Security Configuration Report – Internship Phase 4

**Intern:** Rulane Hlongwani
**Phase:** 4 
**Focus Areas:** Network Security, Cloud Security, Mobile Device & BYOD Security, Security Architecture & Design

---

## 1. Overview

Phase 4 of the cybersecurity internship focused on securing network and cloud environments. The goal was to configure firewall rules for segmentation using pfSense, enforce role-based access using Google Cloud IAM, implement mobile/BYOD security policies, and conduct basic network security audits. The output of this phase is this configuration report and documentation pushed to GitHub.

---

## 2. pfSense Firewall & Network Segmentation

**Tools:** pfSense (VirtualBox), OpenCart (Ubuntu VM), Android VM
**Network Segments:**

* **LAN:** Internal systems (Ubuntu + OpenCart)
* **DMZ:** Public services (simulated via OpenCart web)
* **WAN:** Internet access

**Configuration Steps:**

* Configured LAN, WAN, and DMZ interfaces on pfSense
* Set up firewall rules:

  * Allow LAN → DMZ
  * Block DMZ → LAN
  * WAN → DMZ (Only HTTP/HTTPS allowed)
* Bridged Adaptor rules configured for port forwarding to OpenCart

**Evidence:**

* Screenshots of users & roles, interface setup

---

## 3. Google Cloud IAM Role-Based Access Control

**Project:** `intern-network-security`
**IAM Accounts Used:**

* `main@gmail.com` – Owner/Admin Role
* `second@gmail.com` – Editor/Manager Role

**Custom Role:** `OpenCartLogViewer`
**Permissions:** `logging.logEntries.list`, `compute.instances.get`, `resourcemanager.projects.get`

**Purpose:** To simulate admin vs. manager roles accessing cloud logs and resources.

**Access Controls Mapped to OpenCart:**

* `main@gmail.com` → OpenCart Admin (`giginini`)
* `second@gmail.com` → OpenCart Manager (`managerstore`)

---

## 4. Mobile Device / BYOD Security Policy Implementation

**Device Used:** Android VM (VirtualBox)
**Scenario Simulated:**

* BYOD user accessing OpenCart via mobile browser
* Access monitored via pfSense firewall logs
* Tested blocking Android device IP to simulate MDM-level restrictions

**BYOD Policy Highlights:**

* Require encryption on personal devices
* Prohibit rooted/jailbroken devices
* Enforce strong authentication (PIN/password)
* Restrict app installation (simulated only)

---

## 5. Network Security Audit

**Tool Used:** pfSense Logs
**Activities:**

* Scanned OpenCart server using GCP
* Logged access attempts and system activity in GCP audit logs

**Findings:**

| Component      | Issue                             | Risk Level | Recommendation                     |
| -------------- | --------------------------------- | ---------- | ---------------------------------- |
| OpenCart VM    | Port 22 exposed to WAN            | High       | Restrict SSH via firewall          |
| pfSense Rules  | DMZ allowed access to LAN         | Medium     | Block DMZ → LAN completely         |
| Android Device | Accessed insecurely (HTTP)        | High       | Enforce HTTPS and use certificates |
| GCP IAM        | Overbroad permissions for manager | Medium     | Use least privilege for non-admins |

---

## 6. Conclusion

This phase successfully demonstrated core competencies in firewall configuration, cloud IAM security, mobile/BYOD access control, and audit procedures. Screenshots and configurations were documented and tested in real-time lab conditions. The work reflects a comprehensive approach to modern network and cloud security.

---

## 7. GitHub Repository

A GitHub repository has been created to host all documentation, screenshots, and configs related to this phase.

**GitHub Repo:** [https://github.com/rulanehlongwani/phase4-network-cloud-security](https://github.com/rulanehlongwani/phase4-network-cloud-security)

**Contents:**

* `/screenshots/` – pfSense, IAM, OpenCart, Android VM screenshots
* `/configs/` – Firewall rules, IAM policies 
* `README.md` – Summary of activities, how to reproduce setup
* `Network_Cloud_Security_Report_Phase4.pdf` – Final Report

---

✅ **Phase 4 Complete.**
🚀 Ready for Phase 5.
