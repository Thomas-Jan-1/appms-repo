appms_basic
=========

Mit Hilfe dieser Ansible-Rolle kann eine funktionierendes AppMS-System auf eeinem vorhandenen unbuntu-22.04-Server aufgesetzt werden.
Dabei werden alle Abhängigkeiten ebenfalls installiert. Das Script installiert folgende Komponenten:
- lokale Datenbank (postgres)
- Webserver (Apache)
- AppMS  (erreichbar über url/appms/)
- Dokuwiki (lokale Dokumentation von Appms; ereichbar über url/appms/wiki/)


Requirements
------------

1. notwendige ansible-role(s) installieren
   - role apache (ansible-galaxy install geerlingguy.apache)
2. bei Bedarf neue Zertifikate erzeugen und die vorhandenen in Ordner "files" ersetzen 
   Beispiel zur Erzeugung von selbstsignierten Zertifikaten:
   sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/private/appms-test-selfsigned.key -out /etc/ssl/certs/appms-test-selfsigned.crt
3. Targetserver: Ubuntu Server 22.04
4. **playbook-start**: ansible-playbook playbooks_IVO/appms_basic.yml -kKb


Role Variables
--------------

Die Variablen werden in der Datei appms_basic/vars/my_vars.yml definiert. Alle Variablen werden dort auch erläutert. Die meisten Variablen können i.d.R. wie vorgegeben verwendet werden. Folgende Variablen sollten jedoch geprüft werden:
- **Zeile 69**: appms_version -> Falls eine neuere Version verfügbar ist, kann diese genutzt werden. Die neue Versionsdatei muss in dem Fall im ansible-Ordner appms_basic/files abgelegt werden.
- **Zeile 81**: appms_db_userpassword -> ein beliebiges Passwort festlegen.




Example Playbook
----------------
```bash
- name: Execute appms_basic playbook
  hosts: appms-test-server-02
  become: true
  vars_files:
    - ../[roles]/appms_basic/vars/my_vars.yml

  roles:
  #-> Aufruf des Default-Skriptes (appms_basic/tasks/main.yml
    - appms_basic
```


License
-------

BSD


Author Information
------------------

Thomas J.
