Work in progress

<style>
    .comment {
        color: lightgreen;
    }

    .cmd {
        color: orange;
    }

    .dollar_ {
        color: cyan;
    }

    .else {
        color: white;
    }

    .curly_b {
        color: yellow;
    }

    .round_b {
        color: blue;
    }

    .state {
        color: blue;
    }
</style>

# Hands on PowerShell
PowerShell Core v7.3.8

## Content:
<a href="#autocomplete">Auto Complete</a><br>
<a href="#pipes">Pipes</a>


<h2 id="autocomplete">Auto Complete</h2>
Ctrl + space or tab tab ...

<h2 id="pipes">Pipes</h2>
<h3>Example:</h3>
<pre>
<span class="comment"># Piping the output from one Cmdlet as input to another and print as list</span>
<span class="cmd">Get-Service</span> <span class="else">|</span> <span class="cmd">Where-Object</span> <span class="curly_b">{</span> <span class="dollar_">$_</span><span class="else">.</span><span class="cmd">Status</span> <span class="else">-eq</span> <span class="state">"Running"</span> <span class="curly_b">}</span> <span class="else">|</span> <span class="cmd">Select-Object</span> <span class="else">DisplayName, Status</span>
</pre>
