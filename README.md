# Harden Validator Node: Firewall and SSH Configuration

This repository provides a lightweight security hardening playbook for blockchain validator nodes, focusing on **firewall rules** and **SSH access controls** using Ansible.

---

## 🔐 Attack Mitigated

**Node Infrastructure Exposure** — Nodes exposed to the internet with open ports and weak SSH configurations are vulnerable to:

- Brute-force attacks  
- Remote code execution  
- Unauthorized configuration changes  
- DoS via unfiltered public access

This mitigation helps prevent these risks by tightly controlling network access.

---

## ⚙️ What It Does

This Ansible playbook:

- Installs and configures UFW (Uncomplicated Firewall)  
- Denies all incoming traffic by default  
- Allows Ethereum P2P traffic on TCP port 30303  
- Allows SSH only from whitelisted IP addresses  
- Disables password-based SSH authentication  
- Disables root login over SSH  

---

## 📁 Files Included

- `harden_validator_node.yml`: The Ansible playbook  

## ✅ Prerequisites

Before using this playbook, make sure the following requirements are met:

- **Target System**:  
  - Ubuntu 22.04 LTS (or compatible Debian-based distro)
  - Validator node exposed to Ethereum P2P traffic (port 30303)

- **Control Machine** (where you run Ansible):  
  - Python 3.x  
  - Ansible 2.10+ installed  
  - SSH key access to the validator node

- **Other**:  
  - UFW (Uncomplicated Firewall) will be configured; ensure it's compatible with your setup  
  - You have permission to modify `/etc/ssh/sshd_config` and restart SSH on the validator node  
  - You have whitelisted the IP(s) that will manage the node (to avoid being locked out)

> ⚠️ **Important**: Always test this playbook on a staging or backup node before applying to production validators.
