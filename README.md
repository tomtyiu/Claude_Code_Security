## Claude_Code_Security - Setup for least privilege  Claude Code
This is repositiory to provide Claude code security and safety information
Claude Code uses strict read-only permissions by default, but if you want further security, here are some further settings and commands.


## Setup tips
- ensure allow only the workspace folder
- Allow write privileges only for files that need to be edited. Do not permit write access to any OS-related or sensitive files.
- do not allow administration rights if there is sensitive data

## Recommend to run claude code in sandbox mode in WIndows or Linux
```
> wsl2 ## for Windows
> sudo apt-get install bubblewrap socat  #Ubuntu / Debian
#Enable Sandbox
> /sandbox

> claude --settings managed-settings.json
```
## For further information about permission settings, refer: 
- [Claude Code settings](https://code.claude.com/docs/en/settings)

## For best security, recommend to avoid the following commands in Linux/Windows:
- ### Skip all permission prompts (use with caution)
```
claude --dangerously-skip-permissions
```

- ### Enable permission bypassing as an option without immediately activating it. Allows composing with --permission-mode (use with caution)
```
claude --permission-mode plan --allow-dangerously-skip-permissions
```
### Alternative
Please run docker or VM and run sandbox mode for higher security
