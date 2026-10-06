# Installation

## Environnement
- Hyperviseur : VMware Workstation (Windows 11 hôte, 32 Go RAM)
- Réseau lab : VMnet1 host-only, 192.168.100.0/24, DHCP désactivé
- Sortie Internet : VMnet8 NAT (uniquement Ubuntu Server + Ubuntu DVWA)

## Machines

| Machine | Rôle | IP (VMnet1) | Cartes réseau |
|---|---|---|---|
| Ubuntu Server 24.04 | Wazuh manager + indexer + dashboard | 192.168.100.40 | VMnet1 + NAT |
| Ubuntu 24.04 | DVWA (cible web) + agent Wazuh | 192.168.100.30 | VMnet1 + NAT |
| Windows 10 | Victime + agent Wazuh | 192.168.100.20 | VMnet1 uniquement |
| Kali Linux | Attaquant | 192.168.100.10 | VMnet1 uniquement |

## Wazuh 4.14.0 (all-in-one)
- Script : `wazuh-install.sh -a` (packages.wazuh.com)
- VM : 16 Go RAM, 4 vCPU, 4 Go swap ajouté
- Échec initial à 7,5 Go RAM (OOM pendant l'optimisation des
  plugins du dashboard) → résolu en montant la VM à 16 Go
- (identifiants dashboard conservés hors Git, localement)

## Agents
- Ubuntu DVWA : dépôt apt Wazuh, `WAZUH_MANAGER="192.168.100.40" apt-get install wazuh-agent=4.14.0-1`
- Windows 10 : MSI `wazuh-agent-4.14.0-1.msi /q WAZUH_MANAGER="192.168.100.40"`, service `WazuhSvc`