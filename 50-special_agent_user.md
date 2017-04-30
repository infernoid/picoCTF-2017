## Special Agent User [50 Points]

We can get into the Administrator's computer with a browser exploit. But first, we need to figure out what browser they're using. Perhaps this information is located in a network packet capture we took: data.pcap. Enter the browser and version as "BrowserName BrowserVersion". NOTE: We're just looking for up to 3 levels of subversions for the browser version (ie. Version 1.2.3 for Version 1.2.3.4) and ignore any 0th subversions (ie. 1.2 for 1.2.0)

**Hints:**

- Where can we find information on the browser in networking data?
  Maybe try reading up on user-agent strings.

**Solution:**

Open the data.pcap file in WireShark  
Set filter to: http.user_agent

Wget is not a browser but a linux command line application
```
Frame 54: 190 bytes on wire (1520 bits), 190 bytes captured (1520 bits)
Ethernet II, Src: PcsCompu_e5:81:e1 (08:00:27:e5:81:e1), Dst: PcsCompu_b2:db:ff (08:00:27:b2:db:ff)
Internet Protocol Version 4, Src: 10.0.0.5, Dst: 10.0.0.1
Transmission Control Protocol, Src Port: 43016, Dst Port: 80, Seq: 1, Ack: 1, Len: 124
Hypertext Transfer Protocol
    GET /pages/friends.html HTTP/1.1\r\n
    User-Agent: Wget/1.16 (linux-gnu)\r\n
...
```

The flag is in the user agent string
```
Frame 90: 259 bytes on wire (2072 bits), 259 bytes captured (2072 bits)
Ethernet II, Src: PcsCompu_e5:81:e1 (08:00:27:e5:81:e1), Dst: PcsCompu_b2:db:ff (08:00:27:b2:db:ff)
Internet Protocol Version 4, Src: 10.0.0.5, Dst: 10.0.0.1
Transmission Control Protocol, Src Port: 43017, Dst Port: 80, Seq: 1, Ack: 1, Len: 193
Hypertext Transfer Protocol
    GET / HTTP/1.1\r\n
    User-Agent: Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/36.0.1985.67
...
```

**Flag:** Chrome 36.0.1985
