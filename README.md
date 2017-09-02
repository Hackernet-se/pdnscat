# PDNSCAT - PowerDNS search client.
pdnscat is a bash script that curls the PowerDNS API after all search domains in /etc/resolv.conf file.

After you have filtred down to 1 line you can SSH to that device using predifined usernames like root, admin the user you are.

## Usage
pdnscat arg1 arg2 arg3 ... [f] [a|r|q|l] ...

###Examples
Grep on all nameservers.
'''bash
sparco@jumpgate:~$ y ns    
10.240.100.12   A       ns3
172.22.0.12     A       ns4
10.240.100.13   A       ns5
172.22.0.13     A       ns6
'''
