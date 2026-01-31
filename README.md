
---

````md
# Ansible Lab (Beginner Level)

This repository is created to help beginners learn **Ansible basics** using **Ansible Roles** on  
**RedHat / Fedora based systems**.

---

## Supported Operating Systems

### Controller Machine
- RedHat
- Fedora

### Managed / Remote Nodes
- RedHat
- Fedora
- Debian
- Ubuntu
- Kali Linux

---

## Requirements

- Root user access
- Internet connection
- SSH access to remote servers
- At least one remote server

---

## Step 1: Switch to Root User

Login as root user:

```bash
su -
````

---

## Step 2: Install Ansible

First try installing Ansible directly:

```bash
dnf install ansible -y
```

If the above command **does not work**, install EPEL repository first:

```bash
dnf install epel-release -y
dnf install ansible -y
```

---

## Step 3: Setup Passwordless SSH Connection

Ansible uses SSH to connect to remote servers.

### Generate SSH Key

```bash
ssh-keygen
```

Press **Enter** three times (do not set password).

### Copy SSH Key to Remote Server

```bash
ssh-copy-id root@<remote_server_ip>
```

Example:

```bash
ssh-copy-id root@192.168.1.10
```

Repeat this step for **all remote servers**.

---

## Step 4: Go to Ansible Directory

```bash
cd /etc/ansible/
```

---

## Step 5: Add Remote Server IPs to Hosts File

Edit the Ansible hosts file:

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

## Step 6: Test Ansible Connectivity

Run the ping module to test connection:

```bash
ansible all -m ping
```

Expected output:

```text
SUCCESS => pong
```

---

## Step 7: Clone the Ansible Lab Repository

```bash
git clone https://github.com/MrTarit0x/Ansible_Lab.git
```

---

## Step 8: Move Roles to Ansible Roles Directory

Move the role directories to `/etc/ansible/roles/`:

```bash
mv fwd_service/ httpd_setup/ /etc/ansible/roles/
```

---

## Step 9: Go to Playbooks Directory

```bash
cd /etc/ansible/playbooks/
```

---

## Step 10: Run the Ansible Playbook

```bash
ansible-playbook roles_demo.yml
```

This playbook will execute the roles and configure services on remote servers.

---

## Step 11: Verify the Setup

1. Open a web browser
2. Type your **remote server IP address**
3. Press **Enter**

If everything is correct, the web page will open successfully.

---

## Summary

✔ Installed Ansible
✔ Configured passwordless SSH
✔ Added inventory hosts
✔ Used Ansible roles
✔ Deployed services using playbook

---

## Author

**MrTarit0x**

---

## Happy Learning 🎉

Ansible makes automation easy 🚀

```

---

