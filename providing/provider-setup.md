# Provider Setup

### Contents

- [Setup](#setting-up-a-provider-node)
  - [Linux](#on-linux)
  - [Windows](#on-windows)
  - [macOS](#on-macos)
  - [Raspberry Pi](#on-raspberry-pi)
- [Settings](#change-settings-on-your-node)
  - [Pricing](#pricing)
  - [Allocated Resources](#allocated-resources)
  - [Make it run as a service](#make-it-run-as-a-service)
- [Experimental Contributions](#experimental-contributions)
  - [Providing Logs](#providing-logs)
  - [Rewards](#rewards)
- [Credits](#credits)

## Setting up a provider node

### On Linux
Install the latest stable release by invoking this command:

``curl -sSf https://join.golem.network/as-provider | bash -``

##### Troubles? Refer to [this](https://handbook.golem.network/troubleshooting/provider-troubleshooting) page or join the [discord](https://chat.golem.network).

### On Windows
1. Install VMWare [here](https://www.vmware.com/products/workstation-player.html).
2. Download Ubuntu [18.04 LTS](https://releases.ubuntu.com/18.04/) or [20.04 LTS](https://releases.ubuntu.com/20.04/).
3. Set it up in VMWare - [video guide](https://youtube.com/watch?v=9rUhGWijf9U).
4. Make sure KVM is enabled by following these instructions in VMWare:
> Power off the (virtual) machine > Right click > Settings > Hardware > Processors > Virtualize Intel VT-x/EPT or AMD-V/RVI
5. Power on the machine/create an account/setup it how you want.
6. Open the terminal and enter this command:

``curl -sSf https://join.golem.network/as-provider | bash -``

##### Troubles? Refer to [this](https://handbook.golem.network/troubleshooting/provider-troubleshooting) page or join the [discord](https://chat.golem.network).

### On macOS
Currently not supported

### On Raspberry Pi
See install instructions [here](https://github.com/MarijnStevens/yagna-binaries).

## Change settings on your node

### Pricing
Open a new terminal window and set prices for the seperate commands by invoking these commands:

```css
golemsp settings set --starting-fee <price>
golemsp settings set --env-per-hour <price>
golemsp settings set --cpu-per-hour <price>
```
Then, restart the node with `golemsp stop`, and confirm with `golemsp status` or by locating your node [here](https://golemstats.com/).

### Allocated Resources
Open a new terminal window and set prices for the seperate commands by invoking these commands:

```css
golemsp settings set --node-name <node-name>             
golemsp settings set --cores <num>                       Number of shared CPU cores
golemsp settings set --memory <bytes (like "1.5GiB")>    Size of shared RAM
golemsp settings set --disk <bytes (like "1.5GiB")>      Size of shared disk space
golemsp settings set --account <account>                 Account for payments [env: YA_ACCOUNT=]
golemsp settings set --payment-network <network>         Payment network [env: YA_PAYMENT_NETWORK=]  [default: mainnet]
                                                         [possible values: mainnet, rinkeby]
```
Then, restart the node with `golemsp stop`, and confirm with `golemsp status` or by locating your node [here](https://golemstats.com/).

### Make it run as a service
If you want to run golem as an isolated user account you can run:
```bash
# Create a new user with home folder
useradd -m golem -s /bin/bash
# Add user to kvm group
usermod -aG kvm golem
# Switch to new account
su -l golem
# Run install script
curl -sSf https://join.golem.network/as-provider | bash -
```

A sample systemd service (e.g. `/etc/systemd/system/golem.service`):
```
[Unit]
Description=Golem
After=network.target

[Service]
User=golem
Group=golem
Environment=PATH=/home/golem/.local/bin:/home/golem/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin
Restart=on-failure
WorkingDirectory=/home/golem
ExecStart=/home/golem/.local/bin/golemsp run

# Increase Systemd Service Security Score
LockPersonality=true
NoNewPrivileges=true
PrivateUsers=true
ProtectControlGroups=true
ProtectHostname=true
ProtectKernelLogs=true
ProtectKernelModules=true
ProtectKernelTunables=true
RemoveIPC=true
RestrictNamespaces=true
RestrictRealtime=true
RestrictSUIDSGID=true
RestrictAddressFamilies=AF_INET AF_INET6 AF_NETLINK AF_PACKET AF_UNIX
SystemCallArchitectures=native
SystemCallFilter=~@clock @debug @module @mount @raw-io @reboot @privileged @obsolete
CapabilityBoundingSet=~CAP_SYS_ADMIN CAP_SYS_PTRACE CAP_SETUID CAP_SETGID CAP_SETPCAP CAP_NET_ADMIN CAP_CHOWN CAP_FSETID CAP_SETFCAP CAP_FOWNER CAP_IPC_OWNER CAP_DAC_OVERRIDE CAP_DAC_READ_SEARCH CAP_KILL CAP_SYS_BOOT

[Install]
WantedBy=default.target
```

This is a semi-locked down systemd service with a `systemd-analyze security` score of `4.0`

`Overall exposure level for golem.service: 4.0 OK`

Start it with:
```bash
systemctl enable golem.service
systemctl start golem.service 
```

## Experimental Contributions
Right now, there is a payment bug stopping some transactions to go through. There will always be issues to resolve, and feedback to be given. With that being said, you can help issues get resolved by contributing time, logs, and other node-specific information.

### Providing Logs
##### Use of Experimental Versions
Sometimes, logs are only looked for in releases that are not yet officially released. These are so called Release Candidates, and can be found [here](https://github.com/golemfactory/yagna/releases). 

Installing the one you want is as simple as running this command:

`curl -sSf https://join.golem.network/as-provider | YA_INSTALLER_CORE=pre-rel-vX.X.X-rcX bash -`

where `vX.X.X-rcX` is swapped for something in the lines of `v0.6.6-rc1`.

##### Collecting logs
To start collecting logs, simply start golemsp with this command:

`RUST_LOG=debug,ya_runtime_api=info,ya_runtime_vm=info,ya_payment=trace golemsp run --payment-network mainnet --subnet public-beta`

##### Errors currently sought-after
Current issues being looked for are listed [here](https://github.com/golemfactory/yagna-triage/issues).

If you're unsure on which errors you've found, any logs are greatly appreciated and sorting can be done by somebody else.

##### Sending log files
Once you've found a sought-after error, join the [discord](https://chat.golem.network) and send them privately to `@Phillip#9780` or publicly in `#providers`.

### Rewards
Every month, two users are picked for being helpful for how much feedback they have given on the technology. This, per the [CIP](https://blog.golemproject.net/community-incentives-program/), rewards these users with 1,000 GLM each!

## Credits
Written by figurestudios

Contribution by MysticRyuujin
