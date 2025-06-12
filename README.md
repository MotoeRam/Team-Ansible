
# Ansible Installation and Setup Guide

## Overview

Ansible is an open-source automation tool for configuration management, application deployment, and provisioning. This guide helps you install and set up Ansible on a Linux system.

---

## Prerequisites

* A Unix-like OS (Ubuntu, RedHat, CentOS, Oracle Linux)
* Python 3 installed
* SSH access to managed nodes

---

## Installation

### Ubuntu / Debian

```bash
sudo apt update
sudo apt install -y software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install -y ansible
```

### RedHat / CentOS / Oracle Linux

```bash
sudo dnf install -y epel-release
sudo dnf install -y ansible
```

### Using pip (any OS with Python)

```bash
python3 -m pip install --user ansible
```

> Ensure `~/.local/bin` is in your `$PATH`

---

## Verify Installation

```bash
ansible --version
```

---

## Basic Setup

1. Create a project directory:

```bash
mkdir -p ~/ansible-project
cd ~/ansible-project
```

2. Create an inventory file:

```ini
# inventory.ini
[webservers]
192.168.1.10
192.168.1.11

[dbservers]
db1.example.com
```

3. Create a simple playbook:

```yaml
# ping.yml
- name: Test connectivity
  hosts: all
  tasks:
    - name: Ping all hosts
      ansible.builtin.ping:
```

4. Run the playbook:

```bash
ansible-playbook -i inventory.ini ping.yml
```

---

## SSH Configuration

Generate SSH keys and copy to remote hosts:

```bash
ssh-keygen -t rsa
ssh-copy-id user@remote-host
```

---

## Testing

Run ping test to verify Ansible works:

```bash
ansible all -i inventory.ini -m ping
```

---

## Documentation

* Official Docs: [https://docs.ansible.com](https://docs.ansible.com)
* Galaxy: [https://galaxy.ansible.com](https://galaxy.ansible.com)

---

## Uninstall Ansible

**Ubuntu/Debian:**

```bash
sudo apt remove ansible
```

**RHEL/CentOS:**

```bash
sudo dnf remove ansible
```

**Pip uninstall:**

```bash
pip uninstall ansible
```

---

Happy Automating with Ansible! 🚀
