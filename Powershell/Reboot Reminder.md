```
$wshell = New-Object -ComObject Wscript.Shell
[System.Media.SystemSounds]::Hand.Play()

#[console]::Beep(600,1100)
$Output = $wshell.Popup("Dont forget to reboot today!", 0, "Reboot Reminder", 48+0)
```
