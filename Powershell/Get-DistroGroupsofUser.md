```
Write-Host "connecting to O365..."
Connect-ExchangeOnline -UserPrincipalName {EMAIL} -DelegatedOrganization {DOMAIN}
Write-Host "connected"

$Username = "{USER EMAIL}" 

Write-Host "Searching Groups . . . "
$DistributionGroups= Get-DistributionGroup | where { (Get-DistributionGroupMember $_.Name | foreach {$_.PrimarySmtpAddress}) -contains "$Username"}

Write-Host "User is Present in: "
$DistributionGroups

```
