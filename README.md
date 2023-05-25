# WinMods
Settings and Modifications for Windows

##Disable Old TLS Protocols
See [Disable Old TLS Protocols] directory

##DisableSearchBoxSuggestions
https://www.tomshardware.com/how-to/disable-windows-web-search
See [DisableSearchBoxSuggestions] directory.



##Disable Edge "Use Recommended Browser Settings"
https://beebom.com/how-disable-use-recommended-browser-settings-microsoft-edge/
edge://flags/#edge-show-feature-recommendations
Set "Show feature and workflow recommendations" to Disable; then restart edge.


##Disable Old Style Right Click in Windows11 FileExplorer
https://www.xda-developers.com/how-to-open-full-right-click-menu-by-default-windows-11/
To get back to old Win 10 style File Right Click menu.
> reg.exe add "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}\InprocServer32" /f /ve
To restore new context menu options (ie. revert back to default.)
> reg.exe delete "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}" /f
