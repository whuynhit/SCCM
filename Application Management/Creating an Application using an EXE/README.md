# Creating an Application using an EXE

### For this example, we shall be installing the [Chrome](https://www.google.com/chrome) browser.
### In SCCM, navigate to Software Library\Overview\Application Management\Applications.
### Right-click and select "Create Application."
### Manually specify the application information.
![exe](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20EXE/sub/1.png)

### General Information:
  - Name: Google Chrome.
  - Application comments: Browser.
  - Publisher: Google.
  - Software version: 116.0.5845.141.
  - Owners: Administrator.
  - Support contacts: Administrator.
###
![exe](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20EXE/sub/2.png)

### In Software Center:
  - Localized Application Name: Google Chrome.
  - User categories: Browser.
  - Icon: <image.icon>.
###
![exe](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20EXE/sub/3.png)

### Deployment Types:
  - Add...
###
![exe](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20EXE/sub/4.png)

### Create Deployment Type:
### General Information:
  - Type: Script Installer.
  - Manually specify the deployment type information.
###
![exe](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20EXE/sub/5.png)

### Name: Chrome <version_number> exe x86.
![exe](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20EXE/sub/6.png)

### Content location: \\WS22SCCM\Software\Google Chrome.
```
Regeditor directory for uninstall string and DisplayVersion:
Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome

Install program:
"ChromeSetup.exe" /silent /install

Uninstall program:
"C:\Program Files\Google\Chrome\Application\116.0.5845.141\Installer\setup.exe" --uninstall --channel=stable --system-level --verbose-logging
```

![exe](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20EXE/sub/7.png)

### Detection Method:
  - Add Clause...
###
![exe](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20EXE/sub/8.png)

### Detection Rule:
  - Setting Type: Registry.
  - Hive: Browse...
###
![exe](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20EXE/sub/9.png)

### Browse Registry and navigate to Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome and select DisplayVersion.
![exe](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20EXE/sub/10.png)

### Detection Rule:
  - Setting Type: Registry.
  - Hive: HKEY_LOCAL_MACHINE.
  - Key: SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome
  - Value: DisplayVersion.
  - Enable "This registry key is associated with a 32-bbit application on 64-bit systems."
  - Data Type: Version.
  - Enable "This registry setting must satisfy the following rule to indicate the prescence of this application."
  - Operator: Greater than or equal to.
  - Value: 116.0.5845.141.
###
![exe](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20EXE/sub/11.png)

### Detection method should now be configured with a detection rule.
![exe](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20EXE/sub/12.png)

### User Experience:
  - Installation Behavior: Install for system.
  - Logon requirement: Whether or not a user is logged on.
  - Installation program visibility: Normal.
  - Maximum allowed run time (minutes): 15 minutes.
  - Estimated installation time (minutes): 2 minutes.
###
![exe](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20EXE/sub/13.png)

### Click "Next" til completion and then click "Close."
![exe](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20EXE/sub/14.png)

### Deployment type should now be configured.
### Click "Next" til completion and then click "Close."
![exe](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20EXE/sub/15.png)


### Right-click the newly created application and select "Properties."
### Google Chrome Properties:
  - Enable "Allow this application to be installed from the Install Application task sequence action without being deployed."
### Apply changes.
![exe](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20EXE/sub/16.png)

### CLIENT1 Workstation should be able to see the Google Chrome application in Software Center after deployment from SCCM.
![exe](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20EXE/sub/17.png)
