```
Write-Host "connecting to O365..."
Connect-ExchangeOnline -UserPrincipalName sam.gordon@cyburity.com -DelegatedOrganization trivector.us
Write-Host "connected"

$Username = "Steve.Jefferys@AppliedITServices.com" 

Write-Host "Searching Groups . . . "
$DistributionGroups= Get-DistributionGroup | where { (Get-DistributionGroupMember $_.Name | foreach {$_.PrimarySmtpAddress}) -contains "$Username"}

Write-Host "User is Present in: "
$DistributionGroups

```