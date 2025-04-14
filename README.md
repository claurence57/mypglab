# mypglab
Ansible playbook and / or script use for my PostgreSQL lab

# Gestion d'Etcd avec Ansible

Ce dépôt contient des playbooks Ansible pour gérer l'installation et la désinstallation de l'environnement Etcd. Deux playbooks principaux sont fournis : `install_etcd.yaml` et `clean_etcd.yaml`.

## Table des Matières
- [Pré-requis](#pré-requis)
- [playbook: clean_etcd.yaml](#playbook-clean_etcdyaml)
- [playbook: install_etcd.yaml](#playbook-install_etcdyaml)

## Pré-requis
Avant d'exécuter ces playbooks, assurez-vous d'avoir :
- Ansible installé sur votre machine.
- Un inventaire d'hôtes configuré avec les nœuds Etcd.
- Les droits d'accès nécessaires pour exécuter des tâches avec élévation de privilèges (sudo).

## playbook: clean_etcd.yaml

Le playbook `clean_etcd.yaml` est conçu pour nettoyer l'environnement Etcd en supprimant l'utilisateur et le groupe associés. 

### Rôles et Tâches
- **Supprimer l'utilisateur Etcd** : Utilise le module `user` pour supprimer l'utilisateur spécifié par la variable `{{ etcd_user }}`.
- **Supprimer le groupe Etcd** : Utilise le module `group` pour supprimer le groupe spécifié par la variable `{{ etcd_group }}`.

### Utilisation
Pour exécuter ce playbook, utilisez la commande suivante :
```bash
ansible-playbook clean_etcd.yaml -i votre_inventaire

