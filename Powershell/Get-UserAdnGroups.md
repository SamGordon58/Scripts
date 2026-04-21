```
$Groups = Get-ADGroup -Properties * -Filter * -SearchBase "{OU StRUCTURE}" 
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
