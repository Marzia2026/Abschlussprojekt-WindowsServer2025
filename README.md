# Abschlussprojekt – Windows Server 2025

## TechWork Solutions

**Domäne:** `firma.local`
**Domain Controller:** `TW-DC01`
**Betriebssystem:** Windows Server 2025

## Projektübersicht

Dieses Projekt dokumentiert die Konfiguration und Umsetzung von zwölf Aufgaben im Rahmen des Abschlussprojekts Windows Server 2025.

Die einzelnen Aufgaben umfassen Active Directory, Berechtigungen, Gruppenrichtlinien, Speicherverwaltung, Verschlüsselung, Datendeduplizierung, Kontingente, Webserver, Remotedesktopdienste, Druckverwaltung, Windows Admin Center und Datensicherung.
Aufgrund von Speicherplatz-undRAM mangel, Aufgabe 13 kann nicht abgeschlossen werden. 
Die zugehörigen Nachweisbilder befinden sich im Ordner `Screenshots/` und werden unter den jeweiligen Aufgaben angezeigt.

## Inhaltsverzeichnis

1. [A01 – Active Directory](#a01--active-directory)
2. [A02 – NTFS- und Freigabeberechtigungen](#a02--ntfs--und-freigabeberechtigungen)
3. [A03 – Gruppenrichtlinien (GPO)](#a03--gruppenrichtlinien-gpo)
4. [A04 – Storage Spaces](#a04--storage-spaces)
5. [A05 – BitLocker und EFS](#a05--bitlocker-und-efs)
6. [A06 – Datendeduplizierung](#a06--datendeduplizierung)
7. [A07 – FSRM-Kontingente](#a07--fsrm-kontingente)
8. [A08 – IIS-Webserver](#a08--iis-webserver)
9. [A09 – Remote Desktop Services](#a09--remote-desktop-services)
10. [A10 – Druckserver](#a10--druckserver)
11. [A11 – Windows Admin Center](#a11--windows-admin-center)
12. [A12 – Windows Server Backup](#a12--windows-server-backup)

---

## A01 – Active Directory

### Ziel

Einrichtung der Organisationseinheiten, Sicherheitsgruppen und Benutzerkonten für die Mitarbeiter von TechWork Solutions.

### Organisationseinheiten

* TW-Mitarbeiter
* TW-Gruppen
* TW-Computer

### Sicherheitsgruppen

* `GG_Geschaeftsfuehrung`
* `GG_IT_Admin`
* `GG_Buchhaltung`
* `GG_Alle_Mitarbeiter`

### Benutzer und Gruppenmitgliedschaften

| Benutzer | Gruppenmitgliedschaften                    |
| -------- | ------------------------------------------ |
| m.huber  | GG_Geschaeftsfuehrung, GG_Alle_Mitarbeiter |
| t.berger | GG_IT_Admin, GG_Alle_Mitarbeiter           |
| s.wagner | GG_Buchhaltung, GG_Alle_Mitarbeiter        |

### Nachweis 1 – OU-Struktur und Sicherheitsgruppen

![A01 – OU-Struktur und Sicherheitsgruppen](<Screenshots/A01-OU-Struktur &_Sicherheitsgruppen.png>)

### Nachweis 2 – Mitarbeiter

![A01 – Mitarbeiter](Screenshots/A01-Mitarbeiter.png)

---

## A02 – NTFS- und Freigabeberechtigungen

### Ziel

Einrichtung geeigneter NTFS- und Freigabeberechtigungen, um den Zugriff auf die gemeinsamen Ordner entsprechend den jeweiligen Aufgabenbereichen zu steuern.

### Berechtigungskonzept

| Bereich            | Sicherheitsgruppe     | Zweck                                       |
| ------------------ | --------------------- | ------------------------------------------- |
| Geschäftsführung   | GG_Geschaeftsfuehrung | Zugriff auf den Geschäftsführungsbereich    |
| IT                 | GG_IT_Admin           | Zugriff auf den IT-Bereich                  |
| Buchhaltung        | GG_Buchhaltung        | Zugriff auf den Buchhaltungsbereich         |
| Gemeinsame Dateien | GG_Alle_Mitarbeiter   | Zugriff auf freigegebene gemeinsame Dateien |

Die tatsächlichen Zugriffsrechte werden durch die konfigurierten NTFS- und Freigabeberechtigungen bestimmt.

### Nachweis 1 – Gesamtübersicht

![A02 – Gesamtübersicht](Screenshots/A02-01-All.png)

### Nachweis 2 – Berechtigungen der Geschäftsführung

![A02 – NTFS Geschäftsführung](Screenshots/A02-02-NTFS-Geschaeftsfuehrung.png)

### Nachweis 3 – Berechtigungen der IT

![A02 – NTFS IT](Screenshots/A02-03-NTFS-IT.png)

### Nachweis 4 – Berechtigungen der Buchhaltung

![A02 – NTFS Buchhaltung](Screenshots/A02-04-NTFS-Buchhaltung.png)

### Nachweis 5 – Zugriff vom Client

![A02 – NTFS vom Client](<Screenshots/A02-05-NTFS von CLIENT.png>)

### Nachweis 6 – NTFS-Berechtigungen

![A02 – NTFS-Berechtigung](Screenshots/A02-06-NTFS-Berechtigung.png)

### Nachweis 7 – Zugriff verweigert

![A02 – Client kann nicht zugreifen](<Screenshots/A02-07-NTFS-CLIent cannt ACCEESS.png>)

### Nachweis 8 – Berechtigungseinstellungen

![A02 – NTFS Permissions](Screenshots/A02-08-NTFS-PERm.png)

### Nachweis 9 – Zugriff auf freigegebene Ordner

![A02 – Shared Folders Access](Screenshots/A02-09-SharedFoldersAccess.png)

---

## A03 – Gruppenrichtlinien (GPO)

### Ziel

Zentrale Verwaltung von Benutzer- und Computereinstellungen über Gruppenrichtlinien.

### Umsetzung

* Verknüpfung einer Gruppenrichtlinie mit einer Organisationseinheit.
* Konfiguration einer Desktop-Hintergrundrichtlinie.
* Überprüfung der Richtlinienanwendung auf einem Client.
* Test des Zugriffs auf Dateien über das Netzwerk.

### Nachweis 1 – Dateizugriff über das Netzwerk

![A03 – Access File via Network](<Screenshots/A03-01-AccessFile Via Network.png>)

### Nachweis 2 – GPO-Verknüpfung mit einer OU

![A03 – GPO und OU](<Screenshots/A03-02-connection GPO o OU.png>)

### Nachweis 3 – Wallpaper-GPO

![A03 – GPO Wallpaper](Screenshots/A03-03-GPO-Wallpaper.png)

### Nachweis 4 – Hintergrundbild nach der Anmeldung

![A03 – Wallpaper bei der Anmeldung](<Screenshots/A03-04-Wallpaper IN LoGON.png>)

---

## A04 – Storage Spaces

### Ziel

Konfiguration von Storage Spaces zur zentralen Verwaltung physischer Datenträger und virtueller Speicher.

### Umsetzung

* Erstellung und Verwaltung eines Storage Pools.
* Konfiguration eines virtuellen Datenträgers.
* Bereitstellung eines Volumes für die Datenspeicherung.

### Nachweis 1 – Storage Pools

![A04 – Storage Pools](Screenshots/A04-01-Storage-Pools.png)

### Nachweis 2 – Storage und Virtual Disk

![A04 – Storage und Virtual Disk](<Screenshots/A04-02-Storage & VirtualDisk.png>)

### Nachweis 3 – Virtueller Datenträger

![A04 – Virtual Disk](Screenshots/A04-03-VDisk.png)

### Nachweis 4 – Storage und Volume E

![A04 – Storage und Volume E](Screenshots/A04-04-Storage\&VolumeE.png)

---

## A05 – BitLocker und EFS

### Ziel

Schutz von Daten durch Laufwerksverschlüsselung und Dateiverschlüsselung.

### Umsetzung

* Konfiguration und Überprüfung von BitLocker.
* Verschlüsselung einer Datei mit Encrypting File System (EFS).
* Überprüfung des Dateizugriffs durch einen Client.
* Kontrolle der Verschlüsselungsfunktion.

### Nachweis 1 – BitLocker-Konfiguration

![A05 – BitLocker](Screenshots/A05-01-BitLocker.png)

### Nachweis 2 – BitLocker-Einstellungen

![A05 – BitLocker Einstellungen](Screenshots/A05-02-BitLocker.png)

### Nachweis 3 – EFS-verschlüsselte Datei

![A05 – EFS File Encrypted](<Screenshots/A05-03-EFSFile Encrypted.png>)

### Nachweis 4 – Client-Zugriff auf verschlüsselte Datei

![A05 – Client kann nicht zugreifen](Screenshots/A05-04-ClientCanntAccess.png)

### Nachweis 5 – Funktionsprüfung von BitLocker

![A05 – BitLocker funktioniert](<Screenshots/A05-05-Bitlocker Funktioniert.png>)

---

## A06 – Datendeduplizierung

### Ziel

Reduzierung des Speicherbedarfs durch Datendeduplizierung.

### Umsetzung

* Installation beziehungsweise Konfiguration der Datendeduplizierung.
* Überprüfung des Deduplizierungsstatus.
* Kontrolle der Konfiguration über die verfügbaren Verwaltungstools.

### Nachweis 1 – Datendeduplizierung

![A06 – Datendeduplizierung](Screenshots/A06-01-Dataduplication.png)

### Nachweis 2 – Get-DedupStatus

![A06 – Get-DedupStatus](Screenshots/A06-02-GetDedupStatus.png)

---

## A07 – FSRM-Kontingente

### Ziel

Verwaltung des Speicherverbrauchs mithilfe von File Server Resource Manager (FSRM).

### Umsetzung

* Konfiguration eines Speicherkontingents.
* Begrenzung des verfügbaren Speicherplatzes entsprechend den vorgenommenen Einstellungen.
* Überprüfung der Kontingentkonfiguration.

### Nachweis – Quota-Konfiguration

![A07 – Quota](Screenshots/A07-01-Quota.png)

---

## A08 – IIS-Webserver

### Ziel

Installation und Konfiguration eines Webservers mit Internet Information Services (IIS).

### Umsetzung

* Installation und Konfiguration der IIS-Rolle.
* Bereitstellung einer Website.
* Überprüfung der Erreichbarkeit vom Client aus.

### Nachweis 1 – Webserver-Test vom Client

![A08 – Client Test Web](Screenshots/A08-01-Client.TestWEB.png)

### Nachweis 2 – IIS-Konfiguration

![A08 – IIS](Screenshots/A08-02-IIS.png)

---

## A09 – Remote Desktop Services

### Ziel

Einrichtung und Überprüfung der Remotedesktopdienste für den Fernzugriff.

### Umsetzung

* Installation beziehungsweise Konfiguration der benötigten RDS-Komponenten.
* Überprüfung der Verbindung vom Client.
* Kontrolle der Benutzer- und Serverkonfiguration.

### Nachweis 1 – RDS-Installation und Verbindung

![A09 – RDS Installed and Connect](<Screenshots/A09-01-RDSInstalled & Connect.png>)

### Nachweis 2 – Remotedesktop-Test vom Client

![A09 – Client Remote Test](<Screenshots/A09-02-CLIENTtest REMOT.png>)

### Nachweis 3 – RDS-Konfiguration

![A09 – RDS](Screenshots/A09-03-RDS.png)

### Nachweis 4 – RDS-Benutzer

![A09 – RDS User](Screenshots/A09-04-RDS-USER.png)

### Nachweis 5 – Remotedesktop vom Client

![A09 – Remote Desktop vom Client](<Screenshots/A09-05-RemotDS von CLEINT.png>)

---

## A10 – Druckserver

### Ziel

Zentrale Verwaltung von Druckern über die Druckserverfunktion von Windows Server 2025.

### Umsetzung

* Verwaltung der Drucker über die Druckerverwaltung.
* Überprüfung der installierten Drucker.
* Kontrolle der Drucker- und Scannerkonfiguration.

### Nachweis 1 – TW-Drucker in Print Management

![A10 – TW-Drucker in Print Management](<Screenshots/A10-01-TW-Drucker-01 in PrintManagement.png>)

### Nachweis 2 – Printer und Scanner

![A10 – Printer und Scanner](<Screenshots/A10-02-Printer und Scanner.png>)

---

## A11 – Windows Admin Center

### Ziel

Zentrale browserbasierte Verwaltung des Windows Servers über Windows Admin Center (WAC).

### Umsetzung

* Herstellung einer Verbindung mit Windows Admin Center.
* Überprüfung der Verbindung zum verwalteten Server.
* Kontrolle der verfügbaren Verwaltungsfunktionen im Dashboard.

### Nachweis 1 – Windows Admin Center Connection

![A11 – WAC Connection](Screenshots/A11-01-WACconnection.png)

### Nachweis 2 – Windows Admin Center Dashboard

![A11 – Dashboard](Screenshots/A11-02-Dashboard.png)

---

## A12 – Windows Server Backup

### Ziel

Konfiguration und Überprüfung einer Datensicherung mit Windows Server Backup.

### Umsetzung

* Auswahl der zu sichernden Elemente.
* Konfiguration eines Sicherungszeitplans.
* Durchführung einer Sicherung.
* Überprüfung des Sicherungsergebnisses.

### Nachweis 1 – Auswahl der Sicherungselemente

![A12 – Select Item Backup](<Screenshots/A12-01-SelectItem Backup.png>)

### Nachweis 2 – Erfolgreiche Sicherung

![A12 – Backup Successful](<Screenshots/A12-02-Backup Successful.png>)

### Nachweis 3 – Geplante Sicherung

![A12 – Schedule Backup](Screenshots/A12-03-Schedule-Backup.png)

---

## Fazit

Im Rahmen dieses Abschlussprojekts wurden zwölf zentrale Themen der Windows-Server-Administration dokumentiert.

Die Aufgaben umfassen die Benutzer- und Gruppenverwaltung in Active Directory, die Absicherung von Dateien und Freigaben, die Konfiguration von Gruppenrichtlinien, die Verwaltung von Speicherressourcen, Verschlüsselung, Datendeduplizierung, Kontingente, Webdienste, Remotedesktopdienste, Druckverwaltung, zentrale Serververwaltung und Datensicherung.

Die Screenshots dienen als Nachweise für die dokumentierten Konfigurationen und Tests.
