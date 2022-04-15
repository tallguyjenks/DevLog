---
id: 23xvy5h0503jnwb51mhvvjv
title: Configuration
desc: ''
updated: 1650049769786
created: 1646726626690
---

## Link Aggregation

[[n.link-aggregation]] / [[n.protocol.lacp]]

in the console follow the prompts to add all current interfaces to a `lagg` using [[n.protocol.lacp]], Then configure the aggregation for [[n.protocol.dhcp]]

Now the web console should be available at a listed IP Address

## Configure Users and groups for shared volumes

To create shared volumes you can access through connection to your local network, see the following instructions.
Go to accounts on the left panel.
Click on groups.
Click add.
Enter a group name (you can leave the GID as it is).
Enable permit sudo and samba authentication.
Submit.
Go to accounts on the left panel.
Click on users.
Click add.
Fill in all the empty field under Identification
Uncheck new primary group.
Choose the group you made previously from the drop down menu in primary groups.
Go ahead and check all of the boxes under Home Directory Permissions.
Under Authentication check permit sudo and Samba authentication.
Submit.