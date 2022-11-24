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
  background-color: #00ff99;
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
  document.getElementById("unit").style.visibility = "hidden";
}
      
    // Here the value is stored in new variable x 
    function myFunction() {
        var x = document.getElementById("filter1").value;
        var y = document.getElementById("path").value;
        var z = document.getElementById("unit").value;
        document.getElementById("demo").innerHTML = "dataset = xdr_data " + x + "'" + y + "'" + z;}
  
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

    <p>- Enter IP address or hostname:</p>
    <p><input class="boks" type="text" id="path" value="" placeholder="192.168..."></p>

    <br/>

    <p>- Select Event ID:</p>
    		<select class="select" id="eventid">
	  	<option value="| fields _time, agent_ip_addresses, agent_hostname, actor_effective_username, action_local_ip, action_local_port, action_remote_ip, action_remote_port, actor_process_image_name, actor_process_command_line, actor_process_os_pid, actor_process_signature_status, agent_os_type">Network mode</option>
		<option value="| fields _time, agent_ip_addresses, actor_process_image_name, actor_process_command_line, actor_process_os_pid, actor_process_signature_status, agent_hostname, actor_effective_username, action_local_ip, action_local_port, action_remote_ip, action_remote_port, agent_os_type">Debug mode</option>
		</select>

	
    <br/>
    <br/>

    <p><button class="block" type="button" onclick="myFunction()"><b>Generate XQL command</b></button></p>

    <br/>

<p> Output:</p>

<pre id="demo">
<code id="copy">Get-WinEvent -LogName 'Security' -FilterXPath ..... and .... and .... </code>
</pre>
      
<!-- <a href="#" onclick="CopyToClipboard('copy');return false;">Copy To clipboard</a> -->

</body>

<p>Sloppy hobby project brought to you by:</p>
<a href="https://twitter.com/b41ss">@b41ss</a>	 
<p>Cheers!</p>
</html>
