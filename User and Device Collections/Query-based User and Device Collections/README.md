# Query-Based User and Device Collections


## User Collections


### Example 1

###  On the DC Server in Active Directory Users and Computers, create a new Managers OU and create new three users.
![Ex1](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex1/1.png)

### On the SCCM Server, in SCCM, navigate to Assets and Compliance\Overview\User Collections.
### Right-click and create a new user collection.
### General:
- Name: Query Managers.
- Limiting Collections: All Users.
###
![Ex1](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex1/2.png)

### Membership Rules:
 - Use incremental updates for this collection.
###
![Ex1](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex1/3.png)

### Membership Rules:
 - Add Rule > Query Rule.
###
![Ex1](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex1/4.png)

### Query Rule Properties:
  - Name: Managers.
  - Resource Class: User Resource.
  - Click "Edit Query Statement."
### 
![Ex1](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex1/5.png)

### Query Statement Properties:
  - New (Star icon).
###
![Ex1](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex1/6.png)

### Criterion Properties:
  - Criterion Type: Simple value.
  - Where: Select...
###
![Ex1](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex1/7.png)

### Select Attribute:
  - Attribute class: User Resource.
  - Attribute: User OU Name.
###
![Ex1](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex1/8.png)

### Criterion Properties:
  - Operator: is equal to.
  - Value: Value...
###
![Ex1](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex1/9.png)

### Values: MYDOMAIN.COM/SCCMDOMAIN/MANAGERS.
![Ex1](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex1/10.png)

### Query Rule Properties:
  - Query Statement should now be automatically changed to:
```
select * from SMS_R_User 
where SMS_R_User.UserOUName = "MYDOMAIN.COM/SCCMDOMAIN/MANAGERS"
```
###
![Ex1](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex1/11.png)

### Managers from query statement should now be added to the user collection.
![Ex1](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex1/12.png)

### Click next til completion, then close.
![Ex1](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex1/13.png)

### With members from the Managers OU added to the user collection, the user collection should reflect the number of members of the OU.
![Ex1](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex1/14.png)

### Navigate to Assets and Compliance\Overview\Users\Query Managers.
### You should be a to see the domain users that are members of the Manager OU.
![Ex1](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex1/15.png)



 
### Example 2

### On the DC Server in Active Directory Users and Computers, choose a user and open the user properties.
### Select the Organization tab.
### Insert the following information to specified fields:
  - Job Title: Engineer.
  - Department: Engineering.
  - Company: Contoso.
![Ex2](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex2/1.png)

### In SCCM, navigate to Administration\Overview\Hierarchy Configuration\Discovery Methods
### Right-click Active Directory User Discovery and open Properties. Select the Active Directory Attributes.
### Add the "department" attribute to the Selected Attributes section.
![Ex2](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex2/2.png)

### Navigate to Assets and Compliance\Overview\User Collections.
### Right-click and create a new user collection.
### General:
- Name: Engineering
- Limiting Collections: All Users.
###
![Ex2](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex2/3.png)

### Membership Rules:
 - Use incremental updates for this collection.
 - Add Rule > Query Rule.
###
![Ex2](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex2/4.png)


### Query Rule Properties:
  - Name: Engineering.
  - Resource Class: User Resource.
  - Click "Edit Query Statement."
###
![Ex2](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex2/5.png)

### Query Statement Properties:
  - New (Star icon).
###
![Ex2](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex2/6.png)

### Criterion Properties:
  - Criterion Type: Simple value.
  - Where: Select...
### Select Attribute:
  - Attribute class: User Resource.
  - Attribute: department.
###
![Ex2](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex2/7.png)

### Criterion Properties:
  - Criterion Type: Simple value.
  - Where: User Resource - department.
  - Operator: is equal to.
  - Value: Engineering.
###
![Ex2](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex2/8.png)

### Click "OK" and "Next" til completion, then click "Close."
![Ex2](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex2/9.png)

### Navigate to Assets and Compliance\Overview\Users\Engineering.
### You should be able to see the one domain user who was associated with "Engineering" in the user's department attribute that was assigned through Active Directory Users and Computers.
![Ex2](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex2/10.png)




### Example 3

### On the DC Server, in Active Directory Users and Computers, add three domain users as members of the Domain Admins user group.
![Ex3](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex3/1.png)

### In SCCM, Navigate to Assets and Compliance\Overview\User Collections.
### Right-click and create a new user collection.
### General:
- Name: Query AD.
- Limiting Collections: All Users.
###
![Ex3](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex3/2.png)

### Membership Rules:
 - Use incremental updates for this collection.
 - Add Rule > Query Rule.
###
![Ex3](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex3/3.png)

### Query Statement Properties:
  - New (Star icon).
### Criterion Properties:
  - Criterion Type: Simple value.
  - Where: User Resource - User Group Name.
  - Operator: is equal to.
  - Value: MYDOMAIN\Domain Admins.
###
![Ex3](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex3/4.png)

### Click "OK" and "Next" til completion, then click "Close."
![Ex3](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex3/5.png)


### Navigate to Assets and Compliance\Overview\Users\Query AD.
### You should be able to see the domain users who have been added to the Domain Admins user group in Active Directory Users and Computers.
![Ex3](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/User/Ex3/6.png)




## Device Collections

### In SCCM, Navigate to Assets and Compliance\Overview\Device Collections.
### Right-click and create a new user collection.
### General:
- Name: Query Services.
- Limiting Collections: All Systems.
###
![Ex1](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/Device/Ex1/1.png)

### Membership Rules:
 - Use incremental updates for this collection.
 - Add Rule > Query Rule.
###
![Ex1](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/Device/Ex1/2.png)

### Query Rule Properties:
  - Name: Services.
  - Resource Class: System Resource.
  - Click "Edit Query Statement."
###
![Ex1](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/Device/Ex1/3.png)

### Query Statement Properties:
  - New (Star icon).
###
![Ex1](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/Device/Ex1/4.png)


### Select Attribute:
  - Attribute class: Services.
  - Attribute: Name.
###
![Ex1](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/Device/Ex1/5.png)

### Criterion Properties:
  - Criterion Type: Simple value.
  - Where: User Resource - Services - Name.
  - Operator: is equal to.
  - Value: BITS.
###
![Ex1](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/Device/Ex1/6.png)

### Click "OK" and "Next" til completion, then click "Close."
![Ex1](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/Device/Ex1/7.png)


### Navigate to Assets and Compliance\Overview\Users\Query AD.
### You should be able to see the domain system that runs the specified service.
![Ex1](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Query-based%20User%20and%20Device%20Collections/Device/Ex1/8.png)

