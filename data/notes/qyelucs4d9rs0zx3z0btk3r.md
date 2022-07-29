

## Inputs

## Notes

Today i read from a comment on a youtube video of mine from another user that a modern IT practice these days is to forgo installing a dedicated OS like a linux disto and instead to just put a [[hypervisor]] like [[proxmox]] on the bare metal and use that to run [[VM's|virtual machine]] and [[docker]] containers.

So now i'm going to need to look more into how to set up [[proxmox]] and more about [[docker]] containers and [[VM's|virtual machine]]

To help with monthly reviews in dendron i just made a [[s.apps.vscode]] task to get me the files edited that month from the dendron vault!

```json
{
    "version": "2.0.0",
    "tasks": [
        {
            "label": "Notes Made This Month",
            "type": "shell",
            "command": "cd \"${workspaceFolder}\" && lsd -lA *.md | awk '{print $7,$10,$NF}' | grep \"$(date +\"%b %Y\")\" | awk '{print \"[[\"$NF\"]]\"}'"
        }
    ]
}
```
