# ansible-lab

My first Ansible playbooks, tested locally on VirtualBox
(1 control VM + 2 Ubuntu Server targets).

- `inventory.ini`: the 2 targets, group `lab`
- `01_utilisateur.yml`: creates the adminlab user and deploys its SSH key on the target servers
- `02_update.yml`: package updates on the target servers (`upgrade: safe`, to avoid breaking dependencies)

Requirement: `ansible-galaxy collection install ansible.posix`

Usage: `ansible-playbook -i inventory.ini 01_utilisateur.yml -K`

Tested with --syntax-check, then run, then re-run to check idempotence (changed=0).
