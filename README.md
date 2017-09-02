# PDNSCAT - PowerDNS search client.
pdnscat is a bash script that curls the PowerDNS API after all search domains in /etc/resolv.conf file.

After you have filtred down to 1 line you can SSH to that device using predifined usernames like root, admin the user you are.

## Usage
Script need __curl__ and __JQ__ to work.
```
git clone https://github.com/Hackernet-se/pdnscat
./pdnscat arg1 arg2 arg3 ... [f] [a|r|q] ...
```
### Examples
##### Grep on all nameservers.
```bash
sparco@jumpgate:~$ y ns    
10.240.100.12   A       ns3
172.22.0.12     A       ns4
10.240.100.13   A       ns5
172.22.0.13     A       ns6
```
##### SSH to ns5
```bash
sparco@jumpgate:~$ y ns 5   
10.240.100.13   A       ns5
sparco@jumpgate:~$ y ns 5 r                                      
                                                                 
--- IP and hostname ---                                          
10.240.100.13                                                    
ns5                                                              
ssh root@10.240.100.13                                           
                                                                 
root@10.240.100.13's password:                                   
Welcome to Ubuntu 16.04.2 LTS (GNU/Linux 4.4.0-79-generic x86_64)
```
##### Grep on everything from a subdomain.
```bash
sparco@jumpgate:~$ y rsg f
10.60.0.50      A       rsg-proxy.hackernet.se.
10.60.0.4       A       esxispa1-ilo.rsg.hackernet.se.
10.60.0.5       A       esxispa2-ilo.rsg.hackernet.se.
10.60.0.6       A       esxispa3-ilo.rsg.hackernet.se.
10.60.0.16      A       esxispa3.rsg.hackernet.se.
10.60.0.53      A       foreman.rsg.hackernet.se.
10.60.0.12      A       ilocz3128ldh5.rsg.hackernet.se.
10.60.0.5       A       ilocz3128ldje.rsg.hackernet.se.
10.60.0.6       A       ilocz3128ldjv.rsg.hackernet.se.
10.60.0.10      A       ilocz3128ldjy.rsg.hackernet.se.
10.60.0.11      A       ilocz3128ldkb.rsg.hackernet.se.
10.60.0.4       A       ilocz3128le5v.rsg.hackernet.se.
10.60.0.7       A       ilocz32025rlt.rsg.hackernet.se.
10.60.0.9       A       ilocz32025rma.rsg.hackernet.se.
10.60.0.8       A       iloczj2100hf4.rsg.hackernet.se.
```
