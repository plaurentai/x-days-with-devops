- Created a temporary user account with an expiration date:

```bash
sudo useradd -e 2026-07-07 tipizo
```

- Verified account expiration details:

```bash
sudo chage -l tipizo
```

- Login to linux server and disabled roo ssh access

```bash
sudo login to username@server
sudo vi /etc/ssh/sshd_config
Change PermitRootLogin no
```

- Restart the sshd server

```bash
sudo systemctl restart ssh