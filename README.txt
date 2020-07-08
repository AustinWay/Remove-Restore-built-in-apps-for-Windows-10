# Remove-Restore-built-in-apps-for-Windows-10

# https://kb.rice.edu/page.php?id=73705

# How to remove/restore built-in apps for Windows 10
# Before starting these steps, make sure you close all running apps on your computer. Failing to do so can cause problems when you're uninstalling built-in apps.

# Completely Uninstall Default Windows Store Apps in Windows 10
# Before starting these steps, make sure you close all running apps on your computer. Failing to do so can cause problems when you're uninstalling built-in apps.
# Run the following command in an elevated PowerShell (Admin) window.
# Right-click the Start button
# Click Windows Powershell (Admin)
# Type a command into PowerShell.
# For a list of all installed apps and PackageFullName enter
# Get-AppxPackage | Select Name, PackageFullName
# Write down the PackageFullName and replace it in the following command:
# Get-AppxPackage PackageFullName | Remove-AppxPackage

# So the command to remove some of the apps will look as follows:

# Uninstall 3D Builder
# Get-AppxPackage *3dbuilder* | Remove-AppxPackage

# Uninstall Alarms & Clock
# Get-AppxPackage *windowsalarms* | Remove-AppxPackage

# Uninstall Calculator
# Get-AppxPackage *windowscalculator* | Remove-AppxPackage

# Uninstall Camera
# Get-AppxPackage *windowscamera* | Remove-AppxPackage

# Uninstall Calendar & Mail
# Get-AppxPackage *windowscommunicationsapps* | Remove-AppxPackage

# Uninstall Get Office app
# Get-AppxPackage *officehub* | Remove-AppxPackage

# Uninstall Get Started app
# Get-AppxPackage *getstarted* | Remove-AppxPackage

# Uninstall Solitaire Collection
# Get-AppxPackage *solit* | Remove-AppxPackage

# Uninstall Get Skype app
# Get-AppxPackage *skypeapp* | Remove-AppxPackage

# Uninstall Groove Music
# Get-AppxPackage *zunemusic* | Remove-AppxPackage

# Uninstall Microsoft Solitaire Collection
# Get-AppxPackage *solitairecollection* | Remove-AppxPackage

# Uninstall Maps
# Get-AppxPackage *windowsmaps* | Remove-AppxPackage

# Uninstall Money
# Get-AppxPackage *bingfinance* | Remove-AppxPackage

# Uninstall Movies & TV
# Get-AppxPackage *zunevideo* | Remove-AppxPackage

# Uninstall OneNote
# Get-AppxPackage *onenote* | Remove-AppxPackage

# Uninstall News
# Get-AppxPackage *bingnews* | Remove-AppxPackage

# Uninstall People app
# Get-AppxPackage *people* | Remove-AppxPackage

# Uninstall Phone Companion
# Get-AppxPackage *windowsphone* | Remove-AppxPackage

# Uninstall Photos
# Get-AppxPackage *photos* | Remove-AppxPackage

# Uninstall Store
# Get-AppxPackage *windowsstore* | Remove-AppxPackage

# Uninstall Sports
# Get-AppxPackage *bingsports* | Remove-AppxPackage

# Uninstall Voice Recorder
# Get-AppxPackage *soundrecorder* | Remove-AppxPackage

# Uninstall Weather
# Get-AppxPackage *bingweather* | Remove-AppxPackage

# Uninstall Xbox
# Get-AppxPackage *xboxapp* | Remove-AppxPackage



# Run the command to uninstall the particular pre-installed default Windows 10 Store app  and restart your computer.

# If you want to uninstall the particular pre-installed app from all user accounts, use the following command format:
# Get-AppxPackage -allusers PackageFullName | Remove-AppxPackage

# If you wish to remove a pre-installed app from a particular user account, use following command:
# Get-AppxPackage -user username PackageFullName | Remove-AppxPackage

# New Users
# Even though you’ve uninstalled all the apps for all the users, every time you create a new user, the default apps will be reinstalled for that user. You can prevent this default action by executing the following command in the Powershell.
# Get-AppXProvisionedPackage -online | Remove-AppxProvisionedPackage –online


# How to restore built-in apps on Windows 10
# Right-click the Start button
# Click Windows Powershell (Admin)
# Type "Get-AppxPackage -AllUsers |  For each app: Add-AppxPackage -DisableDevelopmentMode -Register "$($_InstallLocation)\AppXManifest.xml"
# Hit Enter. This command tells Windows to install those default apps again. Give it some time and allow it to finish, even if nothing appears to happen at first. Even if you see an error message, restart your PC.
# You should now be able to find all the built-in apps in Windows 10.

# It’s also likely that future updates (especially major updates) could reinstall those apps.
