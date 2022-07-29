

allows you to check the state of ports on the local host.

## On Windows

- `-a` displays all connections (active [[n.protocol.tcp]] and [[n.protocol.udp]] connections plus ports in the listening state).
- `-o` shows the Process ID (PID) number that has opened the port.
- `-b` shows the process name that has opened the port.
- `-n` displays ports and addresses in numerical format. Skipping name resolution speeds up each query.
- `-s` shows per protocol statistics (such as packets received, errors, discards, unknown requests, port requests, failed connections, and so on).
- `-p` proto displays connections by protocol ([[n.protocol.tcp]] or [[n.protocol.udp]] or TCPv6/UDPv6). When used with `-s`, this switch can also filter the statistics shown by IP, IPv6, [[n.protocol.icmp]], and ICMPv6.
- `-r` shows the routing table.
- `-e` displays Ethernet statistics.

---

## On Linux

- `‑t` for [[n.protocol.tcp]] Internet connections
- `‑u` for [[n.protocol.udp]] Internet connections
- `‑w` for raw connections
- `‑x` UNIX sockets/local server ports 
- `-a` includes ports in the listening state in the output. `-l` shows only ports in the listening state (omits established connections).
- `-p` shows the Process ID (PID) number that has opened the port (similar to `-o` on Windows).
- `-r` shows the routing table.
- `-s` displays protocol statistics (as in Windows).
- `-i` displays interface statistics (similar to `-e` on Windows).
- `-e` displays extra information.
- `-c` sets output to update continuously.
### example

For example, the following command shows Internet connections ([[n.protocol.tcp]] and [[n.protocol.udp]]) only: `netstat ‑tu`
