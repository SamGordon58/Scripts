```
Get-ADComputer -filter * -Properties name, description, created, lastLogon | select name, description, created, @{N='LastLogon'; E={[DateTime]::FromFileTime($_.LastLogon)}} | Export-Csv -path {Filepath}
```