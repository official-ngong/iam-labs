# Identity and Access Management — Hands-on Labs (1–12)

> **Course:** Linux Security & Identity Management  
> **Platform:** AlmaLinux 9 · Ubuntu 22.04 · CentOS 7 (VMs)  
> **Submission:** April 2026

---

## 📋 Overview

This repository contains the lab report and supporting documentation for **Labs 1–12** of the IAM Hands-on Lab series. Each lab was performed inside virtual machines and focuses on core Linux identity, access control, and system hardening concepts.

---

## 🗂️ Repository Structure

```
├── README.md                          ← This file
├── IAM_Lab_Report_Labs1-12.pdf       ← Full lab report (submitted PDF)
```

---

## 📚 Lab Summaries

| # | Lab Title | Key Tools / Concepts |
|---|-----------|----------------------|
| 1 | Assigning Limited sudo Privileges | `visudo`, command aliases, STORAGE alias |
| 2 | Disabling the sudo Timer | `Defaults timestamp_timeout`, `sudo -k` |
| 3 | Encrypted Home Directory | `ecryptfs-utils`, `adduser --encrypt-home` |
| 4 | Password Complexity Criteria | `pam_pwquality`, `pwquality.conf`, minlen, minclass |
| 5 | Account & Password Expiry | `useradd -e`, `usermod`, `chage`, `passwd -e` |
| 6 | Detecting Compromised Passwords | HaveIBeenPwned API, k-Anonymity, `pwnedpasswords.sh` |
| 7 | Configuring pam_tally2 | `pam_tally2`, account lockout, PAM stack configuration |
| 8 | Distributed Identity Management | FreeIPA, Adsys, SSSD, Kerberos, LDAP |
| 9 | SUID/SGID File Auditing | `find -perm /6000`, `chmod 4755`, `diff` |
| 10 | Extended File Attributes | `chattr +a`, `chattr +i`, `lsattr` |
| 11 | Shared Group Directory + ACLs | `chmod 3770`, SGID, sticky bit, `setfacl`, `getfacl` |
| 12 | SELinux Type Enforcement | `chcon`, `restorecon`, `ls -Z`, `httpd_sys_content_t` |

---

## 🔧 Environment

- **AlmaLinux 9** — Primary VM for sudo, PAM, SELinux, and IAM labs
- **Ubuntu 22.04** — Used for ecryptfs, pwquality, and package-based labs
- **CentOS 7** — Used for pam_tally2 (module deprecated in newer distros)
- **Parrot Security 7.0**

---

## 💡 Key Takeaways

- **Least privilege** is enforced at multiple layers: sudo rules, PAM modules, file permissions, ACLs, and SELinux policies.
- **PAM** provides a modular and stackable authentication framework — misconfiguration in one module cascades to the entire login flow.
- **SELinux Mandatory Access Control** operates independently of standard DAC permissions. A file with world-readable permissions can still be blocked by an incorrect SELinux type context.
- **eCryptFS** provides per-user transparent encryption at the VFS layer without requiring full-disk encryption.
- **POSIX ACLs** extend the Unix permission model to allow fine-grained, per-user access control beyond the owner/group/other triad.
- **HaveIBeenPwned k-Anonymity** allows safe, privacy-preserving password breach checking without exposing full credentials.

---

## 📁 Report

The full lab report (`IAM_Lab_Report_Labs1-12.docx`) contains:
- Step-by-step command execution for each lab
- Observed outputs and results tables
- Outcome analysis per lab
- Security implications and best practices

---

