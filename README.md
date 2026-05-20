 Laboratoire SecOps : Pentest & Supervision en Temps Réel

Ce dépôt contient l'infrastructure complète d'un laboratoire de cybersécurité combinant l'analyse offensive (**Red Team**) et la surveillance industrielle (**Blue Team**). L'objectif est d'exploiter une vulnérabilité critique d'injection de commande (OWASP Top 10) et d'analyser son impact sur les ressources matérielles et réseau en temps réel via une pile de supervision moderne.

---

 Architecture du Laboratoire

L'environnement est segmenté de manière étanche pour garantir la sécurité des manipulations :
* **Réseau :** Commutateur virtuel isolé `Host-Only` sous VMware Workstation Player (pas d'accès Internet pour la cible afin d'éviter toute fuite de flux malveillants).
* **Machine Attaquante :** Kali Linux (équipée de Nmap, Netcat et des outils d'audit).
* **Machine Cible :** Ubuntu Server orchestrant l'infrastructure conteneurisée via Docker Compose.

 Schéma Fonctionnel de l'Infrastructure
![Architecture du Lab SecOps](.github/screenshots/schema_architecture.png)

---

 Déploiement Rapide (Infrastructure as Code)

Pour instancier l'intégralité du laboratoire sur la machine cible Ubuntu, clonez ce dépôt et exécutez la commande suivante à la racine du projet :

```bash
sudo docker-compose up -d
