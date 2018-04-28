### Powershell notes

#### Retrieve Execution Policy

```PowerShell
Get-ExecutionPolicy
```

#### Set the Execution Policy (Allow scripts execution)

```PowerShell
Set-ExecutionPolicy RemoteSigned
```

```PowerShell
Set-ExecutionPolicy Unrestricted
```

#### Set the Execution Policy (Disable scripts execution)

```PowerShell
Set-ExecutionPolicy Restricted
```

#### Set the Execution Policy for myself

```PowerShell
Set-ExecutionPolicy -Scope "CurrentUser" -ExecutionPolicy "RemoteSigned"
```

```PowerShell
Set-ExecutionPolicy -Scope "CurrentUser" -ExecutionPolicy "Unrestricted"
```
