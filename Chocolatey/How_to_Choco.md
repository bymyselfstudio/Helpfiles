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

List already installed packages
~~~
choco list
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

Upgrade locally installed chocolatey packages
~~~
choco upgrade all
~~~
