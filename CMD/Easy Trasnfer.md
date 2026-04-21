```
set SRC=
set DST=

robocopy /e /mir /xj /R:0 /W:0 "%SRC%\Contacts"  "%DST%\Contacts" 
robocopy /e /mir /xj /R:0 /W:0 "%SRC%\Desktop"  "%DST%\Desktop" 
robocopy /e /mir /xj /R:0 /W:0 "%SRC%\Downloads"  "%DST%\Downloads" 
robocopy /e /mir /xj /R:0 /W:0 "%SRC%\Documents" "%DST%\Documents" 
robocopy /e /mir /xj /R:0 /W:0 "%SRC%\Pictures" "%DST%\Pictures"
robocopy /e /mir /xj /R:0 /W:0 "%SRC%\Favorites" "%DST%\Favorites"
robocopy /e /mir /xj /R:0 /W:0 "%SRC%\AppData\Local\Microsoft\Outlook" "%DST%\AppData\Local\Microsoft\Outlook"
echo "Transfer Complete"


```