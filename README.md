📘 Zabbix Automation via Ansible
This repository contains two Ansible playbooks to automate interactions with a Zabbix server:

Test Zabbix API Connectivity

Create a Zabbix Host via Python Zabbix API

📂 Playbooks Overview
🔹 test_zabbix_connection.yml
This playbook checks:

If the Zabbix web interface is reachable

If the API is accessible and authentication is successful

Use Case: Quickly verify if the Zabbix server is online and your API credentials work.

🔹 create_zabbix_host.yml
This playbook:

Installs the zabbix-api Python package (if not already installed)

Authenticates with the Zabbix API

Creates a new host with predefined settings (host name, IP, group, etc.)

Use Case: Automate the creation of new Zabbix hosts from Ansible.

⚙️ Requirements
Python 3

Ansible

Zabbix server with API access enabled

Internet access to install Python packages

Valid Zabbix credentials

🔐 Variables
Set these in the playbooks:

yaml
Copy
Edit
zabbix_url: "http://your-zabbix-url/zabbix"
zabbix_user: "Admin"
zabbix_password: "--your-password--"
▶️ Usage
1. Test Zabbix API Connection
----
Copy
Edit
ansible-playbook test_zabbix_connection.yml
Sample Output:

----
Copy
Edit
Zabbix web interface is reachable
Successfully connected to Zabbix API
2. Create Host in Zabbix
----
Copy
Edit
ansible-playbook create_zabbix_host.yml
Sample Output:

json
Copy
Edit
ok: [localhost] => {
    "zabbix_result.stdout": "{'hostids': ['10489']}"
}
📎 Notes
groupid: '2' in host creation typically maps to Linux servers in Zabbix. Adjust as needed.

Avoid hardcoding credentials for production. Use Ansible Vault or environment variables.

The Python-based playbook uses a command module with inline Python. For complex logic, consider external .py scripts.

🧾 License
This project is licensed under the MIT License.


Any doubts ping me in anithadamarla0313@gmail.com
