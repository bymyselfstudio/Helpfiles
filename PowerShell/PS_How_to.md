<h1>PowerShell</h1>
PowerShell Core v7.3.8<br><br>

<p>Auto complete works either with pressing <i>Tab</i> multiple times or <i>Ctrl + Space</i> to see a list of possible commands or options. To loop through possible options, a - (dash) is needed first.</p>

<h3>Useful commands</h3>

Get help for any command:
~~~
Get-Help name_of_command
~~~

List all help files:
~~ 
Get-Help *about*
~~~

Filters for anything containing "policy":
~~~
Get-Command *policy*
~~~

Filters for commands with 'time' in its noun:
~~~
Get-Command -Noun *time*
~~~

Filters for commands with 'time' in its name:
~~~
Get-Command -Name *time*
~~~

Filters for commands with "time" in noun and 'get' in verb:
~~~
Get-Command -Noun *time* -Verb get
~~~

Works also with reversed options:
~~~
Get-Command -Verb Set -Noun *time*
~~~

Shows all aliases:
~~~
Get-Alias
~~~

Tracking a session:
~~~
Start-Transcript
~~~

Stopping the tracking session:
~~~
Stop-Transcript
~~~

<h3>Pipes</h3>

Filter and pipe the output from one Cmdlet as input to another and print as list:
~~~
Get-Service | Where-Object { $_.Status -eq "Running" } | Select-Object DisplayName, Status
~~~

<h3>Create a log file</h3>

Create a textfile from output in the current directory:<br>
~~~
Get-Command -Verb Get -Noun *time* > .\name_of_file.txt
~~~

Append output in an existing textfile in the current directory:<br>
~~~
Get-Command -Verb Get -Noun *time* >> .\name_of_file.txt
~~~

<h3>Moving files</h3>

Move all excel files from current directory to another:<br>
~~~
Move-Item -Path .\*.xlsx -Destination C:\Temp
~~~
