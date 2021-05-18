# destiny2firewall
Setup: initial setup
sudo bash d2firewall.sh -a setup

Add: add a sniffed id to your firewall
sudo bash d2firewall.sh -a add

Remove: remove ids from the end of the list
sudo bash d2firewall.sh -a remove

Sniff: Auto sniffer. (You must add your 2 host consoles prior to running this)
sudo bash d2firewall.sh -a sniff

Open: Enables public matchmaking
sudo bash d2firewall.sh -a open

Close: Disables public matchmaking
sudo bash d2firewall.sh -a close

List: List the current accounts
sudo bash d2firewall.sh -a list

Update: Update the script to the newest version.
sudo bash d2firewall.sh -a update

Load: Load the saved rules after a reboot
sudo bash d2firewall.sh -a load

Reset: Reset iptables to default
sudo bash d2firewall.sh -a reset



Raw User Data

#!/bin/bash
sudo "echo 1 > /proc/sys/net/ipv4/ip_forward"
wget https://git.io/vpn -O openvpn-ubuntu-install.sh
chown ubuntu:ubuntu openvpn-ubuntu-install.sh
chmod +x openvpn-ubuntu-install.sh
wget -q https://raw.githubusercontent.com/Tornatus/destiny2firewall/main/d2firewall -O ./d2firewall.sh
chown ubuntu:ubuntu d2firewall.sh
chmod +x d2firewall.sh
mv openvpn-ubuntu-install.sh /home/ubuntu/openvpn-ubuntu-install.sh
mv d2firewall.sh /home/ubuntu/d2firewall.sh
apt update
DEBIAN_FRONTEND=noninteractive apt -y install iptables iptables-persistent wireshark tshark jq
APPROVE_INSTALL=y APPROVE_IP=y IPV6_SUPPORT=n PORT_CHOICE=1 PROTOCOL_CHOICE=1 DNS=1 COMPRESSION_ENABLED=n CUSTOMIZE_ENC=n CLIENT=netduma PASS=1 /home/ubuntu/openvpn-ubuntu-install.sh

