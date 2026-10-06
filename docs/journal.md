# Journal de bord

## Jour 1 — 02/10/2026
- Réseau VMnet1 host-only créé (192.168.100.0/24), DHCP off
- Repo GitHub initialisé, schéma d'architecture drawio

## Jour 3 — Installation Wazuh 4.14.0
- Échec 1 : URL `packages.wazuh.com/4.x/...` → réponse XML
  "AccessDenied" (le serveur exige un numéro de version complet : 4.14)
- Échec 2 : dashboard en OOM avec 7,5 Go RAM → VM montée à 16 Go + swap 4 Go
- Échec 3 : purge dpkg bloquée (prerm exit 127 après suppression
  manuelle de /var/ossec) → contourné en supprimant
  /var/lib/dpkg/info/wazuh-manager.prerm puis dpkg --purge
- ✅ Installation all-in-one réussie (indexer + manager + dashboard)

## Jour 4 — Agents
- Agent Ubuntu DVWA : OK, modules SCA/FIM/syscollector actifs
- Agent Windows : erreurs de syntaxe PowerShell (commandes chaînées
  sans ';') puis nom de service incorrect (WazuhSvc, pas wazuh-agent)
- ✅ 2 agents Active dans le dashboard

## Jour 5 — Sysmon
- Sysmon64 installé avec config sysmon-modular (Olaf Hartong)
- Canal Microsoft-Windows-Sysmon/Operational ajouté à ossec.conf
- ⚠️ Piège : le service Wazuh Windows s'appelle WazuhSvc
- ✅ Events Sysmon visibles dans Wazuh (Security Events)
