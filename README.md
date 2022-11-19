# My Windows Configuration Files

**Warning:**

These are my private notes, untidy & disorganized.

I do not update this, so entries may be outdated.

---
Mostly a copy of: $ENV:APPDATA\Microsoft\Windows\PowerShell\PSReadLine\ConsoleHost_history.txt

## Setup Github

Here is a good guide: https://docs.github.com/en/authentication/troubleshooting-ssh/using-ssh-over-the-https-port

```
ssh-keygen.exe -t ed25519 -C "${ENV:USERNAME}@${ENV:USERDOMAIN}"

ssh -T -p 443 git@ssh.github.com

git remote set-url --push origin 'ssh://git@ssh.github.com:443/philippweber/WindowsConfig.git'
```

## WSL

WSL related commands

