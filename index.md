<html>

<head>

	<h1 class="title"> XQL query <span style="color: red;">generator</span>.</h1>
	<h1>To assist in hunting for the events that matter.</h1><hr/>
	
	<title>XQL-Query Generator</title>
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
        var x = document.getElementById("filter1").value;
        var y = document.getElementById("path").value;
        var z = document.getElementById("eventdata").value;
        var q = document.getElementById("eventname").value;
        document.getElementById("demo").innerHTML = "dataset = xdr_data " + x + "'" + y + "'" + ' | Select-Object TimeCreated, Id, LevelDisplayName, ProcessId, Message | Format-Table -AutoSize';
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
	
     <p>- Select filter:</p>
        <select class="select" id="filter1">
	<option value="| filter action_local_ip = ">Local IP address (connections from)</option>
	<option value="| filter action_remote_ip = ">Remote IP address (connections to)</option>
	<option value="| filter agent_hostname ">Device name (Workstation)</option>
	<option value="| filter actor_effective_username ">Username</option>
	<option value="| filter dst_action_external_hostname ">Hostname (example.com)</option>
	</select>

    <br/>
    <br/>

    <p>- Enter IP address or hostname:</p>
    <p><input class="boks" type="text" id="path" value="" placeholder="192.168."></p>

    <br/>
    <br/>
	
    <p>- Select mode:</p>
		<select class="select" id="eventdata" value="" placeholder="Empty">
	  	<option value="DestinationPort">Network mode</option>
		<option value="DestinationIp">Debug mode</option>
		<option value="DestinationHostname">BIOC mode</option>
		</select>

    <br/>
    <br/>
	
    <p>- Set the Name value for the choosen EventData:</p> 
    <p><b>For example:</b> Eventdata=DestinationPort <span style="color: red;">And</span> Name=4444 (standard MSF portnumber).</p>  
    <p><input type="text" class="boks" id="eventname" value="" placeholder="e.g. 4444"></p>
	
    <br/>

    <p><button class="block" type="button" onclick="myFunction()"><b>Generate XQL query</b></button></p>

    <br/>

<p> Output:</p>

<pre id="demo">
<code id="copy">dataset = xdr_data  | filter .... </code>
</pre>
      
<!-- <a href="#" onclick="CopyToClipboard('copy');return false;">Copy To clipboard</a> -->

</body>

<p>Sloppy hobby project brought to you by:</p>
<a href="https://twitter.com/b41ss">@b41ss</a>	 
<p>Cheers!</p>
</html>
