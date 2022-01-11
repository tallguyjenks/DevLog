---
id: oYPJOB51rUiNBMKVbIB23
title: Netstat
desc: ''
updated: 1641879998814
created: 1641879876574
---

allows you to check the state of ports on the local host.

- `-a` displays all connections (active [[focus.networking.protocol.tcp]] and [[focus.networking.protocol.udp]] connections plus ports in the listening state).
- `-o` shows the Process ID (PID) number that has opened the port.
- `-b` shows the process name that has opened the port.
- `-n` displays ports and addresses in numerical format. Skipping name resolution speeds up each query.
- `-s` shows per protocol statistics (such as packets received, errors, discards, unknown requests, port requests, failed connections, and so on).
- `-p` proto displays connections by protocol ([[focus.networking.protocol.tcp]] or [[focus.networking.protocol.udp]] or TCPv6/UDPv6). When used with `-s`, this switch can also filter the statistics shown by IP, IPv6, [[focus.networking.protocol.icmp]], and ICMPv6.
- `-r` shows the routing table.
- `-e` displays Ethernet statistics.