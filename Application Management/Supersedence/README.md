# Supersedence

### For this example, we shall be superseding [7-Zip](https://www.7-zip.org/download.html) with the latest version.
### In SCCM, navigate to Software Library\Overview\Application Management\Applications.
### Create the latest 7-Zip.msi application with both 64-bit and 32-bit deployment types.
### Right-click the latest version of 7-Zip and select "Properties."
### Navigate to the Supercedence tab:
  - Add...
###
![Super](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Supersedence/sub/1.png)

### Specify Supercedence Relationship:
  - Superceded Application: select the previous version of the application.

| Old Deployment Type | New Deployment Type |
|-|-|
| 7-Zip old version x64.msi | 7-Zip new version x64.msi |
| 7-Zip old version x86.msi | 7-Zip new version x86.msi |
###
![Super](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Supersedence/sub/2.png)

### Click "Apply."
![Super](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Supersedence/sub/3.png)

### Right-click the latest version of 7-Zip and select "Deploy."
### General:
  - Software: 7-Zip 23.01 x64.
  - Collection: Windows 10 Workstations.
###
![Super](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Supersedence/sub/4.png)

### Content:
  - Add... Distribution Point.
###
![Super](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Supersedence/sub/5.png)

### Select WS22SCCM.MYDOMAIN.COM as Distribution Point.
![Super](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Supersedence/sub/6.png)

### Deployment Settings:
  - Action: Install.
  - Purpose: Available.
  - Enable "Automatically upgrade any superseded versions of this application."
###
![Super](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Supersedence/sub/7.png)

### Click "Next" til completion, then click "Close."
### After deployment of the latest version of 7-Zip, the updated version should automatically be installed on deployed Workstations.
![Super](https://github.com/whuynhit/SCCM/blob/main/Application%20Management/Supersedence/sub/8.png)
