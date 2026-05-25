
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
### Day 03 - Secure Root SSH Access

#### May 23, 2026

---

## Focus

Today’s learning focused on logging into multiple Linux servers and improving security by disabling direct root SSH access.

## Progress

- Logged into all application servers
- Disabled direct root SSH access on each server
- Reinforced Linux server access and security fundamentals

---

## Thoughts

Today was a shorter learning session, but it covered an important security concept.

One of the key lessons was understanding why direct root SSH access should be disabled whenever possible. Allowing remote root login increases the attack surface and can create unnecessary security risks. Restricting root access encourages the use of standard user accounts with privilege escalation when administrative actions are required.

Although the task itself was straightforward, it reinforced the importance of following security best practices and building secure defaults into system administration workflows.

Small improvements like these play a significant role in strengthening the overall security posture of Linux environments.

---

## Key Takeaways

- Avoid allowing direct root SSH access
- Use standard user accounts and elevate privileges only when necessary
- Security hardening starts with simple configuration changes
- Consistent security practices reduce operational risk

---

## Work & Resources

![Useful commands](resources/cli/linux/bible.md)


---

### Day 4 - Script Execution Permissions

#### May 24, 2026

---

## Focus

Granting executable permissions to the `/tmp/movedata.sh` script on the application server.

## Scenario

The system administrator developed a new Bash script named `movedata.sh` and distributed it across all application servers. However, the script lacked executable permissions on `raspberry-02`, preventing users from running it.

---

## Progress

* Logged into `raspberry-02`
* Checked the current permissions of the script:

```bash
ls -l movedata.sh
---------- 1 root root 15 May 25 17:52 movedata.sh
```

* Attempted to execute the script:

```bash
./movedata.sh
```

Output:

```bash
bash: ./movedata.sh: Permission denied
```

* Updated the permissions so all users could read and execute the script:

```bash
sudo chmod a+rx movedata.sh
```

* Verified the updated permissions:

```bash
ls -l movedata.sh
-r-xr-xr-x 1 root root 15 May 25 17:52 movedata.sh
```

* Executed the script successfully:

```bash
./movedata.sh
```

Output:

```bash
Move Data
```

---

## Thoughts

This was a short lesson, but an important one.

It reinforced the idea that even if a script is written correctly, it still cannot run unless the operating system grants the proper permissions.

Seeing the `Permission denied` error and resolving it by updating file permissions made the concept more memorable than simply reading about it. Exercises like this help connect Linux fundamentals with real-world system administration tasks.

Understanding permissions is an essential skill because it affects security, automation, deployment, and day-to-day server operations.

---

## Key Takeaways

* Linux controls access through **read (`r`)**, **write (`w`)**, and **execute (`x`)** permissions
* A script requires the **execute** permission to run directly
* `chmod` modifies file permissions
* `a+rx` grants **read and execute permissions to all users**
* Use `ls -l` to inspect current permissions
* Permission errors are often quick to fix once you understand Linux permission models

---

## Work & Resources:

* Practice additional `chmod` permission combinations
* Learn numeric permissions (`755`, `644`, `700`)
* Explore ownership using `chown` and `chgrp`


---

### Day 5 - Installing and Configuring Rocky Linux on Pi 4

#### May 25, 2026

---

## Focus

Today’s learning focused on installing and configuring a Linux distribution on the Raspberry Pi that closely aligns with the Red Hat ecosystem. I chose **Rocky Linux** to gain more exposure to enterprise-style Linux administration and workflows.

## Progress

- Downloaded **Balena Etcher** and used it to flash the SD card for the Raspberry Pi 4
- Remotely logged into Rocky Linux
- Changed the default password
- Updated the operating system packages
- Configured the hostname
- Set the correct timezone
- Configured networking (LAN and Wi-Fi)
- Expanded the filesystem
- Installed common system administration tools

---

## Thoughts

Today was a valuable hands-on learning experience.

One of my goals is to expose myself to different Linux distributions and administration styles. Running multiple Linux flavors in my home environment gives me broader practical experience and helps me become more comfortable adapting to different systems.

Choosing **Rocky Linux** was intentional because it is closely aligned with **Red Hat Enterprise Linux (RHEL)**, which is widely used across enterprise environments. Working through the installation and configuration process gave me exposure to foundational Linux administration tasks that system administrators perform regularly.

Another exciting part of this project is that I documented the entire setup process and plan to share it with a broader audience. Documenting and teaching what I learn helps reinforce concepts and build stronger operational habits.

---

## Key Takeaways

- Installing Linux manually improves understanding of system setup and configuration
- Enterprise Linux distributions share common administration workflows
- Basic system configuration is an important operational skill
- Documenting and sharing work strengthens learning and creates reusable references
- Hands-on practice builds confidence faster than theory alone

---

## Work & Resources

- Raspberry Pi 4
- Rocky Linux
- Balena Etcher
- SSH remote access
- Linux system administration tools

![Rocky Linux Installation and configuration](resources/cli/linux/rockylinux.md)

---

### Day XX - Title

#### Month Month XX, 2021

**Focus**:

**Progress**:

**Thoughts**:

**Key Takeaways**

**Work & Resources:**
