### Users notes

#### Check registry value

```PowerShell
$val = Get-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System" | Select-Object -ExpandProperty "NoConnectedUser" -ErrorAction Stop
if($val -eq 3){
    return $true
}
else {
    return $false
}
```

#### Add/Edit registry value

```PowerShell
if(!(Test-Path "HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System"))
{
    New-Item -Path "HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System" -Force | Out-Null

    New-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System" -Name "NoConnectedUser" -Value 3 `
    -PropertyType DWORD -Force | Out-Null
}
```
