# LFCS Ansible

TLDR;

This is the repository to store my ansible playbook for LCFS learning.
I use these playbook to configure my local virtual machines running linux.

## Ansible Concepts

### Playbook
A list of plays that define the order in which Ansible performs operations, from top to bottom, to achieve an overall goal.

### Play
An ordered list of tasks that maps to managed nodes in an inventory.

### Task
A reference to a single module that defines the operations that Ansible performs.

### Module
A unit of code or binary that Ansible runs on managed nodes. Ansible modules are grouped in collections with a Fully Qualified Collection Name (FQCN) for each module.

source: https://docs.ansible.com/ansible/latest/getting_started/get_started_playbook.html