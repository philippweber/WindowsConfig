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

