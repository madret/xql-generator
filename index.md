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
  background-color: #00ff99;
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
  document.getElementById("unit").style.visibility = "hidden";
}
      
    // Here the value is stored in new variable x 
    function myFunction() {
        var x = document.getElementById("filter1").value;
        var y = document.getElementById("path").value;
        var z = document.getElementById("unit").value;
        document.getElementById("demo").innerHTML = "dataset = xdr_data " + x + "'" + y + "'" + z;}
  
function CopyToClipboard(id)
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
	
    <p>- Select Event ID:</p>
    		<select class="select" id="filter1">
		<option value="4625">4625 - An account failed to log on</option>
		<option value="4740">4740 - A user account was locked out</option>
		<option value="4771">4771 - Kerberos pre-authentication failed</option>
		</select>

    <br/>
    <br/>
    <br/>

    <p>- Enter IP address or hostname:</p>
    <p><input class="boks" type="text" id="path" value="" placeholder="192.168."></p>

    <br/>
    <br/>
	
    <p>- Select mode:</p>
		<select class="select" id="unit">
	  	<option value="| fields _time, agent_ip_addresses, agent_hostname, actor_effective_username, action_local_ip, action_local_port, action_remote_ip, action_remote_port, actor_process_image_name, actor_process_command_line, actor_process_os_pid, actor_process_signature_status, agent_os_type">Network mode</option>
		<option value="| fields _time, agent_ip_addresses, actor_process_image_name, actor_process_command_line, actor_process_os_pid, actor_process_signature_status, agent_hostname, actor_effective_username, action_local_ip, action_local_port, action_remote_ip, action_remote_port, agent_os_type">Debug mode</option>
		</select>
	
    <br/>

    <p><button class="block" type="button" onclick="myFunction()"><b>Generate XQL query</b></button></p>

    <br/>

<p> Output:</p>

<pre id="demo">
<code id="copy">Results..</code>
</pre>
      
<!-- <a href="#" onclick="CopyToClipboard('copy');return false;">Copy To clipboard</a> -->

</body>

<p>Sloppy hobby project brought to you by:</p>
<a href="https://twitter.com/b41ss">@b41ss</a>	 
<p>Cheers!</p>
</html>
