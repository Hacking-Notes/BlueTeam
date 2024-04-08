--- ---
<h3>What is Tshark?</h3>

Tshark is a command-line network protocol analyzer, part of the Wireshark suite. It allows users to capture and analyze network traffic in real-time or from saved capture files. Tshark provides powerful filtering and analysis capabilities, making it a valuable tool for network administrators, security professionals, and developers.

---
<h3>Common Use and Commands:</h3>

Tshark offers various options to capture, filter, and analyze network traffic. Below is a basic usage example:

```Terminal
tshark [OPTIONS] [CAPTURE_FILTER]
```

Common options include:
- `-i`: Specify the interface for capturing traffic.
- `-r`: Read packets from a capture file.
- `-Y`: Apply display filter expression.
- `-T`: Specify output format (e.g., text, JSON).
- `-w`: Write packets to a capture file.
- `-n`: Disable name resolution.

Example to capture traffic on interface eth0 and display basic packet information:
```Terminal
tshark -i eth0
tshark -Y'http.request.method == "GET"' -i eth0     ---> Display all the http request (LIVE)
```

Example to read packets from a capture file and apply a display filter:
```Terminal
tshark -r capture.pcap -Y "http"
```

---
<h3>More Information:</h3>

For in-depth documentation and advanced usage of Tshark, users can refer to the official Wireshark documentation or visit the Wireshark website. Additionally, the source code for Tshark and Wireshark is available on GitHub: [https://github.com/wireshark/wireshark](https://github.com/wireshark/wireshark).