<html>

<head>

<h1 class="title"> Powershell cmdlet <span style="color: red;">generator</span>. To assist in hunting through Sysmon event logs.</h1>
<hr/>
	
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
  width: 300px;
  border: none;
  background-color: #1E90FF;
  color: white;
  padding: 14px 28px;
  font-size: 16px;
  cursor: pointer;
  text-align: center;
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
        document.getElementById("demo").innerHTML = "Get-WinEvent -Path " + x + " -FilterXPath '*/System/EventID=" + y + ' and */EventData/Data[@Name="' + z +'"] and */EventData/Data=' + q + "'";
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

    <p>- Set the path where the Sysmon eventlog is located:</p>
    <p><input type="text" id="path" value="" placeholder="C:\path\to\<logfile>.evtx"></p>

	<br/>

    <p>- Select Event ID:</p>
    		<select class="select" id="eventid">
		<option value="1">1 - Process Creation</option>
		<option value="3">3 - Network connection detected</option>
		<option value="7">7 - Image loaded</option>
		<option value="8">8 - CreateRemoteThread detected</option>
		<option value="10">10 - Process access</option>	
		<option value="11">11 - File created</option>
		<option value="12">12 - Registry object added/deleted</option>
		<option value="13">13- Registry value set</option>
		<option value="14">14 - RegObject renamed</option>	
		<option value="15">15 - File stream created</option>
		<option value="22">22 - DNS query</option>
		</select>

	<br/>
    	<br/>
    <p>- Select EventData:</p>
		<select class="select" id="eventdata">
		<option value="CommandLine">CommandLine</option>
		<option value="Company">Company</option>
		<option value="CreationUtcTime">CreationUtcTime</option>
		<option value="CurrentDirectory">CurrentDirectory</option>
		<option value="Description">Description</option>
		<option value="DestinationHostname">DestinationHostname</option>
		<option value="DestinationIp">DestinationIp</option>
		<option value="DestinationPort">DestinationPort</option>
		<option value="HostUrl">HostUrl</option>
		<option value="Image">Image</option>
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
		<option value="SourceHostname">SourceHostname</option>
		<option value="SourceImage">SourceImage</option>
		<option value="SourceIp">SourceIp</option>
		<option value="SourcePort">SourcePort</option>
		<option value="StartModule">StartModule</option>
		<option value="TargetFileName">TargetFileName</option>
		<option value="TargetImage">TargetImage</option>
		<option value="TargetObject">TargetObject</option>
		<option value="TargetProcessId">TargetProcessId</option>
		<option value="User">User</option>
		<option value="UtcTime">UtcTime</option>
		</select>

	<br/>
	<br/>
    <p>- Set the Name value for the choosen EventData:</p> 
    <p><b>For example:</b> <span style="color: red;">If</span> the selected Eventdata=DestinationPort <span style="color: red;">Then</span> Name=4444 (standard MSF portnumber).</p>  
    <p><input type="text" id="eventname" value="" placeholder="e.g. 4444"></p>
	
	<br/>

	<p><button class="block" type="button" onclick="myFunction()"><b>Generate Powershell command</b></button></p>

	<br/>

<p> Output:</p>

<pre id="demo">
<code id="copy">Get-WinEvent -Path C:\.... -FilterXPath ..... and .... and .... </code>
</pre>
      
<!-- <a href="#" onclick="CopyToClipboard('copy');return false;">Copy To clipboard</a> -->

</body>

<p>This sloppy hobby project is brought to you by:</p>
<a href="https://twitter.com/b41ss">@b41ss</a>	 
<p>Cheers!</p>
</html>
