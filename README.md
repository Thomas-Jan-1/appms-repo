***
# appms-repo

![AppMS, eine Basis für viele Anwendungen](/img/eine_basis_fuer_viele_apps.jpg)


## Table of Contents
1. [Verwendungszweck](##Verwendungszweck)
2. [Funktionsüberblick](##Funktionsüberblick)
3. [Anwendungsbeispiele](##Anwendungsbeispiele)
4. [Installation](##Installation)
4.1. [Systemvoraussetzungen](###Systemvoraussetzungen)
4.2. [Installation mit Ansible](###Installation mit Ansible - komplett)
4.3. [Weitere Installationsmöglichkeiten](###weitere Installationsmöglichkeiten)
4.3.1 [Installation unter Ubuntu](####Installation unter Ubuntu - komplett)
4.3.2 [Installation unter Windows](####Installtion unter Windows - komplett)
5. [Update einspielen](##Update einspielen)
6. [zusätzliche Anwendung installieren](##zusätzliche Anwendungen installieren)



***
## Verwendungszweck



**AppMS ist ein Baukasten für Webanwendungen**
Dabei folgt AppMS dem Konzept von relationalen Datenbankmanagementsystemen (DBMS).

  * Beliebig viele Anwendungen (APP's) werden durch ein zentrales Anwendungsverwaltungssystem verwaltet (Multi-App-Management)
  * Zentrale Funktionen, wie bspw. Benutzer- und Rollenverwaltung, Authentifizierung, Ajax, Masken rendern, CSS-Konfiguration, Debugging, Query-Building, Backup- und Update, Workflow-Management, Sicherheitsfunktionen usw. werden durch das Kernmodul zur Verfügung gestellt.
  * mehrere APP‘s können auf einem gemeinsamen oder auch auf mehreren verteilten Hosts betrieben werden.
  * Zugrundeliegende Datenbank-Schemata können in einem zentralen oder auch verteilt in unterschiedlichen DBMS betrieben werden.
  * Anwendungen werden nicht programmiert, sondern konfiguriert!
  * Spezialfunktionen für Einzelanwendungen, welche nicht durch das Kernmodul bereitgestellt werden, können ergänzt werden (Plugin).
  * Verbesserungen bzw. Erweiterungen in den Kernfunktionen kommen allen Anwendungen zu Gute.


**AppMS-Anwendungen altern nicht, da sie regelmäßig über Updates des Kernmoduls auf einem aktuellen technischen Stand gehalten werden.**

***
## Funktionsüberblick


* statische Formulare
* interaktive Formulare
* voneinander abhängige Formulare
* Workflow-Manager
* Auswertungsdesigner
* Authentifizierungsmethoden: interne DB und Ldap (SSO in Arbeit)
* Anbindung mehrerer DBMS auf einer Maske (postgres, MySql)
* durchgängiges Rollen- und Rechte-Modell
* umfangreiche Security-Maßnahmen
* integrierter Debugger
* Exportformate: csv, rtf, mail
* flexible Design-Gestaltung
* Verwaltung von historisierten Daten
* Daten dynamsich per Ajax nachladen
* serverseitiges Anstoßen von Scripten (unix->shell oder  windows->cmd)




***
## Anwendungsbeispiele


* **BI-Manager** (Tool zur Verwaltung von Schlüsseltabellen und Datenimporten eines DataWarehouse als Teil eines Business-Intelligence-Systems)
![App BI-Manager](/img/example_bi-manager.png)





* **Antragstool** (Tool zur Erstellung von Online-Formularen, die einen einfachen Standardworkflow durchlaufen)
![App Antragstool](/img/example_req11.png)





* **Workflow-Manager** (integraler Bestandteil aller Tools -> alle Daten können auch über Workflows erfasst werden.)
![App Workflow](/img/example_workflow.png)





* **Wählerverzeichnis** (Online Wählerverzeichnis zur Unterstützung des Wahlablaufes; inkl. SOAP-Schnittstelle zur datenliefernden Anwendung)
![App Wählerverzeichnis](/img/example_vote1.png)




***
## Installation


### Systemvoraussetzungen
**<span style="background-color:lightyellow">Beachte, dass von den nachfolgend genannten Produkten stets nur aktuelle  Versionen eingesetzt werden sollten!</span>**


  * Webserver: Apache 
  * PHP
  * Datenbank: Postgres (empfohlen), MySql oder MariaDB
  * [ggf. Ldap-Verbindung]
  * Client: aktueller Browser (Bspw. Firefox, Edge, Safari, Chrome, Opera, …)

***
### Installation_mit_Ansible - komplett
Am einfachsten ist es AppMS mit Hilfe eines Ansible-Skriptes zu installieren. Das Script ist zur Installation auf Basis von Ubuntu 22.04 geeignet. Dabei werden alle Abhängigkeiten (postgres, Apache, ufw, ...) ebenfalls installiert und konfiguriert.
Wenn Sie bereits einen fertig konfigurierten Webserver haben, dann nutzen Sie die Installationsmethode 


ToDo's:
-------
- warum ist files/appms_step1.dump?
- Wieso wird die dfn-chain mit ausgeliefert?
- Kann die aktuellste appms-sys01-Datei aus dem repo per wget abgeholt werden?
- Warum fehlten die Pakete, welche in der dokuwiki-Installation genannt werden?


***
### weitere_Installationsmöglichkeiten


#### Installation unter Ubuntu - komplett
![Installation einer produktiven Umgebung unter Ubuntu](/install/installation_einer_produktivumgebung_ubuntu.pdf)


#### Installation unter Windows - komplett
![Installation einer produktiven Umgebung unter Ubuntu](/install/installation_einer_testumgebung_windows.pdf)

#### Installation für vorhandenen Webserver - nur AppMS
Voraussetzungen:
- Webserver (Apache) ist vorhanden
- Datenbank (postgres) ist vorhanden
- hier ergänzen




## Update einspielen
![Update einspielen](/install/update_programmversion_installieren.pdf)

## zusätzliche Anwendung installieren
- Gibt es dafür bereits eine Anleitung? Falls nein im Wiki erstellen oder Maske "neue APP installieren" erweitern.
Testen mit REQ11
- prüfen, ob die normale Installation bereits das Wiki installiert -> laut Programmcode, ja


!!! Für eine Erstauslieferung reicht das!!!


-> in Ansible-Script die aktuelles Version herunterladen -> Wie kann die ermittelt werden?
-> in Ansible auch gleich die Wiki-Inhalte von SYS01 herunterladen und installieren?


