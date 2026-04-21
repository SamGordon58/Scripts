```
 Get-Mailbox -ResultSize Unlimited | Get-MailboxPermission -User j.lutz@marinfed.com | Format-Table Identity, AccessRights, Denyc
```