# WSL install & usage

Follow this guide: https://learn.microsoft.com/en-us/windows/wsl/install

## Installation
```
# Start PowerShell as admin
Start-Process -Verb:runas powershell

wsl --install
````

## Usage
```
wsl --status

wsl --list --online

wsl --install --distribution Ubuntu

wsl --list

wsl --list --all --verbose

# Start distribution
wsl --distribution ubuntu

wsl --help
```

# Get systemd running in Ubuntu
```bash
# Solutions here:
#  * https://discourse.ubuntu.com/t/using-snapd-in-wsl2/12113
#  * https://github.com/microsoft/WSL/issues/5126

# Warning: DISPLAY & Co. might no longer work, restart with "wsl -t ubuntu"

# Install requirements
sudo apt-get update && sudo apt-get install -yqq daemonize dbus-user-session fontconfig
# Create new PID namespace
sudo daemonize /usr/bin/unshare --fork --pid --mount-proc /lib/systemd/systemd --system-unit=basic.target
# Enter namespace
exec sudo nsenter -t $(pidof systemd) -a su - $LOGNAME
```

