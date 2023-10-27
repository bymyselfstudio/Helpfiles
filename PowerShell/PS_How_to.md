Work in progress


# PowerShell
PowerShell Core v7.3.8

<details>
<summary>Overview</summary>
<a href="#autocomplete">Autocomplete</a><br>
<a href="#pipes">Pipes</a>
</details>

<h2 id="autocomplete">Autocomplete</h2>
Ctrl + space or tab tab ...

<h2 id="pipes">Pipes</h2>
<h3>Example:</h3>
Piping the output from one Cmdlet as input to another and print as list:
<pre>
Get-Service | Where-Object { $_.Status -eq "Running" } | Select-Object DisplayName, Status
</pre>

