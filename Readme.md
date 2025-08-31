# Setup Bash-it, Pygments et fonction logview pour logs colorés

Ce projet Ansible installe et configure sur un serveur Debian :

- **bash-it** : un framework pour personnaliser ton shell Bash avec thèmes et alias  
- **python3-pygments** : pour la coloration syntaxique Python (alias `pycolor`)  
- **fonction `logview`** : une fonction Bash qui affiche en temps réel les logs systemd avec couleurs et icônes selon le niveau (info, warning, error, etc.)

---

## Contenu du playbook

- Installation de `python3-pygments`  
- Clonage et installation silencieuse de bash-it pour l'utilisateur root  
- Ajout dans `.bashrc` :  
  - Chargement automatique de bash-it  
  - Alias `pycolor` pour colorer du code Python  
  - Fonction `logview` pour afficher joliment les logs systemd  
  - Aliases exemples (`nanolog`, `sshlog`, `mysqlog`) pour suivre certains services  

---

## Prérequis

- Serveur Debian accessible en SSH  
- Ansible installé sur votre machine locale  
- Clé SSH privée avec permissions correctes (chmod 600) configurée pour accéder au serveur  
- Fichier d’inventaire Ansible (exemple : `inventory/hosts`) configuré avec le serveur cible  

---

## Installation et usage

1. **Lancer le playbook d’installation :**

    ```bash
    ansible-playbook -i inventory/hosts playbook.yml
    ```

2. **Lancer le playbook de test :**

    ```bash
    ansible-playbook -i inventory/hosts check-playbook.yml
    ```
