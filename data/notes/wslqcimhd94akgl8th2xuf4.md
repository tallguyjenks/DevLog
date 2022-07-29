


## Details

In a Windows environment, you can troubleshoot [[n.protocol.dns]] with the `nslookup` command, either interactively or from the command prompt.

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

### Resolve host using only the DNS server 

```powershell
-Server IPofDNSserver
```

## Additional

It is also possible to search DNS for records other than [[n.protocol.dns.resource-records.a]] or [[n.protocol.dns.resource-records.aaaa]] records. For example, to show only Mail Exchange records in a specific domain, use the cmdlet:

```powershell
Resolve-DnsName domain-Type MX
```


