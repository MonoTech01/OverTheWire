## Identify and count the number of ICMP packets in the traffic.pcap file

Identify
  
    user@ip-10-10-232-32:~$ tcpdump icmp -r traffic.pcap -n

The result of the above comment will show a list of icmp communications

Count
    
    user@ip-10-10-232-32:~$ tcpdump icmp -r traffic.pcap -n | wc
    reading from file traffic.pcap, link-type EN10MB (Ethernet)
        26     358    2722

26 packets

## Find the IP address of the host that asked for the MAC address of 192.168.124.137

    user@ip-10-10-232-32:~$ tcpdump arp -r traffic.pcap -n
    reading from file traffic.pcap, link-type EN10MB (Ethernet)
    07:18:29.940761 ARP, Request who-has 192.168.124.137 tell 192.168.124.148,
     length 28
    07:18:29.940776 ARP, Reply 192.168.124.137 is-at 52:54:00:23:60:2b, length
     28
    user@ip-10-10-232-32:~$ 
    
192.168.124.148

## Identify the hostname (subdomain) appears in the first DNS query

    user@ip-10-10-232-32:~$ tcpdump -i any udp port 53 -r traffic.pcap -n
    reading from file traffic.pcap, link-type EN10MB (Ethernet)
    07:18:24.058626 IP 192.168.124.137.33672 > 192.168.124.1.53: 39913+ A? mir
    rors.rockylinux.org. (40)
    ...

mirrors.rockylinux.org
