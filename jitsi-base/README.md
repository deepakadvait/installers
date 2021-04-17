# Jitsi Base Installer

`jitsi-base-installer` installs a simple standalone Jitsi server. This script
guides the user during the installation to avoid potential problems.

## Supported distributions

- Debian 10 Buster
- Ubuntu 20.04 Focal Fossa

## Usage

- Don't use this script on a working production server.
- Run it as `root`
- Follow the recommendations during the installation

### use root account

Switch to the `root` account if you are not already `root`. Use one of the
following command according to your system

```bash
sudo su -l
```

or

```bash
su -l
```

### download installer

```bash
apt-get update
apt-get install wget

wget -O jitsi-base-installer https://raw.githubusercontent.com/jitsi-contrib/installers/main/jitsi-base/jitsi-base-installer
```

### host addresses

- Create DNS A record for Jitsi. For example `jitsi.yourdomain.com`
- Create DNS A record for TURN. For example `turn.yourdomain.com`
- Jitsi address and TURN address must be different and don't use IP as address.
- Set related environment variables before starting the installer

```bash
export JITSI_HOST=jitsi.yourdomain.com
export TURN_HOST=turn.yourdomain.com
```

### run the installer

```bash
bash jitsi-base-installer
```