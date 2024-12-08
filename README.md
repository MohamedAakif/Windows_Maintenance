& Windows Maintenance Script

This script is written in C++ and automates various system maintenance tasks on Windows computers. It performs system updates, clears cache, removes temporary files, cleans the Recycle Bin, flushes DNS, and sets the system to high performance mode. The script also logs its activities in a log file for recovery and tracking purposes.

## Requirements

    Windows OS (Windows 10 or later recommended)
    Administrator privileges

## How to Use

    Run as Administrator: To ensure the script performs all required operations, run the script as an administrator. You can right-click on the executable and select Run as administrator.
    Execute the Script: The script will automatically start performing maintenance tasks. Make sure to check the log file C:\Win_Maintenance_log.txt for a detailed record of actions performed.

## How it Works

- Administrator Check: The script first checks if it's being run with administrator privileges. If not, it will display a message and exit.
- System Updates: It forces Windows updates using built-in commands.
- File Cleanup: The script clears temporary files, deletes cache, and removes Recycle Bin contents.
- Power Settings: Sets the system to high-performance power mode to improve performance.
- Logging: All actions are logged in a file located at C:\Win_Maintenance_log.txt.

## Commands Used

    wuauclt.exe /updatenow
    usoclient StartScan
    gpupdate /force
    cleanmgr /autoclean
    powershell -Command "Install-PackageProvider -Name NuGet"
    winget upgrade --all
    del /q /s %USERPROFILE%\AppData\Local\Temp\*
    taskkill /im chrome.exe /f
    ipconfig /flushdns
    powercfg /setactive SCHEME_MAX

## Notes

- The script logs every action performed. Check C:\Win_Maintenance_log.txt for detailed execution logs.
- If the script does not run, ensure that you have Administrator privileges.
