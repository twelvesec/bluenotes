### Users notes

#### Get user account

```PowerShell
Get-LocalUser -Name "Administrator"
```

#### Store password in file

```PowerShell
"123myP@$$w0rd@$" | ConvertTo-SecureString -AsPlainText -Force | ConvertFrom-SecureString | Out-File $filename
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
$user = Get-LocalUser -Name "admin01" -ErrorAction SilentlyContinue

if (!$user) {
    # ....
}
else {
    # ....
}
```
