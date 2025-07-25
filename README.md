# How to create agent flows with a local Flowise environment

## Requirements

### Homebrew (MacOS)

Paste that in a macOS Terminal or Linux shell prompt:<br>
`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`
<br>
For more informations visit [Homebrew](https://brew.sh)

### Chocolatey (Windows)

Paste that in a administrative shell:<br>
`Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))`
<br>
For more informations visit [Chocolatey](https://chocolatey.org/install)

### Podman (Docker)

Make sure that you have installed Docker or Podman.<br> If not use one of the following commands:<br><br>
**For Windows:**<br>
`choco install podman-desktop`<br>
`choco install docker-desktop`
<br><br>
**For MacOS:**<br>
`brew install --cask podman-desktop`<br>
`brew install --cask docker-desktop`
