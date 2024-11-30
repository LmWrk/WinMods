# WinMods
Settings and Modifications for Windows


## Disable Old TLS Protocols
See [Disable Old TLS Protocols] directory


## DisableSearchBoxSuggestions
https://www.tomshardware.com/how-to/disable-windows-web-search

See [DisableSearchBoxSuggestions] directory.


## Win10 Disable Reserved Storage
[Option 1] See [Win10-ReservedStorage] directory for Regisytry method.

To check status, run in PowerShell (As Admin):
> DISM.exe /Online /Get-ReservedStorageState

[Option 2]
To disable Reserved Storage via DISM:
> DISM.exe /Online /Set-ReservedStorageState /State:Disabled

To enable Resverd Storage via DISM:
> DISM.exe /Online /Set-ReservedStorageState /State:Enabled

[Note: Setting only effective after Windows Update installs an update.]

## Disable Edge "Use Recommended Browser Settings"
https://beebom.com/how-disable-use-recommended-browser-settings-microsoft-edge/

edge://flags/#edge-show-feature-recommendations  
Set "Show feature and workflow recommendations" to Disable; then restart edge.


## Enable Old Style Right Click in Windows11 FileExplorer
https://www.xda-developers.com/how-to-open-full-right-click-menu-by-default-windows-11/

To get back to old Win 10 style File Right Click menu.
> reg.exe add "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}\InprocServer32" /f /ve

To restore new context menu options (ie. revert back to default.)
> reg.exe delete "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}" /f

## Change Power Settings Quick

Never Standby on AC
> C:\Windows\System32\powercfg.exe -x standby-timeout-ac 0

Standby in 30 min on AC
> C:\Windows\System32\powercfg.exe -x standby-timeout-ac 30

## Uninstall widgets or OneDrive
In PowerShell:
```
winget uninstall “windows web experience pack”
winget uninstall Microsoft.OneDrive
```

## Disable Lock Screen
```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\Personalization]
"NoLockScreen"=dword:00000001
```

## Turn Num Lock ON for Login Screen
```
Windows Registry Editor Version 5.00

[HKEY_USERS\.DEFAULT\Control Panel\Keyboard]
"InitialKeyboardIndicators"="2147483650"
```
