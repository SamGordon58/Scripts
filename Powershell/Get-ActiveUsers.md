get-ADUser -Filter '*' -SearchBase {"OU=EmployeeAccounts,OU=UserAccounts,OU=OUs,DC={company},DC=com"} | select "Name" | Export-CSV "{File Location}"
