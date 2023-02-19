--- ---

<h2>Log Analysis</h2>

Linux operating system log files (and often software-specific such as apache2) are located within the `/var/log` directory. We can use the `ls` in the `/var/log` directory to list all the log files located on the system:

Listing log files within the /var/log directory

```shell-session
cubuntu@aoc2022-day-2:/var/log$ ls -lah total 724K drwxrwxr-x 9 root syslog 4.0K Nov 14 10:59 . drwxr-xr-x 13 root root 4.0K Oct 26 2020 .. drwxr--r-x 3 root root 4.0K Nov 14 10:56 amazon drwxr-xr-x 2 root root 4.0K Oct 26 2020 apt -rw-r----- 1 syslog adm 11K Nov 14 11:03 auth.log -rw-rw---- 1 root utmp 0 Oct 26 2020 btmp -rw-r--r-- 1 root root 7.3K Nov 14 10:59 cloud-init-output.log -rw-r--r-- 1 syslog adm 251K Nov 14 10:59 cloud-init.log drwxr-xr-x 2 root root 4.0K Oct 7 2020 dist-upgrade -rw-r--r-- 1 root adm 36K Nov 14 10:59 dmesg -rw-r--r-- 1 root adm 36K Nov 14 10:56 dmesg.0 -rw-r--r-- 1 root root 12K Oct 26 2020 dpkg.log drwxr-sr-x+ 3 root systemd-journal 4.0K Nov 14 10:55 journal -rw-r----- 1 syslog adm 98K Nov 14 10:59 kern.log drwxr-xr-x 2 landscape landscape 4.0K Nov 14 10:57 landscape -rw-rw-r-- 1 root utmp 286K Nov 14 11:03 lastlog drwx------ 2 root root 4.0K Nov 14 10:55 private -rw-r----- 1 syslog adm 207K Nov 14 11:03 syslog drwxr-x--- 2 root adm 4.0K Nov 14 10:55 unattended-upgrades -rw-rw-r-- 1 root utmp 8.3K Nov 14 11:03 wtmp
```

![[Pasted image 20221202100007.png]]

---

<h2>Looking Through Log Files</h2>

Log files can quickly contain many events and hundreds, if not thousands, of entries. The difficulty in analysing log files is separating useful information from useless. Tools such as Splunk are software solutions known as Security, and Event Information Management (SIEM) is dedicated to aggregating logs for analysis.

---> [[• Splunk]]
