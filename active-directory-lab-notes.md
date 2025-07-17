
# Active Directory Lab Notes

This file documents my practical experience and coursework involving Microsoft Active Directory across multiple classes and labs.

---

## 🧠 Overview

Active Directory (AD) is a Microsoft directory service used for user and resource management in enterprise networks. I trained on AD concepts and configurations across several college-level courses and cybersecurity labs.

---

## 🔧 Lab Activities

### ✅ Domain Services Setup
- Created and managed Windows Server virtual machines as domain controllers
- Configured forest and domain structures including trust relationships
- Installed and verified DNS integration with AD

### ✅ User & Group Management
- Created, modified, and deleted user accounts using GUI and PowerShell
- Assigned group memberships and created Organizational Units (OUs)
- Practiced implementing Group Policy Objects (GPOs) to enforce password policies and restrictions

### ✅ Permissions & Access Control
- Set file and folder-level NTFS permissions using security groups
- Audited and tested user access based on group assignments
- Used `gpresult` and `rsop.msc` to troubleshoot policy application issues

### ✅ AD Enumeration & Security
- Simulated attacker enumeration using `net user`, `whoami`, `dsquery`, and `net group`
- Studied common misconfigurations like:
  - Excessive privileges
  - Insecure service account usage
  - Lack of audit logging
- Discussed lateral movement techniques and privilege escalation paths in AD environments

---

## 🛠️ Tools & Skills Used
- Windows Server 2016/2019
- PowerShell scripting basics
- Active Directory Users and Computers (ADUC)
- Group Policy Management Console (GPMC)
- Command line tools: `dsquery`, `net group`, `gpresult`, `whoami`

---

## 📌 Key Takeaways
- Built foundational experience in enterprise-level identity management
- Understood how AD structures scale and enforce security policy
- Learned both administrative and attacker-facing perspectives for AD environments
