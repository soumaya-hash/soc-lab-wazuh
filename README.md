# SOC Lab — Wazuh + Suricata + Sysmon + TheHive

## Objectif
Construire un SOC open source complet sur réseau segmenté, avec
détection MITRE ATT&CK et réponse automatisée (SOAR).

## Architecture
![Architecture](screenshots/architecture.png)

## Stack
| Outil | Rôle | Statut |
|---|---|---|
| Wazuh 4.14 | SIEM/XDR (manager, indexer, dashboard) | ✅ |
| Wazuh agents ×2 | Collecte Ubuntu + Windows | ✅ |
| Sysmon | Logs de processus Windows | ⏳ |
| Suricata | IDS réseau | ⏳ |
| TheHive + Cortex | Gestion de cas | ⏳ |
| Shuffle | Orchestration SOAR | ⏳ |

## Résultats
(en cours — voir docs/)

## Démo
(à venir Jour 21)
