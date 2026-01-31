

````md
# 🚀 Ansible Lab — Role-Based Automation

A simple and structured **Ansible lab project** designed to help understand  
**Ansible installation, inventory management, SSH configuration, and role execution**  
on Linux systems.

---

## 📌 Project Overview

This lab demonstrates how to:

- Install and configure Ansible
- Setup passwordless SSH authentication
- Manage multiple servers using Ansible inventory
- Use **Ansible Roles** for service configuration
- Deploy services using a playbook

---

## 🖥️ Supported Platforms

### Ansible Controller Node
- RedHat
- Fedora

### Managed (Remote) Nodes
- RedHat
- Fedora
- Debian
- Ubuntu
- Kali Linux

---

## 📦 Prerequisites

- Root user access
- At least one remote Linux server
- Internet connectivity
- SSH access enabled on all servers


````


---

### ⚙️ Step-by-Step Setup Guide ⚙️


---

### 🔹 Step 1: Switch to Root User

Switch to the root user of your main system:

```bash
su -
```



---

### 🔹 Step 2: Install Ansible

Try installing Ansible directly:

```bash
dnf install ansible -y
```

If Ansible is not available, enable EPEL repository first:

```bash
dnf install epel-release -y
dnf install ansible -y
```

---

### 🔹 Step 3: Configure Passwordless SSH

Ansible communicates with remote servers via SSH.

#### Generate SSH Key

```bash
ssh-keygen
```

Press **Enter** three times (default options).

#### Copy SSH Key to Remote Server

```bash
ssh-copy-id root@<remote_server_ip>
```

Example:

```bash
ssh-copy-id root@192.168.1.10
```

Repeat this step for **each remote server**.

---

### 🔹 Step 4: Navigate to Ansible Configuration Directory

```bash
cd /etc/ansible/
```

---

### 🔹 Step 5: Configure Inventory (Hosts File)

Edit the inventory file:

```bash
vi hosts
```

Add your remote server IP addresses:

```ini
[servers]
192.168.1.10
192.168.1.11
```

Save and exit the file.

---

### 🔹 Step 6: Verify Ansible Connectivity

Test the connection with all remote servers:

```bash
ansible all -m ping
```

Expected output:

```text
SUCCESS => pong
```

---

### 🔹 Step 7: Clone the Project Repository

```bash
git clone https://github.com/MrTarit0x/Ansible_Lab.git
```

---

### 🔹 Step 8: Move Role Directories

Move the role folders to the Ansible roles directory:

```bash
mv fwd_service/ httpd_setup/ /etc/ansible/roles/
```

---

### 🔹 Step 9: Navigate to Playbooks Directory

```bash
cd /etc/ansible/playbooks/
```

---

### 🔹 Step 10: Execute the Ansible Playbook

```bash
ansible-playbook roles_demo.yml
```

This playbook applies the defined roles to all managed nodes.

---

### 🔹 Step 11: Validate Deployment

1. Open a web browser
2. Enter the **remote server IP address**
3. Press **Enter**

If the setup is successful, the service page will load correctly.

---

## 📂 Project Structure

```text
Ansible_Lab/
├── fwd_service/
├── httpd_setup/
├── playbooks/
│   └── roles_demo.yml
└── README.md
```

---

## ✅ What You Learned

* Installing and configuring Ansible
* Creating passwordless SSH connections
* Managing servers using inventory
* Using role-based automation
* Running Ansible playbooks in real scenarios

---

## 👤 Author

**MrTarit0x**

---

## 🌟 Conclusion

This project provides a solid foundation for learning **Ansible automation** using roles.
Feel free to modify, extend, and experiment with the playbooks and roles.

Happy Automating! 🚀✨


