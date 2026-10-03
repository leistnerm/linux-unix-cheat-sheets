# Linux Cheat Sheets

A set of 51 printable, one-page (US Letter) cheat sheets for working on Linux servers. Each sheet covers how to use a command or topic, how to read its output, and a few handy recipes, with a "Remember" tip at the bottom.

Examples assume a GNU/Linux server (Debian/Ubuntu or RHEL/Fedora). Distro- or version-specific details are labelled on the sheets. Sample outputs are realistic but illustrative, so exact spacing and version numbers on your system may differ.

## Contents

- [Text processing](#text-processing)
- [Files and storage](#files-and-storage)
- [Shell, editors and git](#shell-editors-and-git)
- [Networking](#networking)
- [System administration](#system-administration)
- [Packages and tools](#packages-and-tools)
- [Virtualization and containers](#virtualization-and-containers)
- [Security](#security)

## Text processing

| Sheet | Description |
|---|---|
| [diff](diff-cheat-sheet.pdf) | Using `diff` and reading its output, both the default format (`a`/`c`/`d`, `<`/`>`) and unified (`-u`, `@@` hunks) |
| [grep](grep-cheat-sheet.pdf) | Searching text: options, pattern basics, reading `file:line:` output and context lines |
| [sed](sed-cheat-sheet.pdf) | Find and replace, choosing lines, delete/insert/print commands, editing files in place |
| [awk](awk-cheat-sheet.pdf) | Working with columns: fields, built-in variables, patterns, totals and counts |
| [Regular expressions](regex-cheat-sheet.pdf) | One regex reference for grep, sed and awk: classes, anchors, groups, basic vs extended syntax, common patterns |
| [sort, uniq, cut, tr & wc](sort-uniq-cut-tr-wc-cheat-sheet.pdf) | The small pipeline tools, and chaining them, for example finding the top 10 values |
| [xargs](xargs-cheat-sheet.pdf) | Turning lines into command arguments, handling file names with spaces safely, running jobs in parallel |
| [Viewing files & logs](viewing-files-logs-cheat-sheet.pdf) | cat, less, head, `tail -f`/`-F` and watch, plus where logs live and reading compressed logs |

## Files and storage

| Sheet | Description |
|---|---|
| [find](find-cheat-sheet.pdf) | Finding files by name, type, size, age or owner, and acting on them with `-exec` and `-delete` |
| [Permissions (chmod, chown)](permissions-cheat-sheet.pdf) | Reading `ls -l`, octal values like 755 and 644, chmod/chown, special bits and umask |
| [tar & compression](tar-cheat-sheet.pdf) | Creating, listing and extracting archives, recognizing archive types, gzip and zip |
| [rsync](rsync-cheat-sheet.pdf) | Syncing folders locally and over SSH, the trailing-slash rule, dry runs, `--delete`, change codes |
| [Disk & storage](disk-storage-cheat-sheet.pdf) | df, du, lsblk, mounting, `/etc/fstab` fields, and a checklist for a full disk |
| [LVM](lvm-cheat-sheet.pdf) | Physical volumes, volume groups and logical volumes: creating, growing with `lvextend -r`, snapshots |
| [RAID (mdadm) & SMART](raid-smart-cheat-sheet.pdf) | Reading `/proc/mdstat`, replacing a failed disk, and SMART attributes that predict drive failure |
| [ZFS](zfs-cheat-sheet.pdf) | Pools and datasets, reading `zpool status`, properties, snapshots, send/receive backups |

## Shell, editors and git

| Sheet | Description |
|---|---|
| [Pipes & redirection](pipes-redirection-cheat-sheet.pdf) | stdin/stdout/stderr, `>`, `2>&1`, tee, here-docs, why the order matters, exit status |
| [Bash scripting](bash-scripting-cheat-sheet.pdf) | Variables, quoting, `[[ ]]` tests, loops, case, functions, debugging with `bash -x` |
| [Bash shortcuts & history](bash-shortcuts-cheat-sheet.pdf) | Line-editing keys, Ctrl-r history search, `!!`/`!$` history expansion, brace expansion |
| [vim](vim-cheat-sheet.pdf) | Modes, saving and quitting, moving, editing, search and replace, visual mode |
| [tmux](tmux-cheat-sheet.pdf) | Sessions that survive SSH disconnects, windows, panes, the status bar, a starter config |
| [git](git-cheat-sheet.pdf) | The daily loop, reading `git status` and `git log`, branches, remotes, undoing mistakes |

## Networking

| Sheet | Description |
|---|---|
| [ip](ip-cheat-sheet.pdf) | Interfaces, addresses and routes: finding the main IP, reading `ip addr`, temporary changes |
| [Linux bridge](bridge-cheat-sheet.pdf) | How a bridge works, inspecting ports with `bridge link`/`fdb`, port states, building one by hand |
| [Netplan & nmcli](netplan-nmcli-cheat-sheet.pdf) | Making network config permanent: Netplan YAML for a bridge, `netplan try`, nmcli, ifupdown |
| [VLANs & bonding](vlans-bonding-cheat-sheet.pdf) | VLAN interfaces, VLAN-aware bridges, bonding modes, reading `/proc/net/bonding` |
| [ss](ss-cheat-sheet.pdf) | Which ports are listening and who owns them: reading `ss -tulpn`, connection states, filters |
| [Network troubleshooting](network-troubleshooting-cheat-sheet.pdf) | Seven questions in order, from link up to service answering, plus reading ping and dig |
| [DNS on the host](dns-host-cheat-sheet.pdf) | How lookups work, systemd-resolved and `resolvectl`, `/etc/resolv.conf` and `/etc/hosts`, split DNS |
| [curl & wget](curl-wget-cheat-sheet.pdf) | Downloads, API calls, reading `curl -v`, HTTP status codes, testing a site on a specific IP |
| [tcpdump](tcpdump-cheat-sheet.pdf) | Capturing packets, filter syntax, reading TCP lines and flags, saving captures for Wireshark |
| [ssh](ssh-cheat-sheet.pdf) | Keys, `~/.ssh/config`, port forwarding, scp/sftp, file permissions, common errors |
| [Firewall (nftables & iptables)](firewall-cheat-sheet.pdf) | Reading rule listings, common tasks in both tools, ufw/firewalld, avoiding lockouts |

## System administration

| Sheet | Description |
|---|---|
| [systemctl & journalctl](systemctl-journalctl-cheat-sheet.pdf) | Starting, stopping and enabling services, reading `systemctl status`, filtering logs, unit overrides |
| [systemd timers](systemd-timers-cheat-sheet.pdf) | Scheduling jobs with a .service + .timer pair, OnCalendar syntax, `list-timers` |
| [cron](cron-cheat-sheet.pdf) | crontab, the five time fields, `@` shortcuts, why jobs don't run, checking that they ran |
| [Processes (ps, top, kill)](processes-cheat-sheet.pdf) | Reading `ps aux` and `top`, STAT codes, kill signals, nice, lsof, background jobs |
| [Memory & performance](memory-performance-cheat-sheet.pdf) | Reading free, vmstat and iostat, load average, out-of-memory kills, a quick triage table |
| [Users & sudo](users-sudo-cheat-sheet.pdf) | id, adding and changing users and groups, `/etc/passwd`, su vs sudo, sudoers rules |
| [Hardware info](hardware-info-cheat-sheet.pdf) | lscpu, lspci, lsblk, dmidecode, ethtool, sensors, hostnamectl, inxi |
| [Linux directory layout](linux-directories-cheat-sheet.pdf) | What lives in `/etc`, `/var`, `/usr`, `/proc` and the rest, and where to look for things |
| [Boot & recovery](boot-recovery-cheat-sheet.pdf) | GRUB menu edits, rescue vs emergency mode, resetting root, fixing fstab, kernels, boot logs |

## Packages and tools

| Sheet | Description |
|---|---|
| [apt & dpkg](apt-dpkg-cheat-sheet.pdf) | Debian/Ubuntu packages: update vs upgrade, holds, `apt policy`, `dpkg -l`, fixing broken installs |
| [dnf & rpm](dnf-rpm-cheat-sheet.pdf) | RHEL/Fedora packages: dnf history and undo, rpm queries, `rpm -Va`, CRB and EPEL |
| [Extra Linux tools](extra-tools-cheat-sheet.pdf) | 41 useful tools not installed by default (btop, ncdu, mtr, ripgrep, jq…) and how to install them |

## Virtualization and containers

| Sheet | Description |
|---|---|
| [Docker & Podman](docker-podman-cheat-sheet.pdf) | Running containers, reading `docker ps`, volumes, compose, Podman differences |
| [KVM & virsh](kvm-virsh-cheat-sheet.pdf) | Managing VMs with virsh, attaching a VM to a bridge, virt-install, snapshots, qemu-img |
| [Proxmox VE (qm & pct)](proxmox-cheat-sheet.pdf) | VMs and containers from the Proxmox shell, host commands, backups, the vmbr0 bridge |

## Security

| Sheet | Description |
|---|---|
| [openssl](openssl-cheat-sheet.pdf) | Checking a site's certificate and expiry, reading cert files, keys and CSRs, converting formats |
| [fail2ban](fail2ban-cheat-sheet.pdf) | Reading jail status, banning and unbanning IPs, `jail.local` setup, testing filters |
| [SELinux & AppArmor](selinux-apparmor-cheat-sheet.pdf) | Modes, labels, reading denials, common fixes in order, `aa-status` |
