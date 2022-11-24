<html>

<head>

	<h1 class="title"> XQL query <span style="color: red;">generator</span>.</h1>
	<h1>To assist in hunting for events that matter.</h1><hr/>
	
	<title> XQL-Generator</title>
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
  background-color: #00FF99;
  color: black;
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
        document.getElementById("demo").innerHTML = "Get-WinEvent -LogName " + x + " -FilterXPath '*/System/EventID=" + y;
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
    <p>- Select EventData:</p>
		<select class="select" id="eventdata">
		<optgroup label="Frequently used:">
	  	<option value="DestinationPort">DestinationPort</option>
		<option value="DestinationIp">DestinationIp</option>
		<option value="DestinationHostname">DestinationHostname</option>
		<option value="Image">Image</option>
		<option value="SourcePort">SourcePort</option>
		<option value="SourceIp">SourceIp</option>
		<option value="SourceHostname">SourceHostname</option>
		<option value="SourceImage">SourceImage</option>
		<option value="TargetImage">TargetImage</option>
		<option value="TargetFileName">TargetFileName</option>
		</optgroup>
		<optgroup label="More:">
		<option value="CommandLine">CommandLine</option>
		<option value="Company">Company</option>
		<option value="CreationUtcTime">CreationUtcTime</option>
		<option value="CurrentDirectory">CurrentDirectory</option>
		<option value="Description">Description</option>
		<option value="HostUrl">HostUrl</option>
		<option value="ImageLoaded">ImageLoaded</option>
		<option value="Integrity Level">IntegrityLevel</option>
		<option value="OriginalFileName">OriginalFileName</option>
		<option value="ParentCommandLine">ParentCommandLine</option>
		<option value="ParentImage">ParentImage</option>
		<option value="ProcessId">ProcessId</option>
		<option value="QueryName">QueryName</option>
		<option value="QueryResults">QueryResults</option>
		<option value="QueryStatus">QueryStatus</option>
		<option value="Signature">Signature</option>
		<option value="Signed">Signed</option>
		<option value="StartModule">StartModule</option>
		<option value="TargetObject">TargetObject</option>
		<option value="TargetProcessId">TargetProcessId</option>
		<option value="User">User</option>
		<option value="UtcTime">UtcTime</option>
		</optgroup>
		</select>

    <br/>
    <br/>
	
    <p>- Set the Name value for the choosen EventData:</p> 
    <p><b>For example:</b> Eventdata=DestinationPort <span style="color: red;">And</span> Name=4444 (standard MSF portnumber).</p>  
    <p><input type="text" class="boks" id="eventname" value="" placeholder="e.g. 4444"></p>
	
    <br/>

    <p><button class="block" type="button" onclick="myFunction()"><b>Generate Powershell command</b></button></p>

    <br/>

<p> Output:</p>

<pre id="demo">
<code id="copy">... </code>
</pre>
      
<!-- <a href="#" onclick="CopyToClipboard('copy');return false;">Copy To clipboard</a> -->

</body>

<p>Sloppy hobby project brought to you by:</p>
<a href="https://twitter.com/b41ss">@b41ss</a>	 
<p>Cheers!</p>
</html>
