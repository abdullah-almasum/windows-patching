# 🔧 Windows Patching Automation with Ansible

This repository provides an Ansible playbook for automating Windows Server patching using **WinRM**, suitable for use with **Red Hat Ansible Automation Platform (AAP)**.

---

## 📦 Features

- ✅ Windows Update search & install (Security, Critical, Definition)
- 🔄 Automatic reboot handling
- 🛡️ Defender Antivirus update support
- 🧠 Summary of patches (installed, skipped, filtered)
- 🔍 Compatible with AAP Job Templates and Git Project Sync

---

## 🖥️ Inventory Example (`inventory.yml`)

```yaml
all:
  children:
    windows:
      hosts:
        win-serv-22:
          ansible_host: Target Host IP
          ansible_user: Target Host Username
          ansible_password: "YourSecurePassword"
          ansible_connection: winrm
          ansible_winrm_transport: basic
          ansible_port: 5985

#Run the Playbook
-----------------
ansible-playbook -i inventory.yml winpatch.yml
