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
