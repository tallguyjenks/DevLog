---
id: Ga7bXwoDLwwapP05NOYbQ
title: Networking
desc: ''
updated: 2022-01-01 2239
created: 2021-11-15 1320
publish: true
aliases:
  - Home Lab
  - Network
---

## Resources

---

- TODO [Visualize Your Network with GNS3](https://www.gns3.com/)
- TODO [Observium SNMP](https://observium.org/)
- TODO [Wireshark](https://www.wireshark.org/)
- TODO Nextclound
- TODO `iperf`
- TODO [nmap](https://nmap.org/download.html)
- TODO `dig`
- TODO [grafana and loki for logging](https://youtu.be/h_GGd7HfKQ8)
- TODO [Lansweeper IT Asset Management Software?](https://www.lansweeper.com/)
- TODO portainer
- TODO [heimdall](https://github.com/linuxserver/Heimdall) (the dashboard for all your services)
- TODO [guacamole](https://guacamole.apache.org/) for SSH'ing into your services easier [example](https://youtu.be/E3aVxNtxFsU)
- TODO [truenas](https://www.truenas.com/)

---

- Patch Panel
  - [[+ 2021-11-15 What is a Patch Panel Do You Need One]]
- Server
  - [ ] [Projects to Build](https://youtu.be/SVQmzaSabEQ)
    - fire wall (pfsense)
    - VPN
    - backup server (also push to remote cloud like one drive)
    - database server (postgres)
    - docker containers (docker)
    - virtual machines
    - Pi-Hole
    - FTP server (filezilla?)
    - web server (host a website)
    - IOT (<https://www.home-assistant.io/>)
    - running `iperf` on the server as a background process to run internal network speedtests instead of outside services
    - nextcloud (calendar services?)
    - photo prism
    - home assistant
    - ansible IAC infrastructure as code
    - [grafana loki for logging](https://youtu.be/h_GGd7HfKQ8)
    - heimdall service?
- [Cat6 Cabling](https://youtu.be/NWhoJp8UQpo)
  - UTP - Unshielded Twisted Pair
  - RJ45 - The jack Tip of the cable
  - 8 wires, 4 pairs of 2 twisted wires
  - 2 standards for cable T-568A & T-568B
    - B is more widely used, and both ends must be the same standard
- IP addressing conventions
  - 1st Network IP Address --> Default Gateway i.e. Router
  - Try to use IP Addresses in sequential order
  - Try to separate servers from clients
    - Like `197.156.4.10` to `197.154.4.19` for servers
    - and `197.156.4.200` to `197.156.4.254` for clients
  - Document these things for future tech's
- [[Domain Name System|DNS]]
- Useful Resources
  - [Wolfgangs channel - what he's running on his home server](https://youtu.be/f5jNJDaztqk)
  - [affordable gear?](https://www.pcliquidations.com/p48428-amd-radeon-r5-340x?r=160164167166161&utm_source=bing&utm_medium=cpc&utm_campaign=CPCS_PCLiq-Shopping&utm_term=4581046488142443&utm_content=Products#)
