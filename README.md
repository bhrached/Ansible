# Installation Jenkins, GitLab et Wordpress à travers Ansible

Ce guide vous permet à travers les étapes suivants d'installer et configurer les environnements Jenkins, GitLab et Wordpress en utilisant Vagrant et Ansible.

## Prérequis

Avant de commencer, assurez-vous que vous avez installé les outils suivants sur votre machine hôte :

- **[Vagrant](https://www.vagrantup.com/downloads)** : Outil pour la gestion des machines virtuelles.
- **[VirtualBox](https://www.virtualbox.org/wiki/Downloads)** : Fournisseur de machines virtuelles pour Vagrant.
- **[Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)** : Outil d'automatisation pour la gestion des configurations.

Si l'un de ces outils n'est pas installé, vous devez l'installer avant de poursuivre.

## Étapes d'installation

### 1. Cloner le projet

Commencez par cloner ce dépôt sur votre machine hôte :

```bash
git clone https://github.com/bhrached/Ansible.git
cd Ansible

