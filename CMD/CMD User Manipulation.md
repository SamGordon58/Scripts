## Add a user
net user {username} {password} /add

## Add to administrators group
net localgroup administrators {username} /add

## View local users
net user

## Delete a user account 
net user {username} /delete

## Activate User account 
net user {username} /active:yes
