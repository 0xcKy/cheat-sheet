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
