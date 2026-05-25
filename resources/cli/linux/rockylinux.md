# Rocky Linux Initial Setup on Raspberry Pi 4

## Login

```bash
username: rocky
password: default
```

---

## Become Root

Immediately switch to the root account:

```bash
sudo -i
```

---

## Change the Default Password

Change the default account password for security:

```bash
passwd
```

---

## Update the Entire System

Install the latest package updates:

```bash
sudo dnf update -y
reboot
```

After reboot, run:

```bash
sudo dnf upgrade -y
```

---

## Configure Hostname

Set a custom hostname:

```bash
sudo hostnamectl set-hostname rocky-pi4
```

Verify the hostname:

```bash
hostnamectl
```

---

## Configure Timezone

List available time zones:

```bash
timedatectl list-timezones
```

Set the desired timezone:

```bash
sudo timedatectl set-timezone America/New_York
```

Enable automatic time synchronization:

```bash
sudo timedatectl set-ntp true
```

Verify configuration:

```bash
timedatectl
```

---

# Configure Networking

## Check Network Interfaces

```bash
nmcli device status
```

---

## Connect to Wi-Fi

List available Wi-Fi networks:

```bash
nmcli device wifi list
```

Connect to a network:

```bash
sudo nmcli device wifi connect "Your WiFi" password "YourPassword"
```

---

## Verify IP Address

```bash
ip a
```

---

## Expand Root Filesystem

Check disk usage:

```bash
df -h
```

Expand the filesystem:

```bash
sudo rootfs-expand
```

Reboot after expansion:

```bash
reboot
```

Verify expansion:

```bash
df -h
```

---

# Install Common Administration Tools

```bash
sudo dnf install -y \
vim \
git \
curl \
wget \
htop \
tmux \
tree \
net-tools \
bash-completion
```

---

# Create a Non-Root Administrative User

Create a new user:

```bash
sudo useradd -m devops
```

Set a password:

```bash
sudo passwd devops
```

Grant administrative privileges:

```bash
sudo usermod -aG wheel devops
```

Verify group membership:

```bash
groups devops
```

---

## Final Validation Checklist

* [ ] Password changed
* [ ] System updated
* [ ] Hostname configured
* [ ] Timezone configured
* [ ] NTP enabled
* [ ] Network connected
* [ ] Filesystem expanded
* [ ] Admin tools installed
* [ ] Non-root admin account created

```
```
