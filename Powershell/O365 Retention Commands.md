# Get Mailbox Property
```
Get-Mailbox -Identity "" | Select-Object -Property "Archive*"
```
# Force a Sync to the Archive
```
Start-ManagedFolderAssistant -Identity "{User}"
```