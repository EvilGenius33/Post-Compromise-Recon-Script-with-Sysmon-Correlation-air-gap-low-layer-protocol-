🛡️ Post-Compromise Recon Script – Air-Gap Aware
Auteur : Xenoz
Version : Final
Nom du script : Recon_AirGap_Sysmon.ps1

🎯 Objectif :
Ce script PowerShell est conçu pour effectuer une analyse post-compromission avancée sur une machine Windows, même dans un environnement air-gapped (isolé du réseau).

Il s’appuie sur les journaux Sysmon et les artefacts locaux pour détecter des indices de compromission, persistance ou d’activité réseau suspecte.

✅ Fonctionnalités clés :
Détection des processus lancés récemment (Sysmon EventID 1)
→ Permet d’observer les processus exécutés après compromission.

Surveillance du trafic multicast/IPv6 local (Sysmon EventID 3)
→ Détecte les signaux de présence d’un agent ou d’un scan latéral.

Analyse des DLL chargées hors répertoire système (Sysmon EventID 7)
→ Alerte sur d’éventuelles DLL injectées en mémoire.

Inspection des tubes nommés et usage de WMI (Sysmon EventIDs 17/18)
→ Permet de repérer les tunnels ou mouvements internes silencieux.

Inventaire des tâches planifiées hors de \Microsoft\
→ Recherche de persistance via scheduled tasks.

Scan des clés Run du registre (HKLM & HKCU)
→ Détection de mécanismes de démarrage automatique malveillants.

Vérification de l’existence de Shadow Copies
→ Identifie si les sauvegardes système ont été supprimées (attaque de type ransomware).

Lecture du journal pare-feu Windows
→ Repère des flux réseau multicast suspects (SSDP, mDNS, ICMPv6).

Journalisation complète dans un fichier .txt sur le bureau de l’utilisateur.

🔒 Sécurité et contexte :
Ce script ne dépend pas d’Internet ni d’API externe. Il est idéal pour les environnements critiques ou pour une analyse post-incident hors-ligne. Il exploite uniquement des outils Windows natifs (Sysmon, PowerShell, VSS, registre).

📂 Résultat :
Un rapport complet nommé airgap_sysmon_report.txt est généré automatiquement sur le bureau.


*© 2025 Xenoz. Tous droits réservés.  
Ce script est un logiciel propriétaire. Toute utilisation, modification, reproduction ou distribution non autorisée est strictement interdite sans autorisation écrite explicite de l’auteur.**
