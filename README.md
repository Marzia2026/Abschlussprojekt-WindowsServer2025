# Abschlussprojekt-WindowsServer2025
TechWork Solutions

Domäne: firma.local
Domain Controller: TW-DC01
Betriebssystem: Windows Server 2025

Projektübersicht

Dieses Projekt dokumentiert die Konfiguration und Umsetzung von zwölf Aufgaben im Rahmen des Abschlussprojekts Windows Server 2025.

Die einzelnen Aufgaben umfassen Active Directory, Berechtigungen, Gruppenrichtlinien, Speicherverwaltung, Verschlüsselung, Datendeduplizierung, Kontingente, Webserver, Remotedesktopdienste, Druckverwaltung, Windows Admin Center und Datensicherung.

Die zugehörigen Nachweisbilder befinden sich im Ordner Screenshots/ und werden unter den jeweiligen Aufgaben angezeigt.

Inhaltsverzeichnis
A01 – Active Directory
A02 – NTFS- und Freigabeberechtigungen
A03 – Gruppenrichtlinien (GPO)
A04 – Storage Spaces
A05 – BitLocker und EFS
A06 – Datendeduplizierung
A07 – FSRM-Kontingente
A08 – IIS-Webserver
A09 – Remote Desktop Services
A010 – Druckserver
A011 – Windows Admin Center
A012 – Windows Server Backup
A01 – Active Directory
Ziel

Einrichtung der Organisationseinheiten, Sicherheitsgruppen und Benutzerkonten für die Mitarbeiter von TechWork Solutions.

Organisationseinheiten
TW-Mitarbeiter
TW-Gruppen
TW-Computer
Sicherheitsgruppen
GG_Geschaeftsfuehrung
GG_IT_Admin
GG_Buchhaltung
GG_Alle_Mitarbeiter
Benutzer und Gruppenmitgliedschaften
Benutzer	Gruppenmitgliedschaften
m.huber	GG_Geschaeftsfuehrung, GG_Alle_Mitarbeiter
t.berger	GG_IT_Admin, GG_Alle_Mitarbeiter
s.wagner	GG_Buchhaltung, GG_Alle_Mitarbeiter
Nachweis 1 – OU-Struktur und Sicherheitsgruppen




Nachweis 2 – Mitarbeiter




A02 – NTFS- und Freigabeberechtigungen
Ziel

Einrichtung geeigneter NTFS- und Freigabeberechtigungen, um den Zugriff auf die gemeinsamen Ordner entsprechend den jeweiligen Aufgabenbereichen zu steuern.

Berechtigungskonzept
Bereich	Sicherheitsgruppe	Zweck
Geschäftsführung	GG_Geschaeftsfuehrung	Zugriff auf den Geschäftsführungsbereich
IT	GG_IT_Admin	Zugriff auf den IT-Bereich
Buchhaltung	GG_Buchhaltung	Zugriff auf den Buchhaltungsbereich
Gemeinsame Dateien	GG_Alle_Mitarbeiter	Zugriff auf freigegebene gemeinsame Dateien

Die tatsächlichen Zugriffsrechte werden durch die konfigurierten NTFS- und Freigabeberechtigungen bestimmt.

Nachweis 1 – Gesamtübersicht




Nachweis 2 – Berechtigungen der Geschäftsführung




Nachweis 3 – Berechtigungen der IT




Nachweis 4 – Berechtigungen der Buchhaltung




Nachweis 5 – Zugriff vom Client




Nachweis 6 – NTFS-Berechtigungen




Nachweis 7 – Zugriff verweigert




Nachweis 8 – Berechtigungseinstellungen




Nachweis 9 – Zugriff auf freigegebene Ordner




A03 – Gruppenrichtlinien (GPO)
Ziel

Zentrale Verwaltung von Benutzer- und Computereinstellungen über Gruppenrichtlinien.

Umsetzung
Verknüpfung einer Gruppenrichtlinie mit einer Organisationseinheit.
Konfiguration einer Desktop-Hintergrundrichtlinie.
Überprüfung der Richtlinienanwendung auf einem Client.
Test des Zugriffs auf Dateien über das Netzwerk.
Nachweis 1 – Dateizugriff über das Netzwerk




Nachweis 2 – GPO-Verknüpfung mit einer OU




Nachweis 3 – Wallpaper-GPO




Nachweis 4 – Hintergrundbild nach der Anmeldung




A04 – Storage Spaces
Ziel

Konfiguration von Storage Spaces zur zentralen Verwaltung physischer Datenträger und virtueller Speicher.

Umsetzung
Erstellung und Verwaltung eines Storage Pools.
Konfiguration eines virtuellen Datenträgers.
Bereitstellung eines Volumes für die Datenspeicherung.
Nachweis 1 – Storage Pools




