# home-lab

So the idea for my home lab is to have 8 VLANs:

| VLANID | Purpose | Range |
| --- | --- | --- |
| VLAN10 | Network Infrastructure | 10.10.0.0/24 |
| VLAN20 | Servers | 10.20.0.0/24 |
| VLAN30 | Users | 10.30.0.0/24 |
| VLAN40 | VMs | 10.40.0.0/24 |
| VLAN50 | Game Servers | 10.50.0.0/24 |
| VLAN60 | HomeLab | 10.60.0.0/24 |
| VLAN70 | IoT | 10.70.0.0/24 |
| VLAN80 | DMZ | 10.80.0.0/24 |

Here's how it's meant to look:

## 10.10.0.0/24 - Network Infrastructure

### With CPUs 10.10.0.0/29

| Device | IP | Details |
| --- | --- | --- | 
| Router | 10.10.0.1 | This connects directly to the ISP-provided internet router (transparent gateway) |
| pfSense | 10.10.0.2 | This is the Firewall and what will dictate the VLANS |
| Pi-Hole | 10.10.0.3 | The DNS that shuts down all the ad crap |

### CPU-less 10.10.0.0/25

| Device | IP | Details |
| --- | --- | --- | 
| Wifi AP | 10.10.0.128 | For better WiFi coverage in the house |
| Switch1 | 10.10.0.129 | Switch Jagger - located near the router |
| Switch2 | 10.10.0.130 | Vlan Halen - Located in the Office - Other side of house |

## 10.20.0.0/24 - Servers

| Device | IP | Details |
| --- | --- | --- | 
| Promox.cove | 10.20.0.1 | This is the Main Proxmox node |
| Proxmox.bay | 10.20.0.2 | 2nd Proxmos node |
| phr0st | 10.20.0.? | This server needs to be reporposed - maybe as the 3rd node? |
| old pfSense server | 10.20.0.? | This one never reached production - maybe as the 4th node? |

## 10.30.0.0/24 - Users
| Device | IP | Details |
| --- | --- | --- | 
| Jim-PC | 10.30.0.1 | Yup - this will be the big hitter himself! |
| Jim-Pop!_OS	 | 10.30.0.2 | That's my new (donated) laptop! |
| Jim-Work | 10.30.0.3 | This will be my work laptop when it's at home.	|
| Candice-Laptop | 10.30.0.128 | Yeah, C gets her own /25 |
| Candice Switch | 10.30.0.129 | That's a nintendo, not network infrastructure |
| Candice-Kindle | 10.30.0.130 | Hers still works... mine - not so much |

