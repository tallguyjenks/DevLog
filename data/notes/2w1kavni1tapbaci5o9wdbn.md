

`F`ully `Q`ualified `D`omain `N`ame

## example

> nut.widget.com

## Details

An FQDN is made up of the host name and a domain suffix. 

In the example, the host name is `nut` and the domain suffix is `widget.com`. 

This domain suffix consists of the domain name widget within the top-level domain ([[terms.tld]]) `.com`.
A domain suffix could also contain subdomains between the host and domain name. 
The trailing dot or period represents the root of the hierarchy.

## Rules

- The host name must be unique within the domain.
- The total length of an FQDN cannot exceed 253 characters, 
    - with each label (part of the name defined by a period) no more than 63 characters (excluding the periods).
- A DNS label should use letter, digit, and hyphen characters only. 
    - A label should not start with a hyphen. Punctuation characters such as the period (.) or forward slash (/) should not be used.
- DNS labels are not case sensitive.

## Find your FQDN

### Windows

```shell
ipconfig /all
```

### Linux

```bash
hostname -fqdn
```
