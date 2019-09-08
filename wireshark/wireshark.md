# WIRESHARK CHEAT SHEET

## OPERATORS AND LOGIC
```
eq or == 
lt or < 
ne or != 
ge or >= 
gt or > 
le or <= 
and or && Logical AND 
not or ! Logical NOT
or or || Logical OR 
[n] [_] Substring operator
xor or ^^ Logical XOR
```
## ETHERNET
```
eth.addr 
eth.dst 
eth.src 
eth.ig 
eth.len 
eth.type 
eth.lg 
eth.multicast 
eth.trailer 
```
## IPV4
```
ip.host
ip.id 
ip.len
ip.proto 
ip.src 
ip.dst
ip.ttl
ip.tos 
ip.checksum_bad 
ip.fragment.toolongfragment 
ip.checksum_good 
ip.hdr_len 
ip.dsfield 
ip.dsfield.ce 
ip.dsfield.dscp 
ip.dsfield.ect 
ip.reassembled_in 
ip.dst_host 
ip.flags 
ip.src_host 
ip.flags.df
ip.flags.mf 
ip.tos.cost 
ip.flags.rb 
ip.tos.delay 
ip.fragment 
ip.tos.precedence 
ip.frag_offset 
ip.tos.reliability 
ip.fragment.error 
ip.tos.throughput 
ip.fragment.multipletails 
ip.fragment.overlap 
ip.version 
```

## IPV6
```
ipv6.src
ipv6.src_host
ipv6.hlim 
ipv6.dst 
ipv6.dst_host
ipv6.dst_opt
ipv6.flow 
ipv6.nxt
ipv6.opt.pad1
ipv6.opt.padn
ipv6.plen
ipv6.routing_hdr
ipv6.routing_hdr.addr
ipv6.routing_hdr.left
ipv6.routing_hdr.type
ipv6.mipv6_home_address
ipv6.mipv6_length
ipv6.mipv6_type
ipv6.fragment 
ipv6.fragment.error 
ipv6.fragment.id 
ipv6.fragment.more 
ipv6.reassembled_in
ipv6.fragment.multipletails 
ipv6.fragment.offset 
ipv6.fragment.overlap 
ipv6.fragment.overlap.conflict 
ipv6.fragment.toolongfragment 
ipv6.fragments 
ipv6.version
```
## HTTP
```
http.host 
http.request 
http.accept 
http.authbasic 
http.referer 
http.request.method 
http.location 
http.server 
http.date 
http.user_agent
http.connection 
http.request.uri
http.response 
http.cookie 
http.set_cookie 
http.time > 1 
http.accept_encoding 
http.accept_language 
http.proxy_connect_host 
http.proxy_connect_port
http.proxy_authorization 
http.authorization 
http.cache_control 
http.content_encoding 
http.request.version 
http.content_length 
http.content_type 
http.response.code
http.last_modified 
http.transfer_encoding 
http.notification 
http.www_authenticate
http.proxy_authenticate 
http.x_forwarded_for
frame contains "GET" && !tcp.port==80
http.response.code>299 && http.response.code<400 (HTTP Redirections)
http.request.uri matches "\.(exe|zip|jar)$" 
http.request.method in {PUT POST} 
```