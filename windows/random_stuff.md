### Powershell
Get installed software on computer. Can be run remotely using `Invoke-Command`
```
Get-Package -ProviderName Programs -IncludeWindowsInstaller
```
```
Invoke-Command -ComputerName Server1 -ScriptBlock {Get-Package -ProviderName Programs -IncludeWindowsInstaller}
```
