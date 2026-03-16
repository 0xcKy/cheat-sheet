### Powershell
Get installed software on computer. Can be run remotely using `Invoke-Command`
```
Get-Package -ProviderName Programs -IncludeWindowsInstaller
```
```
Invoke-Command -ComputerName Server1 -ScriptBlock {Get-Package -ProviderName Programs -IncludeWindowsInstaller}
```
Show current processes with PID and PPID

```
Get-CimInstance Win32_Process | Select-Object Name, ProcessId, ParentProcessId
```
ICMP scan using Test-NetConnection, returning active (True) connections only
```
$hosts = @("HOST01", "HOST02") #array of computers to test
foreach ($i in $hosts) {$temp = Test-NetConnection -ComputerName $i -InformationLevel Quiet -WarningAction SilentlyContinue; if ($temp){echo "[+] $i connection is active ($temp) [+]"}}
```
Remotely connect to C$
```
$cred = Get-Credential #optional because param -Credential can be used without a variable
$psDrive = New-PSDrive -Name MyRemoteDrive -PSProvider FileSystem -Root '\\PC_NAME\C$' -Credential $cred
Remove-PSDrive -Name MyRemoteDrive #use to disconnect
```
