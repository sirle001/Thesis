# Readme

In dem Ordner LabAssistantApp befinden sich alle Programmteile der Anwendung.
Der MessageBroker (Mosquitto) sowie der Datenbankserver (postgres) muss gestartet werden.

### Datenbank erzeugen und befüllen
Bevor die Anwendung verwendet werden kann, muss die Datenbank erzeugt und befüllt werden.
```sh
$ cd /LabAssistantApp/LabAssistantBackend/Database
$ python DBinit.py Data.json --clearfile CreateDB.sql --host <hostip> --user <username> --password <password>
```
Das Clearfile setzt die Datenbank in den Ausgangszustand zurück, der Host gibt an wo der Datenbankserver läuft (z.B. 127.0.0.1), Username und Passwort der Datenbank werden ggf. benötigt.

### Server starten
```sh
$ cd /LabAssistantApp/LabAssistantBackend/Communication/BackFront
$ python BackendClientMqtt.py <mqtthost> --mqtt_port <port> --postgres_host <host> --postgres_user <username> --postgres_password <password>
```

### LabSimulation
Die mobile App, die die Laborgeräte simuliert ist zu finden unter:
```sh
$ cd /LabAssistantApp/LabAssistantFrontend/LabSimulation
```
Um die Anwendung nutzen zu können, muss die IP des Servers eingestellt werden.

### LabAssistantApp
Die mobile Anwendung zur Prozessüberwachung ist zu finden unter:
```sh
$ cd /LabAssistantApp/LabAssistantFrontend/LabAssistant
```
Um die Anwendung nutzen zu können, muss die IP des Servers und die ID (1 oder 2) eingestellt werden (Settings in der ActionBar). Beispiel-Barcodes sind im entsprechenden Ordner zu finden.
