---
id: HPvfeFCeGrY5emhbsnnFe
title: Nslookup
desc: ''
updated: 1641887997833
created: 1641887787958
---


## Details

In a Windows environment, you can troubleshoot [[focus.networking.protocol.dns]] with the `nslookup` command, either interactively or from the command prompt.

```powershell
nslookup -Option Host Server
```

## Usage

```powershell
nslookup -type=mx widget.com 8.8.8.8
```

## Powershell DNS resolution

### Resolve Host

```powershell
Resolve-DnsName host
```

### Resolve host using the same method as the Windows client

```powershell
Resolve-DnsName host -NoHostsFile
```

### Resolve host but without using any entries from the HOSTS file in the local cache

```powershell
Resolve-DnsName host -DnsOnly
```

### Resolve 

```powershell

```


