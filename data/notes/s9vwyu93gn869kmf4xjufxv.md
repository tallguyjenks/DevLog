

## Tips

In the Server view, the `Datacenter` option is for settings that affect all your nodes. In essence the "tree" view allows setting editing for all children under the parent item.

## VM Templates

<!-- markdownlint-disable MD031 -->
<!-- markdownlint-disable MD003 -->
<!-- markdownlint-disable MD022 -->
<!-- markdownlint-disable MD023 -->

When you have a default VM config you like, power down the VM, right click, Convert to template.

It can no longer be used as a VM but you can clone from that template

- Mode:
  - Linked clone: dependent child on the template with cascading downstream changes
  - Full Clone: independent entity
    - After cloning these steps will reset important information
      - Change Hostname
        - `sudo vim /etc/hostname`
      - Change hosts file
        - `sudo vim /etc/hosts`
      - Reset Machine ID
        -  
        ```bash
        rm -f /etc/machine-id /var/lib/dbus/machine-id
        dbus-uuidgen --ensure=/etc/machine-id
        dbus-uuidgen --ensure
        ```
      - Regenerate [[n.protocol.ssh]] keys
        -  
        ```bash
        regen ssh keys
        sudo rm /etc/ssh/ssh_host_*
        sudo dpkg-reconfigure openssh-server
        ```

<!-- markdownlint-enable MD031 -->
<!-- markdownlint-enable MD003 -->
<!-- markdownlint-enable MD022 -->
<!-- markdownlint-enable MD023 -->
