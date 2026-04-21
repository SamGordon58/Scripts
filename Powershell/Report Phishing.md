```
# Connect to Exchange Online
$UserCredential = Get-Credential
$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri http://outlook.office365.com/powershell-liveid/ -Authentication Basic -Credential $UserCredential -AllowRedirection
Import-PSSession $Session -DisableNameChecking

# Get the phishing email's MessageId
$PhishingEmailMessageId = "<MessageId of the phishing email>"  # You need to replace this with the actual MessageId

# Report the phishing email
Submit-PhishMessage -MessageId $PhishingEmailMessageId -Recipient user@example.com -Sender phish@example.com -ReportedBy user@example.com -SubmissionDateTime (Get-Date)

# Disconnect from Exchange Online
Remove-PSSession $Session
```

# 2
```
# Connect to Exchange Online
$UserCredential = Get-Credential
$Session = New-PSSession

Import-PSSession $Session -DisableNameChecking

$reporter = Read-Host "What is your email?"
$recipient = Read-Host "Who was the Recipient?"
$sender = Read-Host "Who was the Sender?"
$EmailID = Read-Host "Enter the Email ID."

# Report the phishing email
#Submit-PhishMessage -MessageId $MessageId -Recipient $User -Sender phish@example.com -ReportedBy $User -SubmissionDateTime (Get-Date)

# Disconnect from Exchange Online
Remove-PSSession $Session



#Original Code from ChatGPT
# Connect to Exchange Online
#$UserCredential = Get-Credential
#$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri http://outlook.office365.com/powershell-liveid/ -Authentication Basic -Credential $UserCredential #-#AllowRedirection
#Import-PSSession $Session -DisableNameChecking

# Get the phishing email's MessageId
$PhishingEmailMessageId = "<MessageId of the phishing email>"  # You need to replace this with the actual MessageId

# Report the phishing email
#Submit-PhishMessage -MessageId $PhishingEmailMessageId -Recipient user@example.com -Sender phish@example.com -ReportedBy user@example.com -SubmissionDateTime (Get-Date)

# Disconnect from Exchange Online
#Remove-PSSession $Session

```