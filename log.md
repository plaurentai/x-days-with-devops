
# DevOps Engineer

## Prep my DevOps environment

---

### Install Linux and Configure My Raspberry Pi Servers

#### May 21, 2026

**Focus:** Installing and configuring Ubuntu Server 24.04.4 LTS on Raspberry Pi 4

**Progress:**

- Installed Ubuntu Server 24.04.4 LTS by flashing the SD card
- Configured a static IP address
- Logged into the server and completed initial setup
- Created both interactive and non-interactive users
- Updated Ubuntu packages and system dependencies
- Configured SSH key authentication
- Hardened SSH access for secure remote administration
- Explored and validated the server environment

**Thoughts:**

Today was very hands-on and a great start to the challenge. I successfully brought my Raspberry Pi server online and completed the initial operating system setup. I updated the system, created new users, assigned a static IP address, and secured remote access by configuring SSH.

This was more than just installing Linux—it was the foundation for building my Cloud DevOps home lab. I spent time exploring the environment and understanding how the pieces fit together before moving on to automation and infrastructure projects.

**Work & Resources**:\
![Installation](resources/cli/linux/pi_installation.md)

---

### Day 02: Temporary User Setup with Expiry

#### May 22, 2026

**Focus:** Creating Linux user accounts with an expiration date for temporary access management.

**Progress:**
- Connected remotely to the Raspberry Pi server
- Created a Linux user account with a predefined expiration date
- Verified the account and confirmed the expiration settings

**Hands-on:**
- Created a temporary user account with an expiration date:

```bash
sudo useradd -e 2026-07-07 tipizo
```

- Verified account expiration details:

```bash
sudo chage -l tipizo
```

**Thoughts:**

Today’s exercise focused on user lifecycle management in Linux. One practical scenario is granting temporary server access to a developer, contractor, or support engineer for a limited period of time.

Instead of manually remembering to remove access later, Linux allows user accounts to be created with an expiration date built in. Once the expiration date is reached, the account automatically becomes inactive.

This approach improves security, reduces operational overhead, and helps enforce the principle of least privilege. It also demonstrates how system administration and access management become increasingly important as infrastructure grows.

**Work & Resources:**
![Useful commands](resources/cli/linux/bible.md)

---


# Day XX - Title

#### Month Month XX, 2021

**Focus**:

**Progress**:

**Thoughts**:

**Work & Resources:**::
