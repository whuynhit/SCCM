# Creating Include/Exclude Collections

### In SCCM, navigate to Assets and Compliance\Overview\Device Collections.
### Create two collections. One collection for servers. And one collection for workstations.
### For this example, StaticC DirectR #1 holds the servers WS22DC and WS22SCCM.
### And StaticC DirectR #2 holds the workstation Client1.
![IEC](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Creating%20Include-Exclude%20Collections/sub/1.png)

## Include Collection

### In SCCM, navigate to Assets and Compliance\Overview\Device Collections.
### Right-click and select "Create Device Collection."
### General:
  - Name: Include Collections
  - Limiting Collections: All Syetems
###
![IEC](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Creating%20Include-Exclude%20Collections/sub/2.png)

### Membership Rules:
 - Add Rule > Include Collections.
###
![IEC](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Creating%20Include-Exclude%20Collections/sub/3.png)

### Select Collections:
  - StaticC DirectR #1
  - StaticC DirectR #2
### 
![IEC](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Creating%20Include-Exclude%20Collections/sub/4.png)

### Two collections have now been added to this device collection.
### Click next til completion, then close.
![IEC](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Creating%20Include-Exclude%20Collections/sub/5.png)

## Exclude Collection

### In SCCM, navigate to Assets and Compliance\Overview\Device Collections.
### Right-click and select "Create Device Collection."
### General:
  - Name: Exclude Collections.
  - Limiting Collections: All Syetems.
###
![IEC](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Creating%20Include-Exclude%20Collections/sub/6.png)

### Membership Rules:
 - Add Rule > Direct Rule.
###
![IEC](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Creating%20Include-Exclude%20Collections/sub/7.png)

### Create Direct Membership Rule:
  - Resource Class: System Resource.
  - Attribute name: Name.
  - Value: %.
![IEC](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Creating%20Include-Exclude%20Collections/sub/8.png)

### Select Resources: Select All.
### Click next til completion, then close.
![IEC](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Creating%20Include-Exclude%20Collections/sub/9.png)

### Close.
![IEC](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Creating%20Include-Exclude%20Collections/sub/10.png)

### Right-click Exclude Collections and select "Properties" and navigate to the Membership Rule tab.
### Membership Rules:
 - Add Rule > Exclude Collections.
###
![IEC](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Creating%20Include-Exclude%20Collections/sub/11.png)

### Select Collections:
  - StaticC DirectR #1
### 
![IEC](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Creating%20Include-Exclude%20Collections/sub/12.png)

### Now Exclude Collections only holds devices from StaticC DirecctR #2 and excluded devices belonging to StaticC DirectR #1 collections.
![IEC](https://github.com/whuynhit/SCCM/blob/main/User%20and%20Device%20Collections/Creating%20Include-Exclude%20Collections/sub/13.png)
