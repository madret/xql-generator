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

    <p>- Set the path where the Windows event logs are located:</p>
    <p><input class="boks" type="text" id="path" value="C:\Windows\System32\winevt\Logs\Security.evtx" placeholder="C:\Windows\System32\winevt\Logs\Security.evtx"></p>

    <br/>

    <p>- Select Event ID:</p>
    		<select class="select" id="eventid">
		<option value="4625">4625 - An account failed to log on</option>
		<option value="4740">4740 - A user account was locked out</option>
		<option value="4771">4771 - Kerberos pre-authentication failed</option>
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
<code id="copy">Get-WinEvent -Path C:\.... -FilterXPath ..... and .... and .... </code>
</pre>
      
<!-- <a href="#" onclick="CopyToClipboard('copy');return false;">Copy To clipboard</a> -->

</body>

<p>Sloppy hobby project brought to you by:</p>
<a href="https://twitter.com/b41ss">@b41ss</a>	 
<p>Cheers!</p>
</html>
