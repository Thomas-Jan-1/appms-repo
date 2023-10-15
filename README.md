# appms-repo
***
![AppMS, eine Basis für viele Anwendungen](/img/eine_basis_fuer_viele_apps.jpg)


## Table of Contents
1. [Verwendungszweck](#Verwendungszweck)
2. [Funktionsüberblick](#Funktionsüberblick)
3. [Anwendungsbeispiele](#Anwendungsbeispiele)
4. [Installation](#Installation)
4.1. [Systemvoraussetzungen](#Systemvoraussetzungen)
4.2. [Installation mit Ansible](#Installation_mit_Ansible)
4.3. [Weitere Installationsmöglichkeiten](#weitere_Installationsmöglichkeiten)


## Verwendungszweck
***

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


## Funktionsüberblick
***

* statische Formulare
* interaktive Formulare
* voneinander abhängige Formulare
* Workflow-Manager
* Auswertungsdesigner
* Authentifizierungsmethoden: interne DB und Ldap (SSO in Arbeit)
* Anbindung mehrerer DBMS auf einer Maske (postgres, MySql)
* durchgängiges Rollen- und Rechte-Management
* umfangreiche Security-Maßnahmen
* integrierter Debugger
* Exportformate: csv, rtf, mail
* flexible Design-Gestaltung
* Verwaltung von historisierten Daten
* Daten dynamsich per Ajax nachladen
* serverseitiges Anstoßen von Scripten (shell, cmd)





## Anwendungsbeispiele
***
umgesetzte Anwendungen
* **BI-Manager** (Tool zur Verwaltung von Schlüsseltabellen und Datenimporten eines DataWarehouse als Teil eines Business-Intelligence-Systems)
![App BI-Manager](/img/example_bi-manager.png)



* **Antragstool** (Tool zur Erstellung von Online-Formularen, die einen einfachen Standardworkflow durchlaufen)
![App Antragstool](/img/example_req11.png)



* **Workflow-Manager** (integraler Bestandteil aller Tools -> alle Daten können auch über Workflows erfasst werden.)
![App Workflow](/img/example_workflow.png)



* **Wählerverzeichnis** (Online Wählerverzeichnis zur Unterstützung des Wahlablaufes; inkl. SOAP-Schnittstelle zur datenliefernden Anwendung)
![App Wählerverzeichnis](/img/example_vote1.png)



## Installation
***

$ git clone https://example.com
$ cd ../path/to/the/file
$ npm install
$ npm start


### Systemvoraussetzungen
ein wenig Text


### Installation_mit_Ansible
ein wenig Text


### weitere_Installationsmöglichkeiten
ein wenig Text
