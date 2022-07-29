

Management software that provides a location from which you can oversee network activity. 

The monitor polls agents at regular intervals for information from their [[terms.mib]]'s and displays the information for review. 

It also displays any trap operations as alerts for the network administrator to assess and act upon as necessary. 

The monitor can retrieve information from a device in two main ways:

- [[n.protocol.snmp.monitor.get]]
- [[n.protocol.snmp.monitor.trap]]

The monitor can be used to change certain variables using the `Set` command. 

It can also walk an [[terms.mib]] subtree by using multiple `Get` and `Get Next` commands. 

This is used to discover the complete layout of an [[terms.mib]]. 

Device queries take place over [[n.protocol.udp]] port [[n.port.161]]; traps are communicated over UDP port [[n.port.162]].
