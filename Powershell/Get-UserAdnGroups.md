```
$Groups = Get-ADGroup -Properties * -Filter * -SearchBase "OU=Groups,OU=OUs,DC=resolutionllc,DC=biz" 
$Results = foreach( $Group in $Groups ){

 Get-ADGroupMember -Identity $Group | foreach {

        [pscustomobject]@{

            GroupName = $Group.Name

            Name = $_.Name

            }

        }

    }

$Results | Export-Csv -Path .\Groups_Users.csv -NoTypeInformation
```
