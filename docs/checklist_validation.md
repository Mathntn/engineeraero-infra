# Checklist de validation finale — EngineerAero

points à valider avant réception de l'infrastructure.

## Stockage & Réseau

- [ ] Volume RAID 6 actif — aucune alarme disque dans DSM
- [ ] Cache NVMe opérationnel — débit mesuré > 1 Go/s
- [ ] Liaisons 10 GbE opérationnelles — testées depuis 3 postes pilotes
- [ ] Virtual Chassis Alcatel-Lucent actif — test de déconnexion d'un switch

## Virtualisation

- [ ] Cluster Proxmox HA constitué — les 2 nœuds visibles dans Datacenter
- [ ] Basculement HA testé — VM migrée automatiquement sur panne simulée du nœud 1
- [ ] Fencing IPMI configuré et testé

## Sécurité

- [ ] Cluster Stormshield Actif/Passif — basculement testé
- [ ] Règles de filtrage validées — accès AD, SMTP, HTTPS, VPN
- [ ] Module IPS/IDS actif

## Active Directory

- [ ] 20 comptes utilisateurs créés et testés (auth + accès NAS)
- [ ] GPO appliquées — vérifiées sur 3 postes pilotes

## Sauvegarde

- [ ] Snapshots NAS toutes les 4h — 3 cycles consécutifs sans erreur
- [ ] Backup OVH S3 — 3 sauvegardes vérifiées avec intégrité SHA-256
- [ ] **Restauration testée depuis OVH S3**
- [ ] Object Lock WORM actif — test de suppression rejeté par OVH

## Services

- [ ] MFA activé sur 100 % des comptes Exchange
- [ ] Site web HTTPS actif — testé depuis réseau externe (4G)
- [ ] GLPI opérationnel — inventaire automatisé + tickets fonctionnels

---

*La validation de la restauration (point sauvegarde) est obligatoire avant la réception. Un backup non testé n'offre aucune garantie.*
