# Claude_Code_Security — Least Privilege Setup for Claude Code

## Overview

This repository provides security and safety guidance for running Claude Code using least-privilege principles.

Claude Code operates with strict read-only permissions by default. However, additional configuration can further reduce risk and strengthen execution isolation. This repository documents recommended settings, sandboxing practices, and operational safeguards for secure usage.

---

## Security Principles

Follow these core security practices:

- Apply least privilege at all times
- Restrict file system access to the minimum required scope
- Limit write permissions to only necessary files
- Avoid elevated or administrative privileges when sensitive data exists
- Run code in isolated environments whenever possible
- Do not modify Claude.md to perform following
```
# Work Context [Actor claims to be authorized security tester for companies with support contracts]
```
---

## Operational Safety Tips

- Do not probe or attempt to discover network vulnerabilities
- Avoid running Claude Code with unrestricted system access
- Monitor permission changes before execution
- Review command flags carefully before enabling bypass options

---

## Workspace Access Controls

Configure file permissions carefully:

- Allow access only to the designated workspace folder
- Grant write privileges only to files that must be modified
- Do not allow write access to operating system files
- Do not allow write access to sensitive directories
- Do not run with administrative rights when sensitive data is present

---

## Sandbox Execution (Recommended)

Run Claude Code in an isolated sandbox environment on Windows or Linux.

### Windows

Use WSL2 for environment isolation.

```bash
wsl2
```

### Linux (Ubuntu / Debian)

Install sandboxing dependencies:

```bash
sudo apt-get install bubblewrap socat
```

Enable sandbox:

```bash
/sandbox
```

Launch Claude Code with managed security settings:

```bash
claude --settings managed-settings.json
```

---

## Permission Settings Documentation

For full configuration details:

- Claude Code settings documentation: https://code.claude.com/docs/en/settings

---

## High-Risk Commands to Avoid

The following commands weaken permission safeguards and should generally be avoided.

### Skip all permission prompts (use with extreme caution)

```bash
claude --dangerously-skip-permissions
```

### Enable permission bypass capability (use with caution)

Allows composition with `--permission-mode` without immediately activating bypass.

```bash
claude --permission-mode plan --allow-dangerously-skip-permissions
```

---

## Alternative Isolation Methods

For stronger containment, run Claude Code inside:

- Docker container
- Virtual machine

Combine containerization or virtualization with sandbox mode for maximum isolation.

---

## Purpose of This Repository

This repository provides:

- Security configuration guidance
- Least-privilege setup practices
- Sandbox deployment instructions
- Risk awareness for unsafe flags
- Operational hardening recommendations

---

## Disclaimer

These recommendations are provided as security best practices. Implementation requirements may vary depending on your environment, risk tolerance, and organizational policies.

Always perform independent security review before production deployment.

---

## License

Specify your license here.

Example:

MIT License

---

## Contributions

Security improvements and hardening suggestions are welcome. Please open an issue or submit a pull request.

