# Sources de logs

| # | Source | Hôte | Type de logs | Canal Wazuh | Statut |
|---|---|---|---|---|---|
| 1 | Wazuh agent | Ubuntu DVWA (192.168.100.30) | syslog, auth.log, FIM (syscheck), SCA, syscollector | — | ✅ Jour 4 |
| 2 | Wazuh agent | Windows 10 (192.168.100.20) | EventChannel (Sécurité, Système, Application), FIM, SCA | — | ✅ Jour 4 |
| 3 | Sysmon | Windows 10 | EventChannel Microsoft-Windows-Sysmon/Operational | — | ⏳ Jour 5 |
| 4 | Suricata eve.json | Ubuntu DVWA | IDS réseau | localfile | ⏳ Jour 6 |
| 5 | auditd | Ubuntu Server | appels système | — | ⏳ Semaine 2 |

Légende : ✅ intégré / ⏳ planifié