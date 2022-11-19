<html>

<head>

	<h1 class="title"> Powershell cmdlet <span style="color: red;">generator</span>.</h1>
	<h1>To assist in hunting for the events that matter.</h1><hr/>
	
	<title> Cmdlet-Generator</title>
<style>
pre {
  border-style: inset;
  word-wrap:break-word;
  display:inline-block;
  margin: 0;
}
	
.block {
  display: block;
  width: 350px;
  border: none;
  background-color: #1E90FF;
  color: white;
  padding: 14px 28px;
  font-size: 16px;
  cursor: pointer;
  text-align: center;
}
	
.boks {
 font-size:large;
 border-radius: 10px;
 width:250px;
 height:22px;
	
	}
.select {
height:30px;
font-size:large;
	}	
	
</style>

    <script>

function myFunction() {
  document.getElementById("event_id").style.visibility = "hidden";
}
      
    // Here the value is stored in new variable x 
    function myFunction() {
        var x = document.getElementById("path").value;
        var y = document.getElementById("eventid").value;
        var z = document.getElementById("eventdata").value;
        var q = document.getElementById("eventname").value;
        document.getElementById("demo").innerHTML = "Get-WinEvent -LogName " + x + " -FilterXPath '*/System/EventID=" + y + " | Select-Object TimeCreated, Id, LevelDisplayName, ProcessId, Message | Format-Table -AutoSize";
    }
  
function CopyToClipboard(id)
{
var r = document.createRange();
r.selectNode(document.getElementById(id));
window.getSelection().removeAllRanges();
window.getSelection().addRange(r);
document.execCommand('copy');
window.getSelection().removeAllRanges();
}
</script>

</head>
<body>

    <p>- Select the log:</p>
    <p><input class="boks" type="text" id="path" value="'Security'" placeholder="'Security'"></p>

    <br/>

    <p>- Select Event ID:</p>
    		<select class="select" id="eventid">
		<option value="4625">4625 - An account failed to log on</option>
		<option value="4740">4740 - A user account was locked out</option>
		<option value="4771">4771 - Kerberos pre-authentication failed</option>
		</select>

	
    <br/>
    <br/>

    <p><button class="block" type="button" onclick="myFunction()"><b>Generate Powershell command</b></button></p>

    <br/>

<p> Output:</p>

<pre id="demo">
<code id="copy">Get-WinEvent -LogName C:\.... -FilterXPath ..... and .... and .... </code>
</pre>
      
<!-- <a href="#" onclick="CopyToClipboard('copy');return false;">Copy To clipboard</a> -->

</body>

<p>Sloppy hobby project brought to you by:</p>
<a href="https://twitter.com/b41ss">@b41ss</a>	 
<p>Cheers!</p>
</html>
