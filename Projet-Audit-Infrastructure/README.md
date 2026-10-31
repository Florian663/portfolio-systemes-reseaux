# Projet – Audit et sécurisation d'une infrastructure informatique

## 1. Présentation du projet

Ce projet a été réalisé dans le cadre de ma formation **Administrateur d'Infrastructure Sécurisée (AIS – RNCP37680BC03)**.

L'objectif était de concevoir, déployer et sécuriser une infrastructure informatique virtualisée, tout en intégrant des solutions de supervision et de détection des événements de sécurité.

Le projet repose sur un environnement virtualisé avec Proxmox et plusieurs machines dédiées à l'administration, à la sécurité et à la supervision.

## 2. Architecture technique

### Technologies utilisées

| Domaine                 | Solutions                    |
| ----------------------- | ---------------------------- |
| Virtualisation          | Proxmox                      |
| Système serveur         | Windows Server 2022          |
| Annuaire                | Active Directory, AD DS, GPO |
| Pare-feu                | OPNsense                     |
| Supervision de sécurité | Wazuh                        |
| Supervision système     | Centreon                     |
| Systèmes Linux          | Ubuntu, AlmaLinux            |
| Réseau                  | TCP/IP, VLAN, DHCP, filtrage |

### Segmentation réseau

L'infrastructure est organisée en plusieurs segments réseau afin de séparer les usages et de limiter les communications entre les différentes zones.

| VLAN / Zone | Réseau          | Passerelle   | Usage |
|-------------|-----------------|--------------|-------|
| VLAN 10     | 192.168.10.0/24 | 192.168.10.1 | Administration |
| VLAN 20     | 192.168.20.0/24 | 192.168.20.1 | Support |
| VLAN 30     | 192.168.30.0/24 | 192.168.30.1 | DMZ – Wazuh / Centreon |
| VLAN 40     | 192.168.40.0/24 | 192.168.40.1 | Active Directory principal |
| VLAN 50     | 192.168.50.0/24 | 192.168.50.1 | Active Directory secondaire (CDS) |

Le routage et le filtrage des communications sont assurés par OPNsense.

## 3. Services et composants

### Proxmox

- Hébergement et gestion des machines virtuelles.
- Organisation de l'environnement virtualisé.
- Déploiement des serveurs et services.

### Windows Server – Active Directory

- Gestion centralisée des utilisateurs et des groupes.
- Organisation des comptes et des droits.
- Mise en place de stratégies de groupe (GPO).

### OPNsense

- Gestion des flux réseau.
- Filtrage des communications entre les segments.
- Sécurisation des accès à l'infrastructure.

### Wazuh

- Collecte et analyse des événements de sécurité.
- Surveillance des activités des systèmes.
- Détection des événements suspects.

### Centreon

- Supervision de la disponibilité des équipements et services.
- Surveillance de l'état de l'infrastructure.
- Identification des anomalies et des interruptions de service.

## 4. Objectifs de sécurité

Les principaux objectifs de sécurité du projet sont :

- Segmenter le réseau afin de limiter les communications inutiles.
- Contrôler les flux à l'aide du pare-feu.
- Centraliser l'administration des utilisateurs et des accès.
- Surveiller les événements de sécurité.
- Superviser la disponibilité des services.
- Améliorer la détection des incidents et la continuité de service.

## 5. Compétences mobilisées

- Administration Windows Server et Linux.
- Gestion d'Active Directory et des GPO.
- Virtualisation avec Proxmox.
- Configuration et filtrage réseau avec OPNsense.
- Segmentation réseau et VLAN.
- Déploiement de solutions de supervision.
- Analyse des événements de sécurité.
- Documentation technique d'une infrastructure.

## 6. Conclusion

Ce projet m'a permis de mettre en pratique les connaissances acquises durant ma formation AIS et de travailler sur différents composants d'une infrastructure informatique.

Il m'a notamment permis d'approfondir mes compétences en administration systèmes, réseaux, virtualisation, supervision et cybersécurité.

