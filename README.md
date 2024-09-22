  Installation Jenkins, GitLab et WordPress à travers Ansible

Installation Jenkins, GitLab et WordPress à travers Ansible
===========================================================

Ce guide vous permet d'installer et de configurer les environnements Jenkins, GitLab et WordPress en utilisant Vagrant et Ansible.

Version 1.0
-----------

Cette version comprend trois playbooks distincts pour l'installation et la configuration des services suivants :

*   **Jenkins** : Un serveur d'intégration continue open-source.
*   **GitLab** : Une plateforme de gestion de code source et de collaboration.
*   **WordPress** : Un système de gestion de contenu pour créer des sites web.

Chaque playbook est conçu pour automatiser l'installation des dépendances nécessaires et la configuration de chaque service, permettant ainsi une mise en place rapide et efficace des environnements de développement.

Prérequis
---------

Avant de commencer, assurez-vous que vous avez installé les outils suivants sur votre machine hôte :

*   [Vagrant](https://www.vagrantup.com/downloads) : Outil pour la gestion des machines virtuelles.
*   [VirtualBox](https://www.virtualbox.org/wiki/Downloads) : Fournisseur de machines virtuelles pour Vagrant.
*   [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) : Outil d'automatisation pour la gestion des configurations.

Si l'un de ces outils n'est pas installé, vous devez l'installer avant de poursuivre.

## Changelog

### Version 1.1
- **Décomposition du Playbook WordPress** : Le playbook WordPress a été réorganisé pour améliorer la structure et la maintenabilité. Il est désormais divisé en quatre rôles distincts :
  - **WordPress** : Rôle principal pour l'installation et la configuration de WordPress.
  - **Apache** : Rôle pour l'installation et la configuration du serveur web Apache.
  - **MariaDB** : Rôle dédié à l'installation et à la configuration de MariaDB.
  - **PHP** : Rôle pour l'installation des modules PHP nécessaires au fonctionnement de WordPress.

Étapes d'installation
---------------------

### 1\. Cloner le projet

Commencez par cloner ce dépôt sur votre machine hôte :

    git clone https://github.com/bhrached/Ansible.git
    cd Ansible

### 2\. Configuration des fichiers Vagrant

Avant d'exécuter les playbooks, assurez-vous que les fichiers Vagrant sont correctement configurés. Vérifiez le fichier `Vagrantfile` pour les spécifications des machines virtuelles pour Jenkins, GitLab et WordPress.

### 3\. Lancer Vagrant

Démarrez les machines virtuelles avec Vagrant :

    vagrant up

### 4\. Exécuter les playbooks Ansible

Une fois les machines virtuelles en cours d'exécution, vous pouvez exécuter les playbooks pour installer et configurer chaque service.

*   Pour Jenkins :

    ansible-playbook -i Inventory/hosts.ini Playbooks/playbook_jenkins.yml

*   Pour GitLab :

    ansible-playbook -i Inventory/hosts.ini Playbooks/playbook_gitlab.yml

*   Pour WordPress :

    ansible-playbook -i Inventory/hosts.ini Playbooks/playbook_wordpress/site.yml

### 5\. Accéder aux services

Après l'exécution des playbooks, vous pourrez accéder aux services via les adresses suivantes :

*   **Jenkins** : [http://localhost:8081](http://localhost:8081)
*   **GitLab** : [http://localhost:8090](http://localhost:8090)
*   **WordPress** : [http://localhost:8082](http://localhost:8082)

### Notes

Assurez-vous que les ports requis sont ouverts et accessibles depuis votre machine hôte.

Consultez la documentation respective de chaque service pour plus de détails sur la configuration et l'utilisation.