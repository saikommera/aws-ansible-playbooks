# 🤖 AWS Ansible Playbooks

[![Ansible](https://img.shields.io/badge/Ansible-2.15+-EE0000?style=flat-square&logo=ansible)](https://ansible.com)
[![AWS](https://img.shields.io/badge/AWS-Automation-FF9900?style=flat-square&logo=amazonaws)](https://aws.amazon.com)
[![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)](LICENSE)

Ansible playbooks for automated AWS infrastructure configuration, EC2 provisioning, application deployments, and operational runbooks. Used to eliminate configuration drift and reduce manual toil by 30%.

## 📁 Structure

```
├── playbooks/
│   ├── provision-ec2.yml        # EC2 instance provisioning
│   ├── configure-baseline.yml   # Security baseline hardening
│   ├── deploy-app.yml           # Zero-downtime app deployment
│   ├── rotate-secrets.yml       # Automated secret rotation
│   └── incident-remediation.yml # Auto-remediation runbooks
├── roles/
│   ├── common/                  # Base OS hardening
│   ├── docker/                  # Docker installation
│   ├── node-exporter/           # Prometheus exporter
│   └── cloudwatch-agent/        # CloudWatch metrics agent
├── inventory/
│   ├── dev.aws_ec2.yml          # Dynamic EC2 inventory (dev)
│   └── prod.aws_ec2.yml         # Dynamic EC2 inventory (prod)
└── group_vars/
    ├── all.yml
    ├── dev.yml
    └── prod.yml
```

## 🚀 Quick Start

```bash
# Install dependencies
pip install ansible boto3 botocore
ansible-galaxy collection install amazon.aws community.aws

# Run baseline hardening on all prod servers
ansible-playbook playbooks/configure-baseline.yml \
  -i inventory/prod.aws_ec2.yml \
  --extra-vars "env=prod"

# Zero-downtime app deployment
ansible-playbook playbooks/deploy-app.yml \
  -i inventory/prod.aws_ec2.yml \
  --extra-vars "app_version=1.2.3 env=prod"
```

## 🔐 Security Baseline

The `configure-baseline.yml` playbook enforces:
- CIS Benchmark Level 1 hardening
- SSH key-only authentication (password auth disabled)
- Automatic security updates enabled
- auditd logging configured
- Unused services disabled
- CloudWatch agent installed for centralized logging

## 🧑‍💻 Author

**Sai Babji Kommera** — Senior DevOps / SRE Engineer
[LinkedIn](https://www.linkedin.com/in/sai-babji-kommera-a3b953396/) · saibabji1@gmail.com
