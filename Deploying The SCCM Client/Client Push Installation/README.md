# Client Push Installations

### In SCCM, navigate to Administration\Overview\Site Configuration\Sites.
### Right-click and select Client Installation Settings > Client Push Installation.
![push](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Client%20Push%20Installation/sub/1.png)

### Client Push Installation Properties:
### Client Push Installation Accounts:
  - Add New Account (star icon).
###
![push](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Client%20Push%20Installation/sub/2.png)
### Windows User Account:
  - Username: <username>
  - Password: Password1
### CLick "OK."
![push](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Client%20Push%20Installation/sub/3.png)

### With a new account added, click "OK."
![push](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Client%20Push%20Installation/sub/4.png)

### Navigate to C:\Program Files\Microsoft Configuration Manager\tools.
### Run cmtrace.exe.
![push](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Client%20Push%20Installation/sub/5.png)

### File > Open.
![push](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Client%20Push%20Installation/sub/6.png)

### Navigate to C:\Program Files\Microsoft Configuration Manager\Logs.
### Open ccm.log.
![push](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Client%20Push%20Installation/sub/7.png)

### ccm.log will show any errors from the server side if there is an issue with deploying the client. 
![push](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Client%20Push%20Installation/sub/8.png)

### In SCCM, navigate to Assets and Compliance\Overview\Devices.
### Right-click the workstation Client1 and select "Install Client."
![push](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Client%20Push%20Installation/sub/9.png)

### Next.
![push](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Client%20Push%20Installation/sub/10.png)

### Next.
![push](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Client%20Push%20Installation/sub/11.png)

### Next.
![push](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Client%20Push%20Installation/sub/12.png)

### Close.
![push](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Client%20Push%20Installation/sub/13.png)

### In cmtrace viewing ccm.log, we can see the list of processes that occurred during the client installation.
![push](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Client%20Push%20Installation/sub/14.png)

### During the installation process, we can see that ccmsetup.exe is running on the client threough the Task Manager.
![push](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Client%20Push%20Installation/sub/15.png)

### After setup and installation completes, open Control Panel on Client1.
### View by: Small icons.
### If you see Configuration Manager listed, then the SCCM Client has been successfully installed on the client machine.
### Click and it will open the Configuration Manager Properties.
![push](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Client%20Push%20Installation/sub/16.png)

### In SCCM, navigate to Assets and Compliance\Overview\Devices.
### After about a 15 minute wait, you should see that the SCCM Client is active on the workstation device.
![push](https://github.com/whuynhit/SCCM/blob/main/Deploying%20The%20SCCM%20Client/Client%20Push%20Installation/sub/17.png)
