---
title: 'Using local SSD storage'
published: true
date: '08-08-2018 10:11'
taxonomy:
    category:
        - tutorial
---

**Local SSD Storage als Alternative zu Distributed Storage**

## Ziel

Diese Anleitung dient dazu, Sie in die Lage zu versetzen, Local SSD Storage anstelle des üblichen Distributed Storage als Ephemeral Storage im SysEleven Stack zu verwenden.


## Voraussetzungen

* Sie sollten in der Lage sein, einfache Heat-Templates zu verwenden, wie in [Erste Schritte](/tutorials/firststeps/) gezeigt.
* Sie sollten die Grundlagen der [OpenStack-Kommandozeilenwerkzeuge](/tutorials/openstack-cli/) kennen.
* Umgebungsvariablen werden gesetzt, wie im [API-Zugriff-Einrichten](/tutorials/api-access/) gezeigt.


## Wie man eine Instanz mit Local SSD Storage erzeugt

Es gibt zwei Möglichkeiten, die wir Ihnen hier beide zeigen, beginnend mit der, die am schnellsten zum Ziel führt.


### Verwenden Sie unser Heat-Beispiel für einen einfachen Einzelserver mit Local SSD Storage

Um mit unseren [Heat-Beispielen](https://github.com/syseleven/heat-examples) auf Github zu arbeiten, klonen sie sie zunächst:

```shell
$ git clone https://github.com/syseleven/heat-examples
$ cd heat-examples/single-server-on-local-storage
```

Nun können Sie den Beispiel-Stack für Local SSD Storage erzeugen:

```
$ openstack stack create -t example.yaml local-storage-example-stack -e example-env.yaml --parameter key_name=<ssh key name> --wait
```

In dieser Anweisung steht `key_name` für den SSH-Key, den Sie im [SSH Tutorial](/tutorials/ssh-keys/) hinterlegt haben.

Sie haben soeben einen einfachen Server erstellt, dessen Dateisystem Local SSD Storage verwendet.


### Wandeln Sie eine andere Anleitung oder ein anderes Heat-Beispiel ab

Sie können andere Anleitungen oder Beispiele abwandeln, um Local SSD Storage anstelle des Distributed Storage zu verwenden.
Das ergibt nicht immer Sinn, da nicht alle Anwendungen von Local SSD Storage profitieren, aber es ist im Prinzip möglich.
Dazu folgen Sie den Anweisungen bis vor die Stelle, an der `openstack stack create` ausgeführt wird.
Bearbeiten Sie die Stack-Datei(en) und ersetzen die den Flavor `m1.*` durch den entsprechenden `l1.*` Flavor.
Wenn Sie mit der Erstellung des Stacks fortfahren, werden der/die Server anstelle des Distributed Storage nun Local SSD Storage verwenden.


## Weitere Auswirkungen

Bitte lesen Sie auch unsere [FAQ zu Local SSD Storage](../faq/local-storage), um mehr über die Auswirkungen des Einsatzes von Local SSD Storage zu erfahren.


## Zusammenfassung

Sie haben einen einfachen Server erstellt, der Local SSD Storage nutzt und gelernt, wie sie andere Anleitungen abwandeln, um ebenfalls Local SSD Storage zu verwenden.
Sie sollten nun in der Lage sein, alles, was Sie bisher nur mit Distrubuted Storage machen konnten, zukünftig auch mit Local SSD Storage zu tun.