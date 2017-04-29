## Digital Camouflage [50 Points]
We need to gain access to some routers. Let's try and see if we can find the password in the captured network
data: data.pcap.

**Hints:**
  - It looks like someone logged in with their password earlier. Where would log in data be located in a network capture?
  - If you think you found the flag, but it doesn't work, consider that the data may be encrypted.

**Solution:**  
Open the *data.pcap* file in *WireShark*  
Set filter to: *http.request.method == POST*

```
Frame 65: 109 bytes on wire (872 bits), 109 bytes captured (872 bits)
Ethernet II, Src: PcsCompu_38:2c:5c (08:00:27:38:2c:5c), Dst: PcsCompu_3d:47:5d (08:00:27:3d:47:5d)
Internet Protocol Version 4, Src: 10.0.0.5, Dst: 10.0.0.1
Transmission Control Protocol, Src Port: 59124, Dst Port: 8080, Seq: 388, Ack: 1, Len: 43
[2 Reassembled TCP Segments (430 bytes): #63(387), #65(43)]
Hypertext Transfer Protocol
HTML Form URL Encoded: application/x-www-form-urlencoded
    Form item: "userid" = "sullivanm"
    Form item: "pswrd" = "UldPRVRNOWZhWQ=="
```

Decode the base64 encoded password for the flag
```
$ python
>>> "UldPRVRNOWZhWQ==".decode("base64")
'RWOETM9faY'
```
