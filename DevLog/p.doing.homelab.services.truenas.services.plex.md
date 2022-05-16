---
id: jig9fwrxnzgjbm2vdkm7ugq
title: Plex
desc: ''
updated: 1652679005936
created: 1652643232116
---

## Resources

- [Documentation](https://support.plex.tv/articles/)
- [Full setup guide](https://troypoint.com/plex-media-server-setup-guide/#Media)

## Troubleshooting

If accessing plex from outside your network or if its virtualized on a [[terms.vlan]] and youre accessing it from another [[terms.vlan]] then you need to add a specific piece of text into the configuration file for plex through the TrueNAS CLI

<https://www.truenas.com/community/threads/plex-not-authorized-you-do-not-have-access-to-this-server.96858/post-669513>

Resolved by adding an entry to Plex's `Preferences.xml`:

```xml
allowedNetworks="#.#.#.#/255.255.255.0"
```

File located at: `/mnt/mimisbrunnr/iocage/jails/plex/root/Plex Media Server/Preferences.xml`

## configuration

- File Naming Conventions
  - [Naming Movies](https://support.plex.tv/articles/naming-and-organizing-your-movie-media-files/)
  - [Naming TV Shows](https://support.plex.tv/articles/naming-and-organizing-your-tv-show-files/)
  - [Naming Music Files](https://support.plex.tv/articles/categories/your-media/naming-and-organizing-music-media/)
  - [Naming Media Files](https://support.plex.tv/articles/categories/your-media/naming-and-organizing-personal-media/)
