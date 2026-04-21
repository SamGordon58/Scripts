```
 msiexec /x {EFB51F01-9805-4293-BB16-6F17EF4CEDF2} /qn

timeout /t 5 /nobreak >nul

sc stop AteraAgent > nul 2> nul 
sc delete AteraAgent > nul 2> nul

taskkill /f /im TicketingTray.exe > nul 2> nul

REG DELETE “HKEY_CURRENT_USER\Software\ATERA Networks” /f > nul 2> nul

RMDIR /S /Q “%userprofile%\appdata\local\temp\TrayIconCaching” > nul 2> nul

taskkill /f /im AteraAgent.exe > nul 2> nul \n 
taskkill /f /im TicketingTray.exe > nul 2> nul 
taskkill /f /im AgentPackageMonitoring > nul 2> nul 
taskkill /f /im AgentPackageInformation > nul 2> nul 
taskkill /f /im AgentPackageRunCommandInteractive > nul 2> nul 
taskkill /f /im AgentPackageEventViewer.exe > nul 2> nul 
taskkill /f /im AgentPackageSTRemote.exe > nul 2> nul 
taskkill /f /im AgentPackageInternalPoller.exe > nul 2> nul 
taskkill /f /im AgentPackageWindowsUpdate.exe > nul 2> nul 
taskkill /f /im AgentPackageSystemTools.exe > nul 2> nul 
taskkill /f /im AgentPackageHeartbeat.exe > nul 2> nul 
taskkill /f /im AgentPackageUpgradeAgent > nul 2> nul 
taskkill /f /im AgentPackageProgramManagement > nul 2> nul 
taskkill /f /im AgentPackageRegistryExplorer.exe > nul 2> nul

timeout /t 4 /nobreak >nul

REG DELETE “HKEY_CURRENT_USER\Software\ATERA Networks” /f > nul 2> nul 
REG DELETE “HKEY_LOCAL_MACHINE\SOFTWARE\ATERA Networks” /f > nul 2> nul 
REG DELETE “HKEY_CLASSES_ROOT\Installer\Products\4758948C95C1B194AB15204D95B42292” /f > nul 2> nul 
REG DELETE “HKEY_CLASSES_ROOT\Installer\Products\10F15BFE50893924BB61F671FEC4DE2F” /f > nul 2> nul
REG DELETE “HKEY_CLASSES_ROOT\Installer\Products\FF85A16D746FC5B49B8933204662781D” /f > nul 2> nul

RMDIR /S /Q “C:\Program Files\ATERA Networks\AteraAgent” > nul 2> nul 
RMDIR /S /Q “C:\Program Files (x86)\ATERA Networks” > nul 2> **nul**
```