# TCPDUMP CHEAT SHEET

## COMMAND LINE OPTIONS
```
-A Print frame payload in ASCII
-c <count> Exit after capturing count packets
-D List available interfaces
-e Print link-level headers
-F <file> Use file as the filter expression
-G <n> Rotate the dump file every n seconds
-i <iface> Specifies the capture interface
-K Don't verify TCP checksums
-L List data link types for the interface
-n Don't convert addresses to names
-p Don't capture in promiscuous mode
-q Quick output
-r <file> Read packets from file
-s <len> Capture up to len bytes per packet
-S Print absolute TCP sequence numbers
-t Don't print timestamps
-v[v[v]] Print more verbose output
-w <file> Write captured packets to file
-x Print frame payload in hex
-X Print frame payload in hex and ASCII
-y <type> Specify the data link type
-Z <user> Drop privileges from root to user

Example:
tcpdump -i any -s 0 -w out.cap
```