- Created a temporary user account with an expiration date:

```bash
sudo useradd -e 2026-07-07 tipizo
```

- Verified account expiration details:

```bash
sudo chage -l tipizo
```