Nachweis 2 – Storage und Virtual Disk




Nachweis 3 – Virtueller Datenträger




Nachweis 4 – Storage und Volume E




A05 – BitLocker und EFS
Ziel

Schutz von Daten durch Laufwerksverschlüsselung und Dateiverschlüsselung.

Umsetzung
Konfiguration und Überprüfung von BitLocker.
Verschlüsselung einer Datei mit Encrypting File System (EFS).
Überprüfung des Dateizugriffs durch einen Client.
Kontrolle der Verschlüsselungsfunktion.
Nachweis 1 – BitLocker-Konfiguration




Nachweis 2 – BitLocker-Einstellungen




Nachweis 3 – EFS-verschlüsselte Datei




Nachweis 4 – Client-Zugriff auf verschlüsselte Datei




Nachweis 5 – Funktionsprüfung von BitLocker




A06 – Datendeduplizierung
Ziel

Reduzierung des Speicherbedarfs durch Datendeduplizierung.

Umsetzung
Installation beziehungsweise Konfiguration der Datendeduplizierung.
Überprüfung des Deduplizierungsstatus.
Kontrolle der Konfiguration über die verfügbaren Verwaltungstools.
Nachweis 1 – Datendeduplizierung




Nachweis 2 – Get-DedupStatus




A07 – FSRM-Kontingente
Ziel

Verwaltung des Speicherverbrauchs mithilfe von File Server Resource Manager (FSRM).

Umsetzung
Konfiguration eines Speicherkontingents.
Begrenzung des verfügbaren Speicherplatzes entsprechend den vorgenommenen Einstellungen.
Überprüfung der Kontingentkonfiguration.
Nachweis – Quota-Konfiguration




A08 – IIS-Webserver
Ziel

Installation und Konfiguration eines Webservers mit Internet Information Services (IIS).

Umsetzung
Installation und Konfiguration der IIS-Rolle.
Bereitstellung einer Website.
Überprüfung der Erreichbarkeit vom Client aus.
Nachweis 1 – Webserver-Test vom Client




Nachweis 2 – IIS-Konfiguration




A09 – Remote Desktop Services
Ziel

Einrichtung und Überprüfung der Remotedesktopdienste für den Fernzugriff.

Umsetzung
Installation beziehungsweise Konfiguration der benötigten RDS-Komponenten.
Überprüfung der Verbindung vom Client.
Kontrolle der Benutzer- und Serverkonfiguration.
Nachweis 1 – RDS-Installation und Verbindung




Nachweis 2 – Remotedesktop-Test vom Client




Nachweis 3 – RDS-Konfiguration




Nachweis 4 – RDS-Benutzer




Nachweis 5 – Remotedesktop vom Client




A10 – Druckserver
Ziel

Zentrale Verwaltung von Druckern über die Druckserverfunktion von Windows Server 2025.

Umsetzung
Verwaltung der Drucker über die Druckerverwaltung.
Überprüfung der installierten Drucker.
Kontrolle der Drucker- und Scannerkonfiguration.
Nachweis 1 – TW-Drucker in Print Management




Nachweis 2 – Printer und Scanner




A11 – Windows Admin Center
Ziel

Zentrale browserbasierte Verwaltung des Windows Servers über Windows Admin Center (WAC).

Umsetzung
Herstellung einer Verbindung mit Windows Admin Center.
Überprüfung der Verbindung zum verwalteten Server.
Kontrolle der verfügbaren Verwaltungsfunktionen im Dashboard.
Nachweis 1 – Windows Admin Center Connection




Nachweis 2 – Windows Admin Center Dashboard




A12 – Windows Server Backup
Ziel

Konfiguration und Überprüfung einer Datensicherung mit Windows Server Backup.

Umsetzung
Auswahl der zu sichernden Elemente.
Konfiguration eines Sicherungszeitplans.
Durchführung einer Sicherung.
Überprüfung des Sicherungsergebnisses.
Nachweis 1 – Auswahl der Sicherungselemente




Nachweis 2 – Erfolgreiche Sicherung




Nachweis 3 – Geplante Sicherung




Fazit

Im Rahmen dieses Abschlussprojekts wurden zwölf zentrale Themen der Windows-Server-Administration dokumentiert.

Die Aufgaben umfassen die Benutzer- und Gruppenverwaltung in Active Directory, die Absicherung von Dateien und Freigaben, die Konfiguration von Gruppenrichtlinien, die Verwaltung von Speicherressourcen, Verschlüsselung, Datendeduplizierung, Kontingente, Webdienste, Remotedesktopdienste, Druckverwaltung, zentrale Serververwaltung und Datensicherung.

Die Screenshots dienen als Nachweise für die dokumentierten Konfigurationen und Tests.
