# Assigning a User Collection to an Administrative Security Role

### On the DC Server, in Active Directory Users and Computers, add some members to the SCCM Admins user group.
### For this example, I will have three users as SCCM Admins members.
![SR](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Assigning%20a%20User%20Collection%20to%20an%20Administrative%20Security%20Role/sub/1.png)

### On the SCCM Server, in SCCM, navigate to Assets and Compliance\Overview\User Collections.
### Right-click and create a new user collection.
### General:
  - Name: SCCM Admins.
  - Limiting Collections: All User Groups.
###
![SR](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Assigning%20a%20User%20Collection%20to%20an%20Administrative%20Security%20Role/sub/2.png)

### Membership Rules:
 - Add Rule > Direct Rule.
###
![SR](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Assigning%20a%20User%20Collection%20to%20an%20Administrative%20Security%20Role/sub/3.png)

### Create Direct Membership Rule:
  - Resource Class: User Group Resource.
  - Attribute name: Active Directory Container Name.
  - Value: %.
###
![SR](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Assigning%20a%20User%20Collection%20to%20an%20Administrative%20Security%20Role/sub/4.png)

### Select Resources: MYDOMAIN\SCCM Admins.
![SR](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Assigning%20a%20User%20Collection%20to%20an%20Administrative%20Security%20Role/sub/5.png)


### Click next til completion, then close.
![SR](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Assigning%20a%20User%20Collection%20to%20an%20Administrative%20Security%20Role/sub/6.png)

### With SCCM Admins group added to the collection, click next til completion, then close.
![SR](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Assigning%20a%20User%20Collection%20to%20an%20Administrative%20Security%20Role/sub/7.png)

### Navigate to Administration\Overview\Security\Administrative Users.
### Right-click and select "Add User or Group."
### Add User or Group:
  - User or group name: MYDOMAIN\SCCM Admins
  - Assigned Security Roles: Full Administrator
  - Only the instances of objects that are assigned to the specified security scopes or collections: Add > Collection.
![SR](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Assigning%20a%20User%20Collection%20to%20an%20Administrative%20Security%20Role/sub/8.png)

### Select Collections: SCCM Admins.
### Click "Ok."
### Members of the SCCM Admins group should now be able to have full administrator control in SCCM.
![SR](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Assigning%20a%20User%20Collection%20to%20an%20Administrative%20Security%20Role/sub/9.png)

### To verify this, log out of the current SCCM administrative user.
### Login to the SCCM Server system with a different user that is a member of the SCCM Admins user group.
### Navigate to Administration\Overview\Site Configuration\Servers and Site System Roles.
### Right-click and you should see "Add Site System Roles."
### Only admins should be able to add site system roles.
![SR](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Assigning%20a%20User%20Collection%20to%20an%20Administrative%20Security%20Role/sub/10.png)


### Navigate to Administration\Overview\Security\Administrative Users.
### Right-click and open "SCCM Admins Properties," select Security Roles tab.
### Here, you may change the security roles of the user group.
![SR](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Assigning%20a%20User%20Collection%20to%20an%20Administrative%20Security%20Role/sub/11.png)
