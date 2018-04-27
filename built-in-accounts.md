### Built-in Accounts notes

#### Check if Administrator and Guest accounts are enabled

```PowerShell
get-localuser administrator | Select Enabled -ExpandProperty Enabled
```

```PowerShell
get-localuser guest | Select Enabled -ExpandProperty Enabled
```

#### Disable local account

```PowerShell
Disable-LocalUser -Name "administrator"
```

```PowerShell
Disable-LocalUser -Name "guest"
```
