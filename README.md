# Jira Service Request Automation – SDIMD

This tool allows internal teams to raise **Jira Service Desk (SDIMD) Service Requests**
using a **single command**, without needing Jira UI access or API knowledge.

---

## 🔧 What this tool does
- Creates a **Service Request** in project **SDIMD**
- Uses Jira Service Management REST API
- Automatically sets:
  - Environment: **Production**
  - Impact: **Single User**
  - Urgency: **Medium**
  - Reporting Service: **emaratechIT.IMD.Unix**
- Ensures:
  - Summary = Description
  - Ticket number and link are printed after creation

---

## 🚀 Usage

Once installed, raising a Service Request is as simple as:

```bash
raise-sr "Problem/service request statement"

jira-sr/
├── create_sdimd_sr.yml        # Ansible playbook
├── raise-sr                   # User-facing command
├── README.md
├── .gitignore
└── group_vars/
    └── all/
        └── jira.yml           # (encrypted, NOT in Git)

