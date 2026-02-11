# Claude_Code_Security
Setup for least privilege  Claude code

# This is repositiory to provide Claude code security and safety information
## Recommend to run claude code in sandbox mode in WIndows or Linux
```
wsl2 ## for Windows
sudo apt-get install bubblewrap socat  #Ubuntu / Debian
#Enable Sandbox
> /sandbox
> claude --settings managed-settings.json
```
For further information about permission settings, refer: 
- [Claude Code settings](https://code.claude.com/docs/en/settings)

