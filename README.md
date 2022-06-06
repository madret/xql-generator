# Sysmon Powershell Generator
Generate Get-WinEvent cmdlet queries for Sysmon data. 

## Description
The command line is typically used over the Event Viewer GUI because it can allow for further granular control and filtering that the GUI does not offer.

But when you're not sure which query/filter options there are when searching through Sysmon data, use the generator to get you going.
Generating a valid Powershell query for command line usage.

## Output example:
`Get-WinEvent -Path C:\Path\to\Sysmon.evtx -FilterXPath '*/System/EventID=10 and */EventData/Data[@Name="TargetImage"] and */EventData/Data="C:\Windows\system32\lsass.exe"'`
