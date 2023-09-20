# Creating an Application using an MSI

### For this example, we shall be deploying [7-Zip](https://www.7-zip.org/download.html).
### In SCCM, navigate to Software Library\Overview\Application Management\Applications.
### Right-click and select "Create Application."
### Automatically detect information about this application from installation files:
  - Type: Windows Installer (*.msi file).
  - Location: \\WS22SCCM\Software\Software\7Zip 2201 x64\7z2201-x64.msi.
###
![MSI](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20MSI/sub/1.png)

### General Information:
  - Name: 7-Zip 22.01 x64
  - Application comments: 7-Zip is a file archiver.  
  - Publisher: Igor Pavlov.
  - Software version: 22.01.
  - Installation program: msiexec /i "7z2201-x64.msi" /q.
  - Install behavior: Install for system.
###
![MSI](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20MSI/sub/2.png)

### Click next til completion, then close.
![MSI](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20MSI/sub/3.png)

### In Software Library\Overview\Application Management\Applications, right-click the newly created application and select "Propertie."
### 7-Zip 22.01 x64 Properties:
  - Enable "Allow this application to be installed from the Install Application task sequence action without being deployed."
###
![MSI](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20MSI/sub/4.png)

### In Software Center:
  - Localized Application Name: 7-Zip 2201 x64.
  - User categories: File Archiver.
  - Localized description: 7-Zip is a file archiver.
  - Icon: <image.icon>.
###
![MSI](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20MSI/sub/5.png)

### At the bottom pane, select the Deployment Types tab and right-click 7-Zip x64 and select "Properties."
![MSI](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20MSI/sub/6.png)

### Navigate to the User Experience tab:
  - Maximum allowed run time (minutes): 15 minutes.
  - Estimated installation time (minutes): 2 minutes.
###
![MSI](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20MSI/sub/7.png)

### ### Navigate to the Requirements tab.
  - Add...
###
![MSI](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20MSI/sub/8.png)

### Create Requirement:
  - Condition: Operating System.
  - Operator: One of... All Windows 10 (64-bit).
###
![MSI](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20MSI/sub/9.png)

### With a requirement condition set, SCCM will restrict 7-Zip x64 installation attempts to Windows 10 64-bit systems. 
![MSI](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20MSI/sub/10.png)

### Now create a 32-bit deployment type.
### Right-click 7-Zip and select "Create Deployment Type."
![MSI](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20MSI/sub/11.png)

### Automatically detect information about this application from installation files:
  - Type: Windows Installer (*.msi file).
  - Location: \\WS22SCCM\Software\Software\7Zip 2201 x86\7z2201.msi.
###
![MSI](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20MSI/sub/12.png)

### General Information:
  - Name: 7-Zip 22.01 x86
  - Installation program: msiexec /i "7z2201.msi" /q.
  - Install behavior: Install for system.
###
![MSI](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20MSI/sub/13.png)

### Requirements: Add...
### Create Requirement:
  - Condition: Operating System.
  - Operator: One of... All Windows 10 (32-bit).
###
![MSI](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20MSI/sub/14.png)

### Click next til completion, then click "OK."
![MSI](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20MSI/sub/15.png)

### Now create a device collection for deployment.
### Navigate to Assets and Compliance\Overview\Device Collections.
### Right-click and create a new device collection.
### General:
  - Name: Windows 10 Workstations.
  - Limiting Collections: All Systems.
###
![MSI](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20MSI/sub/16.png)

### Membership Rules:
 - Use incremental updates for this collection.
 - Add Rule > Direct Rule.
### Create Direct Membership Rule:
  - Resource Class: System Resources.
  - Attribute name: Name.
  - Value: %.
### Select Resources: CLIENT1.
![MSI](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20MSI/sub/17.png)

### Click "OK" and "Next" til completion, then click "Close."
![MSI](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20MSI/sub/18.png)

### Navigate to Software Library\Overview\Application Management\Applications.
### Right-click 7-Zip and select "Deploy."
![MSI](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20MSI/sub/19.png)

### General:
  - Software: 7-Zip 22.01 x64.
  - Collection: Windows 10 Workstations.
###
![MSI](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20MSI/sub/20.png)

### Content:
  - Add... Distribution Point.
###
![MSI](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20MSI/sub/21.png)

### Select WS22SCCM.MYDOMAIN.COM as Distribution Point.
![MSI](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20MSI/sub/22.png)

### Click "Next" til completion, then click "Close."
![MSI](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20MSI/sub/23.png)

### On the CLIENT1 workstation, open Software Center and the application should now be available for install.
![MSI](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Creating%20an%20Application%20using%20an%20MSI/sub/24.png)
