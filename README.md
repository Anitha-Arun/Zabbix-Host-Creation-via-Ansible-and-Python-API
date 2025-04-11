# Zabbix-Host-Creation-via-Ansible-and-Python-API


---

# 📘 Zabbix Host Creation via Ansible and Python API

This Ansible playbook connects to the Zabbix API and creates a new host using a Python one-liner script. It installs the required `zabbix-api` Python library and communicates with the Zabbix server to register a host with specified parameters.

---

## 🚀 Features

- Installs the `zabbix-api` Python module
- Authenticates with the Zabbix server
- Creates a new host with defined IP, port, and group
- Outputs the response from the Zabbix API

---

## 🛠️ Requirements

- Python 3
- Ansible
- Zabbix server with API access enabled
- Valid Zabbix Admin credentials

---

## 📄 Playbook Overview

```yaml
- Installs zabbix-api Python library
- Runs a Python one-liner script to:
  - Connect to Zabbix API
  - Authenticate
  - Create a host
- Displays the API response
```

---

## ⚙️ Configuration

Update the following values in the playbook:
- `http://zabbix-url/zabbix` → Your Zabbix server URL
- `'Admin'` and `'ur password'` → Zabbix credentials
- `'192.168.1.1'` → IP of the host to be created
- `'groupid': '2'` → ID of the host group (check in Zabbix UI)

---

## ▶️ Usage

```bash
ansible-playbook create_zabbix_host.yml
```

---

## ✅ Output Example

```json
ok: [localhost] => {
    "zabbix_result.stdout": "{'hostids': ['10489']}"
}
```

---

## 🔐 Security Note

Do not hardcode credentials in production environments. Use **Ansible Vault** or environment variables for secure handling of secrets.

---

## 📎 License

This project is open-source and available under the [MIT License](LICENSE).

Any doubts ping me in anithadamarla0313@gmail.com
