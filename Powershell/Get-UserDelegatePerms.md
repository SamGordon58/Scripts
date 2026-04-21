
 Get-Mailbox -ResultSize Unlimited | Get-MailboxPermission -User {EMAIL} | Format-Table Identity, AccessRights, Denyc
