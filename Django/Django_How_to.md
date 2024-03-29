<h1>Django</h1>

> [!NOTE]
> Voraussetzung ist eine Python-Installation, (PATH aktivieren!).<br>
> Siehe auch https://www.python.org/downloads/

<h2>Django installieren (innerhalb des venv)</h2>

~~~
python -m pip install Django
~~~
oder
~~~
py -3 -m pip install Django
~~~

--> Gilt in diesem Fall für Python 3, was man an py -3 erkennen kann<br>
--> Siehe auch <a href="https://stackoverflow.com/questions/45137395/how-do-i-upgrade-the-python-installation-in-windows-10">Upgrade python installation in win 10</a>

Wozu die -m flag?<br>
--> https://www.datasciencebyexample.com/2023/02/08/different-ways-to-install-python-packages-with-pip/

Die Installation von weiteren Modulen kann automatisiert über <i>requirements.txt</i> stattfinden Das venv sollte hierbei aktiviert sein:<br>
~~~
pip install -r requirements.txt
~~~

Was bedeutet '-r'?<br>
https://stackoverflow.com/questions/38066631/what-does-r-do-in-pip-install-r-requirements-txt

Django-Projekt erstellen (nicht den Punkt am Ende vergessen, damit das Projekt im gleichen Verzeichnis angelegt wird!)
~~~
django-admin startproject <projekt_name> . 
~~~

<h2>Virtuellen Server starten</h2>

<strong>ACHTUNG</strong>:<br>
--> Um den vServer zu starten, muss man erst ein Projekt erstellt haben, damit die manage.py da ist!<br>
--> Zudem darf das venv nicht aktiv sein!

Zum äußeren Projektverzeichnis navigieren (es gibt zwei Verzeichnisse mit dem gleichen Namen, ein äußeres und ein inneres):
~~~
cd <projektname>
~~~
--> Oder in anderen Worten: dort hin navigieren, wo die manage.py liegt, da diese im nächsten Schritt verwendet wird.

Den vServer starten:
~~~
py manage.py runserver
~~~
Hernach sollte im CLI der Link 'http: //127.0.0.1:8000/' erscheinen (ohne Leerzeichen).

HINWEISE:
--> Beim erstmaligen Starten kommt eine Meldung über nicht angewendete Migrationen, die vorerst ignoriert werden kann.<br>
--> Der vServer kann mit Strg+c wieder abgeschaltet werden (da man ansonsten nichts in der Kommandozeile eingeben kann).


<h2>Eine App anlegen</h2>

> [!NOTE] 
> Auch hier darf das venv nicht aktiv sein!

Innerhalb des Projektverzeichnisses (da wo auch manage.py liegt) den Befehl ausführen:
~~~
py manage.py startapp <appname>
~~~

Damit wird ein neues Verzeichnis angelegt und gleichzeitig eine sqlite-Datenbank erstellt.
