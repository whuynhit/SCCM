# Using Collections to Enable the Remote Control Features

### In SCCM, navigate to Assets and Compliance\Overview\Device Collections.
### Right-click and create a new device collection.
### General:
  - Name: Remote Control for Desktops.
  - Limiting Collections: All Systems.
###
![RCF](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Using%20Collections%20to%20Enable%20the%20Remote%20Control%20Feature/sub/1.png)

### Membership Rules:
 - Add Rule > Direct Rule.
###
![RCF](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Using%20Collections%20to%20Enable%20the%20Remote%20Control%20Feature/sub/2.png)

### Create Direct Membership Rule:
  - Resource Class: System Resources.
  - Attribute name: Name.
  - Value: %.
###
![RCF](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Using%20Collections%20to%20Enable%20the%20Remote%20Control%20Feature/sub/3.png)

### Select Resources: CLIENT1.
![RCF](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Using%20Collections%20to%20Enable%20the%20Remote%20Control%20Feature/sub/4.png)

### Click next til completion, then close.
![RCF](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Using%20Collections%20to%20Enable%20the%20Remote%20Control%20Feature/sub/5.png)

### Navigate to Administration\Overview\Client Settings.
### Right-click and select "Create Custom Client Device Settings." 
![RCF](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Using%20Collections%20to%20Enable%20the%20Remote%20Control%20Feature/sub/6.png)

### Create Custom Client Device Settings:
  - Name: Remote Desktop.
  - Select and then configure the custom settings for client devices: Remote Tools.
###
![RCF](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Using%20Collections%20to%20Enable%20the%20Remote%20Control%20Feature/sub/7.png)

### In Client Settings, right-click Remote Desktop and select "Properties."
### Select "Remote Tools" and click "Configure Settings."
![RCF](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Using%20Collections%20to%20Enable%20the%20Remote%20Control%20Feature/sub/8.png)

### Remote Control and Windows Defender Firewall Client Settings:
  - Enable Remote Control on client computers.
  - Enable Domain.
###
![RCF](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Using%20Collections%20to%20Enable%20the%20Remote%20Control%20Feature/sub/9.png)

### Remote Tools > Specify remote control settings on client computers:
  - Manage unsolicited Remote Assistance settings: Yes.
  - Manage solicited Remote Assistance settings: Yes.
  - Level of access for Remote Assistance: Full Control.
  - Manage Remote Desktop settings: Yes.
  - Allow permitted viewers to connect by using Remote Desktop connection: Yes.
  - Require network level authentication: Yes.
###
![RCF](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Using%20Collections%20to%20Enable%20the%20Remote%20Control%20Feature/sub/10.png)

### In Client Settings, right-click Remote Desktop and select "Deploy."
![RCF](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Using%20Collections%20to%20Enable%20the%20Remote%20Control%20Feature/sub/11.png)

### Select Collections: Remote Control for Desktops.
![RCF](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Using%20Collections%20to%20Enable%20the%20Remote%20Control%20Feature/sub/12.png)

### On the client workstation CLIENT1, open Control Panel.
### View by: Small icons.
### Open Configuration Manager Properties and click the Action tab.
### Select Machine Policy Retrieval & Evaluation Cycle.
### Click "Run Now."
![RCF](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Using%20Collections%20to%20Enable%20the%20Remote%20Control%20Feature/sub/13.png)

### In SCCM, navigate to Assets and Compliance\Overview\Devices.
### Select the client workstation CLIENT1.
### In the SCCM ribbon menu at the top, select Start > Remote Control.
![RCF](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Using%20Collections%20to%20Enable%20the%20Remote%20Control%20Feature/sub/14.png)

### On CLIENT1, a Configuration Manager Remote Control window will show and ask the user to Approve or Deny the remote control session.
![RCF](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Using%20Collections%20to%20Enable%20the%20Remote%20Control%20Feature/sub/15.png)

### When approved, on the SCCM Server, the CLIENT1 workstation can now be remotely controlled during the remote control session. 
![RCF](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Using%20Collections%20to%20Enable%20the%20Remote%20Control%20Feature/sub/16.png)

### On CLIENT1 in cmtrace.exe, we can see that in C:\Windows\CCM\Logs\CmRcService.log, the remote control session is in progress.
![RCF](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Using%20Collections%20to%20Enable%20the%20Remote%20Control%20Feature/sub/17.png)
