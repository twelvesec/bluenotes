### Users notes

#### Check registry value

```PowerShell
$val = Get-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System" | Select-Object -ExpandProperty "NoConnectedUser" -ErrorAction Stop
if($val -eq $Value){
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

#### Read password from file (securestring)

```PowerShell
$password = Get-Content $filename | ConvertTo-SecureString
```

#### Read password from file (plaintext)

```PowerShell
$password = Get-Content $filename | ConvertTo-SecureString
$plaintext = (New-Object PSCredential "user", $password).GetNetworkCredential().Password
```

#### Check if local user exists

```PowerShell
if ((Get-LocalUser -Name "admin01" -ErrorAction Ignore).Count -eq 1) {
    Return $True
}
else {
    Return $False
}
```
