> [!NOTE]
> For installation processes open up PowerShell as administrator.

### General commands
Show help
~~~
choco -h
~~~

Show help to a specific command (e. g. list)
~~~
choco list -h
~~~

Show choco version
~~~
choco -v
~~~

Install Choco GUI
~~~
choco install chocolateygui
~~~

List already installed packages
~~~
choco list
~~~

Retrieve package info (e. g. Notepad++)
~~~
choco info notepadplusplus
~~~

Install new package (e. g. Notepad++)
~~~
choco install notepadplusplus
~~~

Install two packages at once
~~~
choco install notepadplusplus vlc
~~~

Search for a specific package
~~~
choco search *notepad*
~~~
or
~~~
choco find *notepad*
~~~

Upgrade all installed packages 
~~~
choco upgrade all
~~~

Upgrade a specific package (e. g. Notepad++)
~~~
choco upgrade notepadplusplus
~~~

Uninstall a specific package (e. g. Notepad++)
~~~
choco uninstall notepadplusplus
~~~
