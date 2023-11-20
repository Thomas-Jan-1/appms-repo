***
# appms-repo

![AppMS, eine Basis für viele Anwendungen](/img/eine_basis_fuer_viele_apps.jpg)


## Table of Contents
- [Verwendungszweck](#Verwendungszweck)
- [Funktionsüberblick](#Funktionsüberblick)
- [Anwendungsbeispiele](#Anwendungsbeispiele)
- [Installation](#Installation)
  - [Systemvoraussetzungen](#Systemvoraussetzungen)
  - [Installation mit Ansible](#Installation-mit-Ansible)
  - [weitere Installationsvarianten](#weitere-Installationsvarianten)
    - [Installation unter Ubuntu](#Installation-unter-Ubuntu)
    - [Installation unter Windows](#Installation-unter-Windows)
- [Update einspielen](#Update-einspielen)
- [zusätzliche Anwendung installieren](#zusätzliche-Anwendungen-installieren)



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
### Installation mit Ansible
Am **einfachsten** ist es AppMS mit Hilfe eines Ansible-Skriptes zu installieren. Das Script ist zur Installation auf Basis von Ubuntu 22.04 geeignet. Dabei werden alle Abhängigkeiten (postgres, Apache, ufw, ...) ebenfalls installiert und konfiguriert.

Hinweise zu Ansible: https://docs.ansible.com/ansible/latest/index.html

Voraussetzung:
- Auf dem Zielhost ist ubuntu 22.04 vorhanden

Vorgehen:
- kopieren Sie sich den Ansible-Ordner: 
```bash
tree 
└───ansible
    ├───roles
    │   └───appms_basic
    │       ├───defaults (wird nicht verwendet)
    │       ├───files    
    │       ├───handlers (wird nicht verwendet)
    │       ├───tasks    
    │       ├───tests    (wird nicht verwendet)
    │       └───vars
    ├───playbooks
    └───hosts.d
```
- individuelles Datenbankpasswort für Nutzer appms festlegen (ansible/roles/appms-basic/vars/my_vars.yml -> Zeile 81)
- Ziel-host in Ansible-Host-Datei eintragen (ansible/host.d/hosts)  Bsp.: appms-test-server-02    ansible_host=192.168.178.48
- Readme-Datei lesen
- playbook starten





***
### weitere Installationsvarianten


#### Installation unter Ubuntu
![Installation einer produktiven Umgebung unter Ubuntu](/install/installation_einer_produktivumgebung_ubuntu.pdf)


#### Installation unter Windows
![Installation einer produktiven Umgebung unter Ubuntu](/install/installation_einer_testumgebung_windows.pdf)


#### Installation für vorhandenen Webserver
Voraussetzungen:
- Webserver (Apache) ist vorhanden
- Datenbank (postgres) ist vorhanden

FixMe: coming soon ...


## Wiki aufrufen
Mit jeder AppMS-Installation wird ein lokales Wiki installiert, welches umfangreiche Anleitungsartikel enthält.
Das Wiki kann über den Browser aufgerufen werden: [URL-des Webservers]/appms/wiki
![Wiki Startseite](/img/wiki-start.png)


## Update einspielen
![Update einspielen](/install/update_programmversion_installieren.pdf)

## zusätzliche Anwendung installieren
Mit Hilfe von AppMS können beliebige Anwendungen erstellt und geteilt werden. In diesem Repository findet sich bspw. die Anwendung "Antragstool (REQ11). Diese kann über die Oberfläche installiert werden.
Vorgehen:
1. In AppMS mit dem Nutzer sys01root anmelden
2. Maske "neue APP installieren" aufrufen.
3. Den Anweisungen folgen.


![eine zusätzliche Anwendung installieren](/img/weitere_app_installieren.png)


