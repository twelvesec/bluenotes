### Built-in Accounts notes

#### Check if Administrator and Guest accounts are enabled

```PowerShell
get-localuser administrator | Select Enabled -ExpandProperty Enabled
```

```PowerShell
get-localuser guest | Select Enabled -ExpandProperty Enabled
```

#### Change built-in account password

```PowerShell
Get-LocalUser -Name "Administrator" | Set-LocalUser -Password "newpassword"
```

```PowerShell
Get-LocalUser -Name "Administrator" | Set-LocalUser -Password "newpassword" -AccountNeverExpires -PasswordNeverExpires
```

#### Disable local account

```PowerShell
Disable-LocalUser -Name "administrator"
```

```PowerShell
Disable-LocalUser -Name "guest"
```

#### Find default local admin account (known SID)

```PowerShell
Get-WmiObject Win32_useraccount | Where-Object {$_.SID -like 'S-1-5-21-*-500'}
```

#### Rename a local account

```PowerShell
Rename-LocalUser -Name "Administrator" -NewName "user1"
```

#### Change local account description

```PowerShell
Set-LocalUser -Name "Administrator" -Description "temporary account."
```

#### Create new local account

```PowerShell
New-LocalUser -Password "mypassw0rd" -Name "manager" -Description "Temporary account for testing purposes."
```

```PowerShell
New-LocalUser -Password "mypassw0rd" -Name "manager" -Description "Temporary account for testing purposes." -AccountNeverExpires -PasswordNeverExpires
```

#### Add user to Groups

```PowerShell
Add-LocalGroupMember -Group "Administrators", "Power Users", "Remote Desktop Users", "Users" -Member "manager"
```
