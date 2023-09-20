# Creating an Application using the Package Model

### For this example, we shall be installing [XML Notepad](https://microsoft.github.io/XmlNotepad/#install).
### In SCCM, navigate to Software Library\Overview\Application Management\Packages.
### Right-click and select "Create Package."
### Package:
  - Name: XML Notepad.
  - Enable "This package contains source files."
  - Source folder: \\WS2SCCM\Software\XML Notepad\XmlNotepadSetup.
![pack](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20the%20Package%20Model/sub/1.png)

### Program Type: Standard program.
![pack](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20the%20Package%20Model/sub/2.png)

### Standard Program:
  - Name:  XML Notepad - Install.
  - Command line:
```
Install script:
MsiExec.exe /i XmlNotepadSetup.msi /qn
```
  - Run: Hidden.
  - Program can run: Whether or not a user is logged on.
  - Drive mode: Run with UNC name.
###
![pack](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20the%20Package%20Model/sub/3.png)

### Requirements:
  - Enable "This program can run on any platform."
  - Estimated disk space: 10 MB.
  - Maximum allowed run time (minutes): 15.
![pack](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20the%20Package%20Model/sub/4.png)

### Click "Next" and then click "Close."
![pack](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20the%20Package%20Model/sub/5.png)

### Right-click XML Notepad and select "Distribute Content."
![pack](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20the%20Package%20Model/sub/6.png)

### Content Distribution:
  - Add... Distribution Point.
###
![pack](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20the%20Package%20Model/sub/7.png)

### Select WS22SCCM.MYDOMAIN.COM as Distribution Point.
![pack](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20the%20Package%20Model/sub/8.png)

### Click "Next" til completion and then click "Close."
![pack](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20the%20Package%20Model/sub/9.png)

### Right-click XML Notepad and select "Deploy."
![pack](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20the%20Package%20Model/sub/10.png)

### General:
  - Software: XML Notepad - Install.
  - Collection: Windows 10 Workstations.
###
![pack](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20the%20Package%20Model/sub/11.png)

### Content:
  - Select WS22SCCM.MYDOMAIN.COM as Distribution Point.
![pack](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20the%20Package%20Model/sub/12.png)

### Deployment Settings:
  - Purpose: Required.
###
![pack](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20the%20Package%20Model/sub/13.png)

### Assignment schedule: New...
![pack](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20the%20Package%20Model/sub/14.png)

### Assignment immediately after this event: As soon as possibe.
![pack](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20the%20Package%20Model/sub/15.png)

### Rerun behavior: Rerun if failed previous attempt.
![pack](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20the%20Package%20Model/sub/16.png)

### User Experience:
  - Enable "Software Installation."
  - Enable "Commit change at deadline or during a maintenance window (requires restarts)." 
![pack](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20the%20Package%20Model/sub/17.png)

### Click "Next" and then click "Close."
![pack](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20the%20Package%20Model/sub/18.png)

### After deployment, XML Notepad should be automatically installed on CLIENT1 workstation.
![pack](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20the%20Package%20Model/sub/19.png)
