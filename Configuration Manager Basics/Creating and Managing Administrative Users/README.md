# Creating and Managing Administrative Users

### In SCCM, navigate to Administration\Overview\Security\Administrative Users.
### Then right-click Administrative Users and select "Add User or Group."
![admin](https://github.com/whuynhit/SCCM/blob/main/Configuration%20Manager%20Basics/Creating%20and%20Managing%20Administrative%20Users/sub/1.png)

### In the Add User or Group window, specify user or group information:
  - Select a user or group name from the domain.
  - Assigned Security Roles: Add... "Full Administrator."
  - Assigned security scopes and collections: All instances of the objects that are related to the assigned security roles.
### Click "OK."
![admin](https://github.com/whuynhit/SCCM/blob/main/Configuration%20Manager%20Basics/Creating%20and%20Managing%20Administrative%20Users/sub/2.png)

### Alternatively, you can create a domain user group and add a domain user as a member of the group. And then add the newly created domain user group.
### Here I added Jack Cahill to the SCCM Admins Group in Active Directory Users and Computers back on the DC Server.
![admin](https://github.com/whuynhit/SCCM/blob/main/Configuration%20Manager%20Basics/Creating%20and%20Managing%20Administrative%20Users/sub/3.png)

### Then I added SCCM Admins group as an Administrative User group with Full Administrator privileges in SCCM on the SCCM Server.
### Any domain user that is a member of the SCCM Admins user group will have Full Administrative control in SCCM. 
![admin](https://github.com/whuynhit/SCCM/blob/main/Configuration%20Manager%20Basics/Creating%20and%20Managing%20Administrative%20Users/sub/4.png)
