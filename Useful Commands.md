# Useful Commands

## Scans For Slowness
* `DISM /online /cleanup-image /checkhealth
* `DISM /Online /Cleanup-Image /ScanHealth
* `DISM /online /cleanup-image /restorehealth
* `SFC /Scannow
* 
## Get mac addresses:
  * get-ciminstance win32_networkadapterconfiguration | select description, macaddress | where {$_.MACAddress -ne $null }

## Check for VPN cert:
  * gci Cert:\LocalMachine\My

## Force VPN connection via Atera:
  * rasdial "MachineVPN"

##  Get list of admins:
  * Get-LocalGroupMember -Group "Administrators"

## AD Sync: ##
  * Start-ADSyncSyncCycle

## Logged in users: ##
  * query user

## Bitlocker get ID and push to AD: ##
  * manage-bde -protectors -get c:
  * manage-bde -protectors -adbackup c: -id "$ID"

## Connect Exchange Online: ##
  * Connect-ExchangeOnline -DelegatedOrganization {DOMAIN} -UserPrincipalName {EMAIL} -ShowProgress $true
  * Import-Module ExchangeOnlineManagement

## Connect AzureAD with Powershell ##
  * Connect-AzureAD -TenantID <id#>


## Monitor live connection (new VPN): ##
  * journalctl -f

## Check live connections (new VPN): ##
  * ipsec whack --trafficstatus

## DD commands: ##
  * dd if=/dev/sd* of=/mnt/* bs=4M status=progress oflag=sync conv=noerror,sync
  * To DD disk image to a zip file: dd if=/dev/sd* conv=sync,noerror bs=4M status=progress | gzip -c > /path/to/filename.gz

## Mounting NAS: 

``mount -t cifs -o username=<your username>,domain={DOMAIN},vers=1.0 / /{IP}/share /mnt/<Your mounted Folder>```

## Get ProductKey:
  * wmic path SoftwareLicensingService get OA3xOriginalProductKey

## Get wifi password from machine - open admin command prompt: ##
  * netsh wlan show profile (will list saved wifi networks)
  * netsh wlan show profile "Network Name" key=clear (password will be listed as Key Content under Security Settings)

Not a command - but useful.  
When you have TPM error with Outlook the folder to rename is:
  * C:\users\$dir\AppData\Local\Packages\Microsoft.AAD.BrokerPlugin_cw5n1h2txyewy

## Get external IP from Linux CLI ##
  * curl https://ident.me
    * curl https://Icanhazip.com 

## Make sure libreswan is active ##
  * systemctl status ipsec.service

## List applied firwall rules ##
  * nft list ruleset

## See what mailboxes a user has delegate access on ##
  *  Get-Mailbox -ResultSize Unlimited | Get-MailboxPermission -User {USER EMAIL} | Format-Table Identity, AccessRights, Denyc

## See Powershell Modules Installed ##
Get-Module -ListAvailable

## Create and/or update external contacts - Exchange Online 
  * Create:

Import-Csv .\test.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
 
  * Update: 

Import-Csv .\test.csv|%{Set-Contact -Identity $_.Name -Phone $_.Phone -Company $_.Company}

## Fix Atera 

<code>
reg delete "HKEY_LOCAL_MACHINE\SOFTWARE\ATERA Networks\AlphaAgent" /v AccountId /f
reg delete "HKEY_LOCAL_MACHINE\SOFTWARE\ATERA Networks\AlphaAgent" /v AgentId /f
sc stop ateraagent && sc start ateraagent
</code>

##= Mikrotik Caps Man ##=
   * /ip neighbor print
   * /caps-man remote-cap print
Either of the above will show if an AP is linked.

##= List users and date of last password change ##=
<code>Get-ADUser -SearchBase "{OU STRUCT}" -filter * -properties PwdLastSet | sort Name | ft Name,@{Name='PwdLastSet';Expression={[DateTime]::FromFileTime($_.PwdLastSet)}}</code>


##= Users for password reset links ##=

<code>Get-ADUser -SearchBase "{OU STRUCT}" -filter * | select UserPrincipalName</code>


##= String for graph api ##=

<code> https://graph.microsoft.com/v1.0/users/<emailaddress>?$select=onPremisesImmutableId </code>


##= Dynamic SSO Group Rule/Query ##=
<code> (user.onPremisesDistinguishedName -contains "EmployeeAccounts") </code>
