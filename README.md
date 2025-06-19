These are the prerequisites for Windows Server patch automation. Unlike Linux systems that use SSH, Windows machines use WinRM for remote management. 
WinRM must be enabled on the server before proceeding. Below is a production-grade checklist and step-by-step configuration workflow to prepare both Ansible Automation Platform (AAP) and Windows Server 2022 for automated patching.

✅ Prerequisites (Windows Server & AAP)

🔧 On Windows Server 2022 (target)
1. Enable WinRM
• Required for Ansible to communicate with Windows hosts over port 5985 (HTTP) or 5986 (HTTPS).
2. Configure TrustedHosts & Basic Auth
• WinRM by default rejects remote basic-auth. Must allow it explicitly.
3. Ensure PowerShell 5.1 or later
• Ansible uses PowerShell to execute patching commands under the hood.
4. Enable Windows Update Service
• The wuauserv service must be running.
