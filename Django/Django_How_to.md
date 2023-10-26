DJANGO
======

Voraussetzung ist eine Python-Installation, (PATH aktivieren!). Siehe auch https://www.python.org/downloads/

Django installieren (innerhalb des venv):
$ python -m pip install Django

	oder

$ py -3 -m pip install Django
--> Gilt in diesem Fall für Python 3, was man an py -3 erkennen kann
--> Siehe auch https://stackoverflow.com/questions/45137395/how-do-i-upgrade-the-python-installation-in-windows-10

Wozu die -m flag?
--> https://www.datasciencebyexample.com/2023/02/08/different-ways-to-install-python-packages-with-pip/

Alternativ kann die Installation von Modulen auch über requirements.txt stattfinden:
--> requirements.txt außerhalb des venv-Verzeichnisses erstellen, dort die Module eintragen und speichern
$ pip install -r requirements.txt

Django-Projekt erstellen (Nicht den Punkt am Ende vergessen, damit das Projekt im gleichen Verzeichnis angelegt wird!)
$ django-admin startproject <projekt_name> . 



Virtuellen Server starten
=========================

ACHTUNG:
--> Um den vServer zu starten, muss man erst ein Projekt erstellt haben, damit die manage.py da ist!
--> Zudem darf das venv nicht aktiv sein!

Zum äußeren Projektverzeichnis navigieren (es gibt zwei Verzeichnisse mit dem gleichen Namen, ein äußeres und ein inneres):
$ cd <projektname>
--> Oder in anderen Worten: dort hin navigieren, wo die manage.py liegt, da diese im nächsten Schritt verwendet wird.

Den vServer starten:
$ py manage.py runserver

Hernach sollte im CLI der Link 'http://127.0.0.1:8000/' erscheinen.

HINWEISE:
--> Beim erstmaligen Starten kommt eine Meldung über nicht angewendete Migrationen, die vorerst ignoriert werden kann.
--> Der vServer kann mit Strg+c wieder abgeschaltet werden (da man ansonsten nichts in der Kommandozeile eingeben kann).


Eine App anlegen
================

ACHTUNG:
--> Auch hier darf das venv nicht aktiv sein!

Innerhalb des Projektverzeichnisses (da wo auch manage.py liegt) den Befehl ausführen:
$ py manage.py startapp <appname>

Damit wird ein neues Verzeichnis angelegt und gleichzeitig eine sqlite-Datenbank erstellt.