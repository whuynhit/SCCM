# Using a Collection to Enforce a Maintenance Window

### In SCCM, navigate to Assets and Compliance\Overview\Device Collections.
### Right-click and create a new device collection.
### General:
  - Name: Contoso OU.
  - Limiting Collections: All Systems.
###
![MW](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Using%20a%20Collection%20to%20Enforce%20a%20Maintenance%20Window/sub/1.png)

### Membership Rules:
 - Add Rule > Direct Rule.
###
![MW](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Using%20a%20Collection%20to%20Enforce%20a%20Maintenance%20Window/sub/2.png)

### Create Direct Membership Rule:
  - Resource Class: System Resources.
  - Attribute name: Name.
  - Value: %.
###
![MW](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Using%20a%20Collection%20to%20Enforce%20a%20Maintenance%20Window/sub/3.png)

### Select Resources: CLIENT1.
### Click next til completion, then close.
![MW](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Using%20a%20Collection%20to%20Enforce%20a%20Maintenance%20Window/sub/4.png)

### With CLIENT1 added to the device collection, click next til completion, then close.
![MW](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Using%20a%20Collection%20to%20Enforce%20a%20Maintenance%20Window/sub/5.png)

### Right-click Contoso OU and select "Properties."
### Select the Maintenance Windows tab.
### Click Add New (star icon).
![MW](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Using%20a%20Collection%20to%20Enforce%20a%20Maintenance%20Window/sub/6.png)

### Schedule:
  - Name: Contoso OU Maintenance Schedule
  - Set the scheduled time to whenever you like.
###
![MW](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Using%20a%20Collection%20to%20Enforce%20a%20Maintenance%20Window/sub/7.png)

### Click "Apply" and then "OK."
![MW](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Using%20a%20Collection%20to%20Enforce%20a%20Maintenance%20Window/sub/8.png)
