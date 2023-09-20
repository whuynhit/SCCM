# Creating an Application that Requires Approval

### For this example, we shall be installing the [Notepad++](https://notepad-plus-plus.org/downloads).
### In SCCM, navigate to Software Library\Overview\Application Management\Applications.
### Right-click and select "Create Application."
### Manually specify the application information.
![Appr](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20that%20Requires%20Approval/sub/1.png)

### General Information:
  - Name: Google Chrome.
  - Application comments: Text Editor.
  - Publisher: Don Ho.
  - Software version: 8.5.6.
  - Owners: Administrator.
  - Support contacts: Administrator.
###
![Appr](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20that%20Requires%20Approval/sub/2.png)

### In Software Center:
  - Localized Application Name: Notepad++ 8.5.6.
  - User categories: Text Editor.
  - Icon: <image.icon>.
###
![Appr](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20that%20Requires%20Approval/sub/3.png)

### Deployment Types:
  - Add...
### Create Deployment Type:
### General Information:
  - Type: Script Installer.
  - Manually specify the deployment type information.
### Name: Notepad++ 8.5.6.
![Appr](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20that%20Requires%20Approval/sub/4.png)

### Content location: \\WS22SCCM\Software\NPP\NPP 8.5.6.
```
Regeditor directory for uninstall string and DisplayVersion:
Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall\Notepad++

Install program:
"npp 8.5.6 Installer x64.exe" /S

Uninstall program:
"C:\Program Files\Notepad++\uninstall.exe" /S
```

![Appr](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20that%20Requires%20Approval/sub/5.png)

### Detection Method:
  - Add Clause...
### Detection Rule:
  - Setting Type: Registry.
  - Hive: Browse...
### Browse Registry and navigate to Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall\Notepad++ and select DisplayVersion.
![Appr](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20that%20Requires%20Approval/sub/6.png)

### Detection Rule:
  - Setting Type: Registry.
  - Hive: HKEY_LOCAL_MACHINE.
  - Key: SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall\Notepad++
  - Value: DisplayVersion.
  - Data Type: Version.
  - Enable "This registry setting must satisfy the following rule to indicate the prescence of this application."
  - Operator: Greater than or equal to.
  - Value: 8.5.6.
###
![Appr](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20that%20Requires%20Approval/sub/7.png)

### Detection method should now be configured with a detection rule.
![Appr](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20that%20Requires%20Approval/sub/8.png)

### User Experience:
  - Installation Behavior: Install for system.
  - Logon requirement: Whether or not a user is logged on.
  - Installation program visibility: Normal.
  - Maximum allowed run time (minutes): 15 minutes.
  - Estimated installation time (minutes): 2 minutes.
###
![Appr](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20that%20Requires%20Approval/sub/9.png)

### Requirements:
| Requirement Type | Operator | Values |
|-|-|-|
| Operating System | One of | All Windows 10 (64-bit) |
###
![Appr](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20that%20Requires%20Approval/sub/10.png)

### Click "Next" til completion and then click "Close."
![Appr](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20that%20Requires%20Approval/sub/11.png)

### Deployment type should now be configured.
![Appr](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20that%20Requires%20Approval/sub/12.png)

### Click "Next" til completion and then click "Close."
![Appr](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20that%20Requires%20Approval/sub/13.png)

### Right-click the newly created application and select "Properties."
### Notepad++ 8.5.6 Properties:
  - Enable "Allow this application to be installed from the Install Application task sequence action without being deployed."
### Apply changes.
![Appr](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20that%20Requires%20Approval/sub/14.png)

## Now create a user collection for deployment.
### Navigate to Software Library\Overview\Application Management\Applications.
### Right-click Notepad++ 8.5.6 and select "Deploy."
### General:
  - Software: Notepad++ 8.5.6.
  - Collection: Windows 10 Users.
###
![Appr](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20that%20Requires%20Approval/sub/15.png)

### Content:
  - Add... Distribution Point.
### Select WS22SCCM.MYDOMAIN.COM as Distribution Point.
![Appr](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20that%20Requires%20Approval/sub/16.png)

### Deployment Settings:
  - Action: Install.
  - Purpose: Available.
  - Enable "Require administrator approval if users request this application.."
###
![Appr](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20that%20Requires%20Approval/sub/17.png)

### User Experience:
  - User notifications: Display in Software Center, and only show notifications for computer restarts.
  - Enable "Commit changes at deadline or during a maintenance window (requires restart)."
###
![Appr](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20that%20Requires%20Approval/sub/18.png)

### Click "Next" til completion and then click "Close."
![Appr](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20that%20Requires%20Approval/sub/19.png)

### On CLIENT1 Workstation, in Software Center, the user may request permission to install the application.
![Appr](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20that%20Requires%20Approval/sub/20.png)

### In SCCM, navigate to Software Library\Overview\Application Management\Application Requests.
### You can find user requests for application installation here.
![Appr](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20that%20Requires%20Approval/sub/21.png)

### In Application Requests, you may approve or deny user requests for installation.
![Appr](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20that%20Requires%20Approval/sub/22.png)

### When request is approved, the user can install the request application.
![Appr](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20that%20Requires%20Approval/sub/23.png)
