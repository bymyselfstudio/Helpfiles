<h1>PowerShell</h1>
PowerShell Core v7.3.8

<h3>Autocomplete</h3>
Autocomplete works either with pressing tab or <pre>Ctrl + Space</pre> to see a list of possible commands or options.

<h3>Finding commands</h3>
Filters for commands with 'time' in its noun
<pre>
Get-Command -Noun *time*
</pre>

Filters for commands with 'time' in its name
<pre>
Get-Command -Name *time*
</pre>

Filters for commands with "time" in noun and 'get' in verb
<pre>
Get-Command -Noun *time* -Verb get
</pre>

Works also with reversed options
<pre>
Get-Command -Verb Set -Noun *time*
</pre>

<h3>Pipes</h3>
Example:<br>
Filter and pipe the output from one Cmdlet as input to another and print as list:
<pre>
Get-Service | Where-Object { $_.Status -eq "Running" } | Select-Object DisplayName, Status
</pre>

