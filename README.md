# Ansible Playbook: Install Docker and Zabbix

This Ansible playbook automates the installation of **Docker** and **Zabbix Server** using **Docker Compose**.

## 🚀 Features
- Installs **Docker** and **Docker Compose**
- Deploys **Zabbix Server** using **Docker Compose**
- Sets up **MySQL**, **Zabbix Server**, and **Zabbix Web Interface**

## 📌 Prerequisites
- Ansible installed on your control node
- A target machine with Ubuntu/Debian-based OS
- SSH access to the target machine

## 📂 Project Structure
```
ansible-docker-zabbix/
├── inventory.yml           # Inventory file
├── playbook.yml            # Main Ansible playbook
├── roles/
│   ├── docker-install/     # Role for installing Docker
│   │   ├── tasks/
│   │   │   └── main.yml    # Docker installation tasks
│   ├── zabbix-server/      # Role for setting up Zabbix
│   │   ├── tasks/
│   │   │   └── main.yml    # Zabbix setup tasks
└── README.md               # Project documentation
```

## 🔧 Usage
### 1️⃣ Clone the Repository
```bash
git clone https://github.com/arynishere/zabbix-on-docker.git
cd zabbix-on-docker
```

### 2️⃣ Edit the Inventory File
Modify `inventory.yml` and set the target server details:
```yaml
all:
  hosts:
    target-server:
      ansible_host: 192.168.1.1
      ansible_user: ubuntu
      ansible_ssh_private_key_file: ~/.ssh/id_rsa
```

### 3️⃣ Run the Playbook
```bash
ansible-playbook -i inventory.yml playbook.yml
```

## 📌 Zabbix Web Access
Once the setup is complete, you can access Zabbix at:
```
http://<server-ip>:8080
```
**Default Credentials:**
- **Username:** `Admin`
- **Password:** `zabbix`

## 📜 License
This project is open-source under the MIT License.

