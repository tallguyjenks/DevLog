

This file is sourced upon system login so normally it should only be executed once upon a successful login into the system.

These profile files `.[zx]profile` can also just point to where you want the real file content to be such as 

`$HOME/.xprofile`:

```
.config/x11/xprofile
```

because this file is run once on system login it should also be the trigger to start the graphical environment in the tty.
