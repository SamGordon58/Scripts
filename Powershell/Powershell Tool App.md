```
Write-Host "Welcome . . . "
Write-Host "Select an option below: . . ."



# ~~~~ Testing Calls ~~~~~
#Testing SHutdownInfo Call
ShutdwonInfo
getUsers
GetUserandGroups
setDomain


#Option Menu
function OptionsMenu
{
    While ($selection -ne 0)
    {
    Write-Host " 1. Set Domain "
    Write-Host " 2. Get Users "
    Write-Host " 3. Get Groups "
    Write-Host " 4. Get Users and Groups "
    Write-Host " 5. Get Shutdown Info "
    Write-Host " 0. Quit "
    $selection = Read-Host "Enter option "
    
    switch ($selection)
    {
        switch()
    }
    }
}


# ~~~~ Functions ~~~~
#Function for setting Domain
function setDomain
{ 
    Write-Host " 1. Testing Set Domain. . ."

    #Pulled from Wes's script
#    $dc = $domainName.Split('.')[0]
   #$domainMain = $domainName.Split('.')[1]
  #  $domainSuffix = $domainName.Split('.')[2]
   # $netbiosName = $domainMain.ToUpper()

}

function getDomain
{ 
    Write-Host "Testing get Domain . . . "
    Write-Host " $domainMain "
}

# Get Shutdown event logs for trouble shooting shutdowns.
function ShutdwonInfo
{
    # Function Test
    write-Host "5. Testing Get-ShutdownInfo Function . . ."
    #Get-WinEvent -FilterHashtable @{ LogName = 'System'; Id = 41, 1074, 6006, 6605, 6008; } | Format-List Id, LevelDisplayName, TimeCreated, Message
}

function getUsers
{ 
    # Testing Function
    Write-Host "2. Testing Get User Function . . ."

}
#Function for getting User and Groups
function GetUserandGroups 
{
    #Test for GetUserAndGroups
    Write-Host "4. Testing Get User and Groups"
    

    <# $Groups = Get-ADGroup -Properties * -Filter * -SearchBase "OU=Groups,OU=OUs,DC=resolutionllc,DC=biz" 
    $Results = foreach( $Group in $Groups ){

 Get-ADGroupMember -Identity $Group | ForEach-Object {

        [pscustomobject]@{

            GroupName = $Group.Name

            Name = $_.Name

            }

        }

    }

$Results | Export-Csv -Path .\Groups_Users.csv -NoTypeInformation #>

}
```