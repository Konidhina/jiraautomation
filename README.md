# Jira Service Request Automation – DataCenter edition

This tool allows internal teams to raise **Jira Service Desk Service Requests**
using a **single command**, without requiring Jira UI access or REST API knowledge.

---

## ✅ Prerequisites (Required Configuration)

The following variables **must be configured before using this tool**:

1. `jira_pat` – Jira Personal Access Token  
2. `jira_url` – Jira base URL (example: `https://jira.abcd.com`)

These variables **must be stored securely** in an **Ansible Vault** file:

🔧 What This Tool Does

Creates a Service Request in Jira project SDIMD

Uses Jira Service Management REST API

Automatically sets:

Environment: Production

Impact: Single User

Urgency: Medium

Enforces:

Summary and Description are always the same

Jira ticket number and portal URL are displayed after creation


🚀 Usage

raise-sr "Problem / Service request statement"

## 📁 Repository Structure

```text
jira-sr/
├── create_sdimd_sr.yml        # Ansible playbook (Jira SR creation logic)
├── raise-sr                   # User-facing wrapper command
├── README.md
├── .gitignore
└── group_vars/
    └── all/
        └── jira.yml           # Encrypted (Ansible Vault) – NOT committed to Git

