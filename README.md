# seb-vm-bypass
A quick patch for SEB 3.10.0.826 that sets IsVirtualMachine to always return false.

## Installation
1. Install regular SEB of version 3.10.0 (others may work, worth trying).
2. Replace the SafeExamBrowserMonitoring.dll in C:\Program Files\SafeExamBrowser\Application with the one in this repo.
3. You're gorgeous!

## How to make your own patch for SEB
1. Download the source code from the latest release at [GitHub](https://github.com/SafeExamBrowser/seb-win-refactoring/releases/tag/v3.10.0)
2. Unzip
3. Install Visual Studio
4. Open the .sln file in it
5. Find the method IsVirtualMachine() using the global search (Ctrl+Shift+F)
6. Replace the last statement ```return isVirtualMachine;``` with ```return false;```
7. With the file open, hit Debug next to x64 and select Release
8. Hit Build > Rebuild SafeExamBrowser.Monitoring
9. In the build output, find a line that shows output DLL file path
10. With that DLL, replace the original DLL (see Installation)
 
