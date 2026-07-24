# Project-3-Enterprise-Configuration-Management-using-Ansible.
Project 3 – Enterprise Configuration Management using Ansible.

📖 Project Overview

This project demonstrates how to automate Linux server configuration using Ansible. The implementation starts from installing Ansible and configuring passwordless SSH, then progresses through inventory management, ad-hoc commands, playbooks, variables, templates, handlers, roles, and production-ready project organization.

The project follows enterprise best practices and simulates how DevOps engineers manage infrastructure in production environments.

🎯 Objective
Automate server configuration using Ansible.
Manage multiple Linux servers from a central control node.
Create reusable automation using Playbooks and Roles.
Deploy dynamic web pages using Jinja2 Templates.
Implement production-grade project structure.
Follow Infrastructure as Code (IaC) principles.
🏢 Real-World Scenario

An organisation manages hundreds of Linux servers.

Manual configuration requires:

SSH into each server
Install required packages
Configure services
Deploy configuration files
Restart services

Using Ansible:

One command configures all servers simultaneously.
Infrastructure becomes repeatable.
Human error is reduced.
Deployments become faster and more consistent.
🏗️ Architecture
                 Developer
                     │
                     ▼
              Ansible Master
                     │
          SSH (Port 22)
                     │
        ┌────────────┴────────────┐
        ▼                         ▼
     Web01                     Web02
📁 Production Repository Structure
ansible-project/
│
├── ansible.cfg
├── inventory
├── site.yml
│
├── group_vars/
│   └── webservers.yml
│
├── roles/
│   ├── apache/
│   │
│   ├── tasks/
│   │     └── main.yml
│   │
│   ├── handlers/
│   │     └── main.yml
│   │
│   ├── templates/
│   │     └── index.html.j2
│   │
│   ├── vars/
│   │     └── main.yml
│   │
│   ├── defaults/
│   │     └── main.yml
│   │
│   ├── files/
│   │
│   └── meta/
│
└── users/
🚀 Production Deployment Workflow
    Developer

        │

        ▼

    Git Push

        │

        ▼

Jenkins Pipeline

        │

        ▼

Ansible Playbook

        │

        ▼

 Ansible Master

        │

────────┼───────────────

        ▼

     Web01

        ▼

Deploy Apache

Deploy Website

Restart Service (Handler)

────────┼───────────────

        ▼

     Web02

Deploy Apache

Deploy Website

Restart Service (Handler)
🛠️ Technologies Used
Red Hat Enterprise Linux
AWS EC2
OpenSSH
Python
Ansible Core
YAML
Jinja2
Git
📚 Topics Covered
Phase 1 – Environment Setup
Created Ansible Control Node
Created Managed Nodes
Configured Hostnames
Updated Packages
Installed Required Utilities
Phase 2 – Passwordless SSH
Generated SSH Keys
Configured authorized_keys
SSH Authentication
SSH Troubleshooting
known_hosts
Host Key Verification
Phase 3 – Install Ansible
Installed ansible-core
Verified Python
Verified Installation
Ansible Architecture
Phase 4 – Inventory
Static Inventory
Inventory Groups
Group Variables
Inventory Validation
ansible-inventory
Phase 5 – Ad-hoc Commands

Modules used

ping
command
service
dnf

Commands executed

hostname
uptime
free
df
Install Apache
Start Apache
Enable Apache
Phase 6 – Playbooks

Created first production playbook

Topics

YAML
Tasks
become
Modules
Syntax Check
Idempotency
Phase 7 – Variables

Implemented

vars:

web_package

web_service

web_root

homepage_message

company_name

Learned

Jinja Variables
Variable Reuse
Hardcoded vs Dynamic Values
Phase 8 – Jinja2 Templates

Created

templates/index.html.j2

Used Facts

inventory_hostname
ansible_distribution
ansible_kernel
ansible_architecture
ansible_default_ipv4.address

Generated dynamic HTML page for every server.

Phase 9 – Handlers

Implemented

notify:

Restart Apache

Created

handlers:

Restart Apache

Learned

notify
Handlers
Service Restart
Handler Execution Flow
Multiple Notifications
Idempotent Restarts
Phase 10 – Roles

Converted project into enterprise structure.

Created Role

apache

Moved

Tasks
Variables
Templates
Handlers

Created

site.yml
Phase 11 – Enterprise Repository

Implemented

group_vars
Multiple Roles
users Role
Variable Precedence
Production Folder Structure
Phase 12 – Enterprise Best Practices

Learned

Ansible Vault
Tags
Limit
Check Mode
Diff Mode
Forks
ansible.cfg
Production Deployment
📚 Important Commands
Verify Inventory
ansible-inventory -i inventory --list
Ping Servers
ansible webservers -m ping
Run Playbook
ansible-playbook site.yml
Syntax Check
ansible-playbook --syntax-check site.yml
Dry Run
ansible-playbook site.yml --check
Show Changes
ansible-playbook site.yml --diff
Run Specific Tag
ansible-playbook site.yml --tags deploy
Limit Deployment
ansible-playbook site.yml --limit web01
Increase Debug Logs
ansible-playbook site.yml -vvvv
🎯 Key Concepts Learned
Infrastructure as Code (IaC)
Agentless Architecture
SSH Authentication
Inventory Management
Ad-hoc Commands
Playbooks
Variables
Jinja2 Templates
Ansible Facts
Handlers
Roles
Group Variables
Variable Precedence
Idempotency
YAML
Enterprise Project Structure
Production Deployment
Configuration Management
🔧 Challenges Faced

During the implementation, the following issues were encountered and resolved:

SSH Host Key Verification Failed
Passwordless SSH Configuration
YAML Indentation Errors
Incorrect Handler Placement
Template Module Path Issues
Inventory Configuration Errors
Role Discovery Errors
Variable Resolution Issues

Each issue was analyzed using verbose logging (-vvvv), manual SSH verification, inventory validation, and YAML syntax checks.

🚀 Production Best Practices
Use Roles instead of large playbooks.
Store environment-specific variables in group_vars.
Keep secrets in Ansible Vault.
Use Handlers instead of unconditional service restarts.
Always run --syntax-check before execution.
Test with --check before production deployments.
Use Tags for selective execution.
Use --limit for staged deployments.
Store automation code in Git.
Use ansible.cfg for project-specific settings.
🎤 Interview Topics Covered
What is Ansible?
Why is Ansible Agentless?
Inventory vs Dynamic Inventory
Ad-hoc Commands
Playbooks
Variables
Jinja2 Templates
Handlers
Roles
Group Variables
Variable Precedence
Ansible Facts
Ansible Vault
Tags
Check Mode
Diff Mode
Limit
ansible.cfg
Idempotency
SSH Troubleshooting
YAML Best Practices
🏆 Project Outcome

Successfully built a production-style Ansible automation project capable of:

Managing multiple Linux servers
Deploying Apache automatically
Creating dynamic web pages using templates
Organizing automation into reusable roles
Managing environment-specific configuration
Following enterprise repository standards
Implementing Infrastructure as Code using Ansible
