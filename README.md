This is a fork of the nice working extension from https://github.com/jyvern/ulauncher-ssh (who forked https://github.com/jetbug123/ulauncher-ssh).
Differences are
* Adding an additional parameter for the terminal command to start MATE Terminal with a custom profile (--profile=YOUR_PROFILE_NAME)

# Original README content

A [Ulauncher](https://ulauncher.io) extension to start ssh connections.

![extension screenshot](https://imgur.com/glgIVgM.png)

I obtained the icon from [shareicon.net](https://www.shareicon.net/terminal-94589)

## How to add SSH Connections
This extension builds the connection list automatically by extracting "Host" entries in the current user's ~/.ssh/config file.

For examples and details on how to add entries to the ssh config file, see for instance [this link](https://www.cyberciti.biz/faq/create-ssh-config-file-on-linux-unix/)

This is a typical host entry in .ssh/config:

```
## Home nas server ##
Host nas
     HostName 192.168.1.100
     User root
```

If you have configured [passwordless ssh login](https://linuxize.com/post/how-to-setup-passwordless-ssh-login/) for this host/server, clicking on the 'nas' host entry in ulauncher will open a terminal and log you in the server automatically.

## Terminal Workarounds
### Kitty
Put this wrapper script in a file in your PATH and use it as terminal:
```
#!/usr/bin/env python
import subprocess
import sys

subprocess.Popen("/usr/bin/kitty " + sys.argv[2], shell=True)
```
