<h1>PowerShell</h1>
PowerShell Core v7.3.8

<h3>Autocomplete</h3>
Autocomplete works either with pressing <i>Tab</i> or <i>Ctrl + Space</i> to see a list of possible commands or options.

<h3>Finding commands</h3>

Filters for commands with 'time' in its noun
~~~
Get-Command -Noun *time*
~~~

Filters for commands with 'time' in its name
~~~
Get-Command -Name *time*
~~~

Filters for commands with "time" in noun and 'get' in verb
~~~
Get-Command -Noun *time* -Verb get
~~~

Works also with reversed options
~~~
Get-Command -Verb Set -Noun *time*
~~~

<h3>Pipes</h3>
Example:<br>

Filter and pipe the output from one Cmdlet as input to another and print as list:
~~~
Get-Service | Where-Object { $_.Status -eq "Running" } | Select-Object DisplayName, Status
~~~

