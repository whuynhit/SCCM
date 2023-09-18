# Creating Boundary and Boundary Groups

### In SCCM, navigate to Administration\Overview\Hierarchy Configuration\Boundaries.
### Right-click Boundaries and select "Create Boundary."
![bgroup](https://github.com/whuynhit/SCCM/blob/main/Configuration%20Manager%20Basics/Creating%20Boundary%20and%20Boundary%20Groups/sub/1.png)

### In the Create Boundary window insert the following information:
  - Description: MYDOMAIN Boundary.
  - Type: Active Directory site.
  - Active Directory site name: Default-First-Site-Name.
### Click "OK."
![bgroup](https://github.com/whuynhit/SCCM/blob/main/Configuration%20Manager%20Basics/Creating%20Boundary%20and%20Boundary%20Groups/sub/2.png)

### Right-click Boundary Groups and select "Create Boundary Group."
![bgroup](https://github.com/whuynhit/SCCM/blob/main/Configuration%20Manager%20Basics/Creating%20Boundary%20and%20Boundary%20Groups/sub/3.png)

### In the Create Boundary Group window under General tab insert the following information:
  - Boundary Group Name: MYDOMAIN Boundary Group.
  - Boundaries: Add... "Default First-Site-Name."
### Click "OK."
![bgroup](https://github.com/whuynhit/SCCM/blob/main/Configuration%20Manager%20Basics/Creating%20Boundary%20and%20Boundary%20Groups/sub/4.png)

### In the Create Boundary Group window under References tab insert the following information:
  - Site assignment: Use this boundary group for site assignment
  - Assigned site: SC1-SCCM Site
  - Site system servers: Add... SC1
### Click "OK."
![bgroup](https://github.com/whuynhit/SCCM/blob/main/Configuration%20Manager%20Basics/Creating%20Boundary%20and%20Boundary%20Groups/sub/5.png)
