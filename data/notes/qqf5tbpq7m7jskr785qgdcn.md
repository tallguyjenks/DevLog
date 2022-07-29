

## Details

<https://nmap.org/>

Port scanning tool

![nmap](/assets/images/2022-01-10-22-18-19.png)

## Usage

```
nmap <IP subnet / address> [switches]
```

With no switches like this the default behavior of [[cli.cmd.nmap]] is to [[cli.cmd.ping]] and send a [[n.protocol.tcp]] [[terms.ack]] packet to ports [[n.port.80]] and [[n.port.443]] to determine whether a host is present.

If you want to perform only host discovery, you can use `nmap -sn` (or `-sP` in earlier versions) to suppress the port scan.

## Port scanning

- [[n.protocol.tcp]] [[terms.syn]] (`-sS`)
    - This is a fast technique (also referred to as half-open scanning) as the scanning host requests a connection without acknowledging it. 
    - The target's response to the scan's [[terms.syn]] packet identifies the port state.
- [[n.protocol.tcp]] connect (`-sT`)
    - A half-open scan requires [[cli.cmd.nmap]] to have privileged access to the network driver so that it can craft packets. 
    - If privileged access is not available, [[cli.cmd.nmap]] must use the OS to attempt a full [[n.protocol.tcp]] connection. 
    - This type of scan is less stealthy.
- [[n.protocol.udp]] scans (`-sU`)
    - Scan [[n.protocol.udp]] ports. 
    - As these do not use [[terms.ack]]s, [[cli.cmd.nmap]] needs to wait for a response or timeout to determine the port state, so [[n.protocol.udp]] scanning can take a long time. 
    - A [[n.protocol.udp]] scan can be combined with a [[n.protocol.tcp]] scan.
- Port range (`-p`)
    - By default, [[cli.cmd.nmap]] scans 1,000 commonly used ports. 
    - Use the `-p` argument to specify a port range. 
    - You can also use `--top-ports` n, where n is the number of commonly used ports to scan. 
    - The frequency statistics for determining how commonly a port is used are stored in the [[cli.cmd.nmap]]-services configuration file.
