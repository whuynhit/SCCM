# Preparing for Client Installations with Group Policy

### On the DC Server, open Group Policy Management.
### Create and link a new GPO to the OU that contains your workstation machine objects.
### Name the GPO "SCCM Client."
![gp](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Preparing%20for%20Client%20Installations%20with%20Group%20Policy/sub/1.png)

### Right-click SCCM Client and select "Edit."
### In the Group Policy Management Editor, navigate to Computer Configuration/Preferences/Control Panel Settings/Local Users and Groups.
### Right-click and create a new Local Group.
![gp](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Preparing%20for%20Client%20Installations%20with%20Group%20Policy/sub/2.png)

### New Local Group Properties:
  - Group name: Administrators (built-in)
  - Members: Add...
    - Local Group Member: MYDOMAIN\WS22SCCM$
    - Or browse for the computer in the Select User, Computer or Group window after enabling the Computer object type in the search tool.
![gp](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Preparing%20for%20Client%20Installations%20with%20Group%20Policy/sub/3.png)

### With the server computer account added, click "OK."
![gp](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Preparing%20for%20Client%20Installations%20with%20Group%20Policy/sub/4.png)

### Navigate to Computer Configuration/Policies/Administrative Templates/Network/Network Connections/Windows Defender Firewall/Domain Profile.
### Enable "Windows Defender Firewall: Protect all network connections" policy.
![gp](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Preparing%20for%20Client%20Installations%20with%20Group%20Policy/sub/5.png)

### Navigate to Computer Configuration/Policies/Windows Settings/ Security Settings/Windows Defender Firewall with Advanced Security/Windows Defender Firewall with Advanced Security/Inbound Rules.
### Create new Inbound rule:
  - Rule Type: Predefined: Windows Management Instrumentation (WMI).
  - Predefined Rules: Keep all three checked.
  - Action: Allow the connection.
###
![gp](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Preparing%20for%20Client%20Installations%20with%20Group%20Policy/sub/6.png)
![gp](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Preparing%20for%20Client%20Installations%20with%20Group%20Policy/sub/7.png)
![gp](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Preparing%20for%20Client%20Installations%20with%20Group%20Policy/sub/8.png)

### Create another new Inbound rule:
  - Rule Type: Predefined: File and Printer Sharing.
  - Predefined Rules: Keep all predefined rules checked.
  - Action: Allow the connection.
###
![gp](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Preparing%20for%20Client%20Installations%20with%20Group%20Policy/sub/9.png)
![gp](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Preparing%20for%20Client%20Installations%20with%20Group%20Policy/sub/10.png)
![gp](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Preparing%20for%20Client%20Installations%20with%20Group%20Policy/sub/11.png)

### Create new Outbound rule:
  - Rule Type: Predefined: Windows Management Instrumentation (WMI).
  - Predefined Rules: Keep all three checked.
  - Action: Allow the connection.
###
![gp](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Preparing%20for%20Client%20Installations%20with%20Group%20Policy/sub/12.png)
![gp](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Preparing%20for%20Client%20Installations%20with%20Group%20Policy/sub/13.png)
![gp](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Preparing%20for%20Client%20Installations%20with%20Group%20Policy/sub/14.png)

### Create another new Outbound rule:
  - Rule Type: Predefined: File and Printer Sharing.
  - Predefined Rules: Keep all predefined rules checked.
  - Action: Allow the connection.
###
![gp](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Preparing%20for%20Client%20Installations%20with%20Group%20Policy/sub/15.png)
![gp](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Preparing%20for%20Client%20Installations%20with%20Group%20Policy/sub/16.png)
![gp](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Preparing%20for%20Client%20Installations%20with%20Group%20Policy/sub/17.png)

### On the workstation Client1, open Command Prompt and run the following commands:
```
gpupdate /force

gpresult /r
```
### We should then see that the new GPO has taken effect on the workstation.
![gp](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Preparing%20for%20Client%20Installations%20with%20Group%20Policy/sub/18.png)

### Run Local Users and Groups/lusrmgr.msc
### Navigate to Groups.
### Click Administrators.
### We should then see the SCCM Server is an administrator.
![gp](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Preparing%20for%20Client%20Installations%20with%20Group%20Policy/sub/19.png)

### Run Windows Defender Firewall with Advanced Security.
### Click Properties.
### We should see the following message:
### "For your security, some settings are controlled by Group Policy."
### This indicates that the firewall settings from the SCCM Client GPO is in effect.
![gp](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Preparing%20for%20Client%20Installations%20with%20Group%20Policy/sub/20.png)
