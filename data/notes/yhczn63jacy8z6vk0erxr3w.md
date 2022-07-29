

## Resources

- <https://youtu.be/LxdCzfF77t4>

## Using iLO

### From scratch

- enter iLO menu with `F8` after POST
- in the `[file]` option there is a reset to default settings
- as long as the above points are handled then you can get a new [[n.protocol.dhcp]] DORA process going so that you can use intelligent provisioning via `F10` to boot from an `.iso` on the remote machine.
- **NOTE:** to use the virtual media install you need an iLO license, a trial license should work just fine

### Caveats and Gotchyas

- Make sure the iLO port is connected to a port on the switch that is on the same VLAN as the remote device attempting to connect to it.
- you can let [[n.protocol.dhcp]] handle DORA and configuration and then boot from virtual media via iLO
- Booting from virtual media is an option in the `F9` menu that needs to be enabled before attempting iLO boot
