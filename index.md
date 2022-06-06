<html>

<script>
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
	
<body>

<section class="hero">
  <div class="hero-body">
    <div class="container">
      <h1 class="title">
        Sysmon query <span style="color: red;">generator</span> for Powershell.
      </h1>
	<hr/>

<p> Set the path where the Sysmon eventlog is located:</p>
-Path:
<div class="field">
  <div class="control">
    <input class="input is-small" type="text" name="host" placeholder="C:\path\to\<logname>.evtx">
  </div>
</div>

	<br/>
	<br/>
	<br/>

      <h2 class="subtitle"></h2>
		<form action="generate.php" method="post" id="query">
		<p>Select Event ID:</p>
		<div class="select">
		<select class="" id="platform" name="platform">
		<option option="1">1 - Process Create</option>
		<option option="3">3 - Network connection detected</option>
		<option option="7">7 - Image loaded</option>
		<option option="8">8 - CreateRemoteThread detected</option>
		<option option="10">10 - Process access</option>	
		<option option="11">11 - File created</option>
		<option option="12">12 - Registry object added/deleted</option>
		<option option="13">13- Registry value set</option>
		<option option="14">14 - RegObject renamed</option>	
		<option option="15">15 - File stream created</option>
		<option option="22">22 - DNS query</option>
		</select>
		</div>
	<br/>
	<br/>
	<br/>
		<p>Select EventData:</p>
		<div class="select">
		<select class="" id="action" name="action">
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
		</div>

	<br/>
	<br/>
	<br/>

<p> <b>Optional:</b> Set the value for the choosen EventData (e.g DestinationPort):</p>

		EventData Name:
<div class="field">
  <div class="control">
    <input class="input is-small" type="text" name="port" placeholder="e.g. 4444">
  </div>
</div>

<br/>
<br/>

<p> Output example:</p>
<pre>
  <code id="copy">
Get-WinEvent -Path C:\Windows\System32\winevt\Logs\Microsoft-Windows-Sysmon%4Operational.evtx 
-FilterXPath '*/System/EventID=3 and */EventData/Data[@Name="DestinationPort"] and */EventData/Data=4444
  </code>
<a href="#" onclick="CopyToClipboard('copy');return false;">Copy To clipboard</a>  
</pre>

	<br/>
	<br/>

	<input type="submit" class="button is-success" value="Generate query">
	</form>

<br/>
<br/>

<div class="container has-text-centered">

<p>Thanks for using the generator.</p>

<a href="https://twitter.com/b41ss">@b41ss</a> 
			</div>
    </div>
  </div>
</section>
</body>
</html>
