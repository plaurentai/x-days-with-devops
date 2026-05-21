# This works for raspberry pi version 4 and 5

Assuming you have the followings:
    - a rapsberry pi 4
    - an sdcard
    - You know how to connect your pi to your home network

# Flashing the SDcard

Download and install rpi-imager to flash the SDCard. Make you install ubuntu version 24.04.4 LTS

# Boot up your Pi with the new iamge
You will be ask to enter your username and password

# Connect to your pi
ssh admin@ip_address

# update everything
sudo apt update
sudo apt upgrade -y
sudo apt autoremove -y

# Reboot
sudo reboot

# Assign a static IP
ip a
sudo vi /etc/netplan/50-cloud-init.yaml

network:
  version: 2
  ethernets:
    eth0:
      dhcp4: false
      address:
        - 192.168.0.100
      routes:
        - to: default
          via 192.168.0.1
      nameserver:
        addresses:
          - 1.1.1.1
          - 8.8.8.8
# Apply changes
sudo netplan apply

# Configure hostname
sudo hostnamectl hostname pi-devops-01
hostname

# Create a admin user
sudo adduser myname
sudo usermod -aG sudo myname
su - myname

# Configure SSH Securely
sudo vi /etc/ssh/sshd_config
PermitRootLogin no
PasswordAuthentication no
PubkeyAuthentication yes
sudo systemctl restart ssh

# Generate SSH key locally if needed:
ssh-keygen

# copy public key to the server
ssh-copy-id myname@ip
