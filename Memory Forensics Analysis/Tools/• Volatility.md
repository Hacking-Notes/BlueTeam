--- ---

<h2>Commands</h2>

Volatility
```
#Using Volatility to Analyse an Image
python3 vol.py -f workstation.vmem windows.info

#Showing Plugins in Use
python3 vol.py -f workstation.vmem windows.pslist

#Discover what a specific process was actually doing
python3 vol.py -f workstation.vmem windows.psscan

#Export specific binary for further analyse through static or dynamic analysis.
python3 vol.py -f workstation.vmem windows.dumpfiles --pid X
```

- workstation.vmem                ---> Memory dump (can include location -> /Downloads/x.vmem)
- windows.SOMETHING          ---> Type of pluging we are using to scan

Options
![[Pasted image 20221211181020.png]]

Plugins
![[Pasted image 20221211181441.png]]

---

<h2>What is Volatility</h2>

Volatility is an open-source memory forensics toolkit written in Python. Volatility allows us to analyse memory dumps taken from Windows, Linux and Mac OS devices and is an extremely popular tool in memory forensics. For example, Volatility allows us to:

-   List all processes that were running on the device at the time of the capture
-   List active and closed network connections
-   Use Yara rules to search for indicators of malware
-   Retrieve hashed passwords, clipboard contents, and contents of the command prompt
-   And much, much more!