# pisces P100 Tools / Command Code List (  Vollection )


Scripts to perform maintenance on the Pisces P100

Pisces P100 Devices , External IP Update Command 
```ruby
sudo /etc/monitor-scripts/external-ip.sh LAN
```

Fast Syncronization Command 
This is a collection of scripts useful for Pisces miners P100
DISCLAIMER: Only use this scripts if you know what you are doing!!!
How to run clear_resync.sh:
This script will clean blockchain data and the re-sync the hotspot using Nebra or SenseCAP snapshot based on which one is the closest to the actual blockchain height

```ruby
 wget https://raw.githubusercontent.com/istdizayn/pisces-tools/main/clear_resync.sh -O - | sudo bash
```

FAST Sync Tools - Use this. 
```ruby
sudo wget https://raw.githubusercontent.com/istdizayn/pisces-tools/main/fastsync.sh -O - | sudo bash
```

How to run crontab_job.sh:
This script will install in crontab a job that everyday at midnight will run a check on root filesystem free space left and if it's less than 20% free will run the clean_resync.sh script

```ruby
 wget https://raw.githubusercontent.com/istdizayn/pisces-tools/main/crontab_job.sh -O - | sudo bash
```
How to run fixed_dns.sh:
This script will override the DNS servers pushed from the DHCP server in your LAN and will set the google DNS

```ruby
wget https://raw.githubusercontent.com/istdizayn/pisces-tools/main/fixed_dns.sh -O - | sudo bash
```

PERFORMANCE TWEAKS FROM INIGOFLORES (https://github.com/inigoflores)
Miner Peerbook Settings Tweak
This tool downloads a modified version of sys.config that dramatically reduces the "not found" issue that is affecting almost every Helium miner.

It sets the following values:
```ruby
   {peerbook_update_interval, 90000},
   {max_inbound_connections, 200},
   {outbound_gossip_connections, 50},
```   
   
These values have shown to increase the peer books size to around 200,000. In order to check to the current peer book size, you can run:

```ruby
sudo docker exec miner miner peer book -c
```

Run the script
Apply changes
```ruby
sudo wget https://raw.githubusercontent.com/inigoflores/pisces-p100-tools/main/Not_Found_Fix/apply.sh -O - | sudo bash
```

Restore backup of sys.config
```ruby
sudo wget https://raw.githubusercontent.com/inigoflores/pisces-p100-tools/main/Not_Found_Fix/restore.sh -O - | sudo bash
```
