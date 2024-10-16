1. Display SNI

```
$ tshark -r Test-001.pcap -Y "tls.handshake.type==1" -T fields -e ip.src -e ip.dst -e tls.handshake.extensions_server_name
```

```
$ tshark -r Test-001.pcap -Y "tls.handshake.type==1" -T fields -e ip.src -e tcp.srcport -e ip.dst -e tcp.dstport -e tls.handshake.extensions_server_name
```

2. Filter SNI
```
$ tshark -r Test-001.pcap -Y tls.handshake.extensions_server_name=="www.serpro.gov.br"
```

3. Show DNS queries and the resolved IP addresses
```
$ tshark -r Test-001.pcap -Y "dns.qry.name && dns.a" -T fields -e ip.src -e ip.dst -e dns.qry.name -e dns.a
```


4. Show source ip, destination ip and packets exchanged
```
tshark -r <file.pcap> -T fields -e ip.src -e ip.dst -e frame.len
```

5. Show source ip, destination ip, and bytes exchanged in ascending order

```
tshark -r <file.pcap> -T fields -e ip.src -e ip.dst -e frame.len | awk '{bytes[$1" "$2]+=$3} END {for (ip in bytes) print ip, bytes[ip]}' | sort -k3,3n
```

**Note**:   \
-Y: the same as **Filter** in Wireshark
