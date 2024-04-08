--- ---
<h2>What is Wireshark and How to Use It?</h2>

Wireshark is an industry-standard tool for network protocol analysis and is essential in any traffic and packet investigation. You can view, save and break down the network traffic with it. You can learn more about Wireshark by completing the [**Wireshark module**](https://tryhackme.com/module/wireshark).

--- ---
<h2>Commands</h2>

Filters
```
dns
```


Statistics
```
Statistic ---> Capture Files Properties
```

- Give many information about packets
	- Number of packets
	- Time
	- Other Very useful elements...


Protocol Hierachy
```
Statistics ---> Protocol Hierachy
```

- Give information about the packets (type)
	- ex: how many HTTP packets have been sent, ...


Conversation
```
Statistics ---> Conversation
```

- Analyse the number of packet sent to each ports
- Very great to detemine where the attack took place (what service)


Resolved Address
```
Statistics ---> Resolved Address / All entries to HOST
```

- Allow to see with what DNS was the packet sent


Download Files (Img, PDF, EXE)
```
File ---> export object ---> HTTP (Download the desired file)
```

- Allow you to download a file that has been downloaded by someone else during the time you capture the packets