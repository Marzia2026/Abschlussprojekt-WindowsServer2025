# Abschlussdokumentation – Windows Server 2025

## Projekt: TechWork Solutions
## Betriebssystem: Windows Server 2025
## Domain Controller: TW-DC01
## Domäne: firma.local

## 1. Projektziel

Ziel dieses Projekts war es, wichtige Funktionen der Windows-Server-Administration zu konfigurieren, zu testen und zu dokumentieren.

Die praktische Umsetzung umfasst zwölf Aufgabenbereiche. Die Konfigurationen und Ergebnisse wurden durch Screenshots dokumentiert. Die Nachweisbilder befinden sich im GitHub-Repository im Ordner Screenshots/.
### Aufgrund Speicherplatz (Festplatten und RAM) konnte nicht Aufgabe 13 abgeschlossen werden.
## 2. Technische Rahmenbedingungen

Während der Durchführung gab es zwei wesentliche Einschränkungen:

Kein separater Windows-11-Client

Aufgrund des begrenzten verfügbaren Festplattenspeichers konnte kein zusätzlicher Windows-11-Client installiert werden. Deshalb wurden die Konfigurationen und Tests soweit möglich direkt auf dem Server und mit den dort eingerichteten Benutzerkonten durchgeführt.

Dadurch konnten nicht alle Tests in einer separaten Windows-11-Clientumgebung durchgeführt werden.

Domänenname

Der Domänenname firma.local wurde aus Zeitgründen während des Projekts nicht mehr geändert. Die Aufgaben wurden daher in der bestehenden Domänenumgebung umgesetzt.

Diese Einschränkungen werden transparent dokumentiert, damit die Rahmenbedingungen bei der Bewertung berücksichtigt werden können.

## 3. Übersicht der Aufgaben
Aufgabe	Beschreibung
A01 – Active Directory	Organisationseinheiten, Sicherheitsgruppen und Benutzerkonten eingerichtet.
A02 – NTFS- und Freigabeberechtigungen	Zugriffsrechte für verschiedene Benutzergruppen konfiguriert und überprüft.
A03 – Gruppenrichtlinien (GPO)	Gruppenrichtlinien eingerichtet und die Wallpaper-Richtlinie dokumentiert.
A04 – Storage Spaces	Storage Pools, virtuelle Datenträger und Volumes konfiguriert.
A05 – BitLocker und EFS	Laufwerks- und Dateiverschlüsselung konfiguriert und überprüft.
A06 – Datendeduplizierung	Datendeduplizierung eingerichtet und Statusinformationen überprüft.
A07 – FSRM-Kontingente	Speicherkontingente mit File Server Resource Manager konfiguriert.
A08 – IIS-Webserver	IIS eingerichtet und die Webserverfunktion überprüft.
A09 – Remote Desktop Services	Remotedesktopdienste konfiguriert und dokumentiert.
A10 – Druckserver	Druckerverwaltung und Druckerkonfiguration dokumentiert.
A11 – Windows Admin Center	Verbindung hergestellt und das Dashboard dokumentiert.
A12 – Windows Server Backup	Sicherungseinstellungen, Zeitplanung und Sicherungsergebnis dokumentiert.
## 4. Dokumentation und Nachweise

Die durchgeführten Konfigurationen und verfügbaren Testergebnisse wurden mit Screenshots dokumentiert.

Die Bilder sind im GitHub-Repository unter Screenshots/ gespeichert und im README.md den jeweiligen Aufgaben A01 bis A12 zugeordnet.

Die Screenshots dienen als Nachweise für die dokumentierten Arbeitsschritte. Aufgrund der fehlenden separaten Windows-11-Clientumgebung sind die Ergebnisse im Rahmen der tatsächlich verfügbaren Testmöglichkeiten zu betrachten.

## 5. Fazit

Im Rahmen dieses Projekts wurden zwölf wichtige Bereiche der Windows-Server-Administration bearbeitet.

Dazu gehören die Benutzer- und Gruppenverwaltung, Berechtigungen, Gruppenrichtlinien, Speicherverwaltung, Verschlüsselung, Datendeduplizierung, Kontingente, Webserver, Remotedesktopdienste, Druckverwaltung, Windows Admin Center und Datensicherung.

Trotz der begrenzten Festplattenkapazität und der verfügbaren Projektzeit konnten die vorgesehenen Themen bearbeitet und dokumentiert werden.

Das Projekt bot die Möglichkeit, praktische Erfahrungen mit der Verwaltung und Konfiguration von Windows Server 2025 zu sammeln.
