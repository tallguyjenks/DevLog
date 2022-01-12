---
id: WpyeyOayFXiH6XZ7Yx3NV
title: Monitor
desc: ''
updated: 1641952773856
created: 1641952706154
---

Management software that provides a location from which you can oversee network activity. 

The monitor polls agents at regular intervals for information from their [[terms.mib]]'s and displays the information for review. 

It also displays any trap operations as alerts for the network administrator to assess and act upon as necessary. 

The monitor can retrieve information from a device in two main ways:



Trap The agent informs the monitor of a notable event (port failure, for instance). The threshold for triggering traps can be set for each value.
The monitor can be used to change certain variables using the Set command. It can also walk an MIB subtree by using multiple Get and Get Next commands. This is used to discover the complete layout of an MIB. Device queries take place over UDP port 161; traps are communicated over UDP port 162.