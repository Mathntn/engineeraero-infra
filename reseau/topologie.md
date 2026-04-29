# Topologie réseau — EngineerAero

## Adressage IP

| VLAN | Nom | Réseau | Passerelle | Usages |
|---|---|---|---|---|
| VLAN 10 | Ingénierie | 10.10.10.0/24 | 10.10.10.1 | Postes ingénieurs, accès NAS |
| VLAN 20 | Administration | 10.10.20.0/24 | 10.10.20.1 | Direction, RH, comptabilité |
| VLAN 30 | Invités | 10.10.30.0/24 | 10.10.30.1 | Wifi visiteurs — accès internet uniquement |
| VLAN 99 | Management | 10.10.99.0/24 | 10.10.99.1 | IPMI serveurs, switchs, NAS (admin) |

## Équipements — IPs fixes

| Équipement | VLAN | Adresse IP |
|---|---|---|
| Stormshield SN220 (actif) | Management | 10.10.99.1 |
| Stormshield SN220 (passif) | Management | 10.10.99.2 |
| Switch OS6560 (maître) | Management | 10.10.99.10 |
| Switch OS6560 (secondaire) | Management | 10.10.99.11 |
| Proxmox node1 | Management | 10.10.99.20 |
| Proxmox node2 | Management | 10.10.99.21 |
| NAS Synology DS3622xs+ | Management | 10.10.99.30 |
| VM Active Directory / DNS | Ingénierie | 10.10.10.10 |
| VM Serveur de fichiers | Ingénierie | 10.10.10.11 |
| VM GLPI | Administration | 10.10.20.10 |


## Liaisons physiques 10 GbE

```
Stormshield (SFP+) ──► Switch OS6560 (SFP+ uplink)
Switch OS6560      ──► Proxmox node1 (SFP+ 10 GbE)
Switch OS6560      ──► Proxmox node2 (SFP+ 10 GbE)
Switch OS6560      ──► NAS DS3622xs+ (2x 10 GbE LACP)
```

---

*Stargate Système — Projet TSSR — Avril 2025*
