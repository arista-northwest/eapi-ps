PsEapi
======

Usage
-----


### New-EapiConnection

```powershell
New-EapiConnection [-HostName] <string> [[-Protocol] <string>] [[-UserName] <string>] [[-Password] <string>] [<CommonParameters>]
```

### Invoke-EapiCommands

```powershell
Invoke-EapiCommands [-Commands] <string[]> -Connection <Object> [-Encoding <string>] [<CommonParameters>]
```

### Show-EapiHardwareCapacity

```powershell
Show-EapiHardwareCapacity [-Connection] <Object>  [<CommonParameters>]
```

Example
-------

```powershell
Import-Module -Force PsEapi.psm1
New-EapiConnection -HostName yo631 |
  Show-EapiHardwareCapacity |
  Select-Object -ExpandProperty tables |
  Where-Object {$_.usedPercent -gt 0}
highWatermark : 21
used          : 21
usedPercent   : 2
committed     : 0
table         : ECMP
chip          :
maxLimit      : 1023
feature       : Routing
free          : 1002

highWatermark : 646
used          : 633
usedPercent   : 1
committed     : 0
table         : FEC
chip          :
maxLimit      : 31744
feature       : Routing
free          : 31111

highWatermark : 21
used          : 21
usedPercent   : 2
committed     : 0
table         : ECMP
chip          :
maxLimit      : 1023
feature       :
free          : 1002

highWatermark : 646
used          : 633
usedPercent   : 1
committed     : 0
table         : FEC
chip          :
maxLimit      : 31744
feature       :
free          : 31111

highWatermark : 262
used          : 255
usedPercent   : 2
committed     : 1024
table         : TCAM
chip          :
maxLimit      : 12288
feature       : IPv6
free          : 9985
```
