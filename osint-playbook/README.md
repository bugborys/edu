# OSINT Tools Ansible Playbook

This playbook automates the installation of popular OSINT tools used for open-source intelligence gathering.

## 🔧 Tools Installed:

- **Amass** — Subdomain enumeration (installed via `snap`)
- **bbot** - multi scanner (installed via `pipx`)
- **theHarvester** — Email, subdomain, and domain search
- **Subfinder** — Passive subdomain enumeration
- **Shodan CLI** — Interaction with the Shodan API
- **GitDorker** — Secret search in GitHub
- **TruffleHog** — Alternative to GitDorker for secret discovery

> GitDorker and TruffleHog are separate roles. You can use either or install both.

## 📂 Directory Structure

```bash
osint-playbook/
├── osint.yml
├── README.md
├── requirements.yml
└── roles/
    ├── amass/
    ├── bbot/
    ├── theharvester/
    ├── subfinder/
    ├── shodan/
    ├── gitdorker/
    └── trufflehog/
```

## 🚀 How to Use

### 1. Install all tools:

```bash
ansible-playbook osint.yml
```

### 2. Install a specific tool:

```bash
ansible-playbook osint.yml --tags amass
ansible-playbook osint.yml --tags theharvester
ansible-playbook osint.yml --tags trufflehog
```

> You can also combine tags:

```bash
ansible-playbook osint.yml --tags "amass,subfinder"
```

## 🖥 Remote VPS Support

If you want to install tools on a remote VPS, change `hosts: localhost` to `hosts: vps` in `osint.yml`, and configure your inventory file like this:

```ini
[vps]
your.vps.ip.address ansible_user=your_user
```

## 📦 Requirements

- Ansible ≥ 2.9
- Sudo privileges
- Internet connection

