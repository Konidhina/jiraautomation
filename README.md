# Jira Service Request Automation – Jira Data Center


Command line automation tool to create Jira Service Desk **Service Requests (SR)**
in project **SDIMD** without opening the Jira UI.

The tool uses:

- Jira Data Center REST API
- Jira Personal Access Token (PAT)
- Ansible automation
- Simple Linux wrapper command

---

# Features


- Creates Jira Service Request automatically
- Supports multiple subsidiaries
- Automatically fills mandatory Jira fields
- Uses secure PAT authentication
- Prints Jira ticket number and URL after creation

---

# Repository Structure


```text
jira-sr/
├── create_sdimd_sr.yml              # Main Jira SR creation playbook

├── raise-sr                         # User command wrapper

├── find_subsidiary_options.yml      # Find Jira subsidiary IDs

├── find_sr_type_options.yml         # Find Jira SR Type IDs

├── README.md
├── .gitignore
└── group_vars/
    └── all/
        └── jira.yml                 # Vault file (Not pushed to Git)

Create SR for emaratech G
raise-sr "Deploy Linux VM using automation" G
| Jira Field        | Value                                  |
| ----------------- | -------------------------------------- |
| Project           | SDIMD                                  |
| Issue Type        | Service Request                        |
| Environment       | Production                             |
| Impact            | Single User                            |
| Urgency           | Medium                                 |
| Reporting Service | SD-215                                 |
| SR Type           | Environment Provisioning & Maintenance |

Supported Subsidiary Options

| Command Value | Company             |
| ------------- | ------------------- |
| G             | emaratech G         |
| emaratech     | emaratech           |
| Solutions     | emaratech Solutions |
| Group         | emaratech Group     |
| Noqodi        | noqodi              |
| cybranytech   | Cybranytech         |
| eres          | ERES                |
| egypt         | Egypt               |
| zajel         | Zajel               |
| others        | Others              |


