# ansible-lab

Voici mes premiers playbooks Ansible, testés en local sur VirtualBox
(1 VM de contrôle + 2 cibles Ubuntu Server).

- `inventory.ini` : les 2 cibles faisant parti du groupe `lab`
- `01_utilisateur.yml` : crée l'utilisateur adminlab et dépose sa clé SSH sur les serveurs cibles
- `02_update.yml` : mise à jour des paquets sur les serveurs cibles en veillant à ne pas faire un upgrade pouvant casser des dépendances 

Prérequis : `ansible-galaxy collection install ansible.posix`

Lancement : `ansible-playbook -i inventory.ini 01_utilisateur.yml -K`

Testé avec --syntax-check, puis exécution, puis relance pour vérifier si (changed=0).

