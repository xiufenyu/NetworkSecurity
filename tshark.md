1. Display SNI

```
$ tshark -r Test-001.pcap -Y "tls.handshake.type==1" -T fields -e ip.src -e ip.dst -e tls.handshake.extensions_server_name
```

```
tshark -r Test-001.pcap -Y "tls.handshake.type==1" -T fields -e ip.src -e tcp.srcport -e ip.dst -e tcp.dstport -e tls.handshake.extensions_server_name
```

**Note**:   \
-Y: the same as **Filter** in Wireshark
