# Client and User Discovery Methods

### In SCCM, navigate to Administration\Overview\Hierarchy Configuration\Discovery Methods.
### Right-click and open Active Directory Forest Discovery Properties.
### Enable the following boxes:
  - Enable Active Directory Forest Discovery.
  - Automatically create Active Directory site boundaries when they are discovered.
  - Automatically create IP address range for IP subnets when they are discovered.
  - Schedule: Run every: 1 Weeks.
### Click "OK."
![CUDM](https://github.com/whuynhit/SCCM/blob/main/Configuration%20Manager%20Basics/Client%20and%20User%20Discovery%20Methods/sub/1.png)

### Right-click and open Active Directory Group Discovery Properties.
### Enable the following:
  - Enable Active Directory Group Discovery.
### Add... Location...
![CUDM](https://github.com/whuynhit/SCCM/blob/main/Configuration%20Manager%20Basics/Client%20and%20User%20Discovery%20Methods/sub/2.png)

### Add Active Directory Location:
  - Name: MYDOMAIN Security Groups.
  - Location: LDAP://DC=mydomain,DC=com.
  - Enable Recursively search Active Directory child containers
  - Use the site server's computer account.

### Click "OK" and with new Discovery scope added, click "OK" again.
![CUDM](https://github.com/whuynhit/SCCM/blob/main/Configuration%20Manager%20Basics/Client%20and%20User%20Discovery%20Methods/sub/3.png)

### Right-click and open Active Directory System Discovery Properties.
### Enable the following:
  - Enable Active Directory System Discovery.
### Click New Active Directory containers (star icon):

### Active Directory Container:
  - Path: LDAP://DC=mydomain,DC=com.
  - Recursively search Active Directory child containers.
  - Use the site server's computer account.
### Click "OK."
![CUDM](https://github.com/whuynhit/SCCM/blob/main/Configuration%20Manager%20Basics/Client%20and%20User%20Discovery%20Methods/sub/4.png)
### A new Active Directory container should now be added.
![CUDM](https://github.com/whuynhit/SCCM/blob/main/Configuration%20Manager%20Basics/Client%20and%20User%20Discovery%20Methods/sub/5.png)

### Click the Options tab.
### Select "Only discover computers that have logged on to a domain in a given period of time."
### Click "OK."
![CUDM](https://github.com/whuynhit/SCCM/blob/main/Configuration%20Manager%20Basics/Client%20and%20User%20Discovery%20Methods/sub/6.png)

### Right-click and open Active Directory User Discovery Properties.
### Enable the following:
  - Enable Active Directory User Discovery.
### Click New Active Directory containers (star icon):

### Active Directory Container:
  - Path: LDAP://DC=mydomain,DC=com.
  - Recursively search Active Directory child containers.
  - Use the site server's computer account.
### Click "OK."
### A new Active Directory container should now be added.
### Click "OK" again.
![CUDM](https://github.com/whuynhit/SCCM/blob/main/Configuration%20Manager%20Basics/Client%20and%20User%20Discovery%20Methods/sub/7.png)

### Navigate to Assets and Compliance\Overview\Devices.
### We can see our two servers and one workstation in the network, meaning the Discovery Methods are working.
![CUDM](https://github.com/whuynhit/SCCM/blob/main/Configuration%20Manager%20Basics/Client%20and%20User%20Discovery%20Methods/sub/8.png)
