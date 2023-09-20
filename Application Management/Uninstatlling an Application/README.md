# Uninstalling an Application

### In SCCM, navigate to Software Library\Overview\Application Management\Packages.
### Right-click and select "Create Program."
![Uninstall](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Uninstatlling%20an%20Application/sub/1.png)

### Program Type: Standard program.
![Uninstall](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Uninstatlling%20an%20Application/sub/2.png)

### Standard Program:
  - Name:  XML Notepad - Uninstall.
  - Command line:
```
Uninstall script:
MsiExec.exe /X{F02D9762-C9D4-4594-B7F2-788099ADF5E8} /qn

Taken from Regeditor directory:
Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Uninstall\{F02D9762-C9D4-4594-B7F2-788099ADF5E8}

```
  - Run: Hidden.
  - Program can run: Whether or not a user is logged on.
  - Drive mode: Run with UNC name.
###
![Uninstall](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Uninstatlling%20an%20Application/sub/3.png)

### Click "Next" and then click "Close."
![Uninstall](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Uninstatlling%20an%20Application/sub/4.png)

### In the bottom pane, select the Programs tab.
### Right-click XML Notepad - Uninstall and select "Deploy."
![Uninstall](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Uninstatlling%20an%20Application/sub/5.png)

### General:
  - Software: XML Notepad - Uninstall.
  - Collection: Windows 10 Workstations.
###
![Uninstall](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Uninstatlling%20an%20Application/sub/6.png)

### Content:
  - Select WS22SCCM.MYDOMAIN.COM as Distribution Point.
###
![Uninstall](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Uninstatlling%20an%20Application/sub/7.png)

### Deployment Settings:
  - Purpose: Required.
###
![Uninstall](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Uninstatlling%20an%20Application/sub/8.png)

### Assignment schedule: New...
  - Assignment immediately after this event: As soon as possibe.
  - Rerun behavior: Rerun if failed previous attempt.
###
![Uninstall](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Uninstatlling%20an%20Application/sub/9.png)

### User Experience:
  - Enable "Commit change at deadline or during a maintenance window (requires restarts)."
###
![Uninstall](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Uninstatlling%20an%20Application/sub/10.png)

### Keep the default selections.
![Uninstall](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Uninstatlling%20an%20Application/sub/11.png)

### Close.
### After deployment, XML Notepad should be uninstalled from CLIENT1 workstation.
![Uninstall](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Uninstatlling%20an%20Application/sub/12.png)
