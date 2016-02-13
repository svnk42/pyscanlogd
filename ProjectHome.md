Pyscanlogd is a network port scan detection tool written in pure Python. It can detect most fast port scans and even can detect port-scans of longer duration upto an hour. It can run in the foreground and log scans to the console as well as a daemon while logging scans to a file.

```
$ sudo pyscanlogd
listening on eth0: 

# Regular scan detection

[2010-03-17 17:23:13]: TCP syn scan (flags:6) from 172.16.220.124 to 172.16.220.214 
(ports:256,995,554,8080,3389,139,3306,23,111,993,53,1723)
[2010-03-17 17:23:13]: Continuation of TCP syn scan from 172.16.220.124 to 
172.16.220.214 (ports:113,199,21,5900,22,1720,135,587,445,2065,6005,3703,631)
[2010-03-17 17:23:13]: Continuation of TCP syn scan from 172.16.220.124 to 
172.16.220.214 (ports:4004,1761,1075,4129,7921,33354,255,55600,1600,1065)
...
[2010-03-17 17:23:47]: TCP x-mas scan (flags:41) from 172.16.220.124 to 
66.102.13.104 (ports:110,21,111,1720,993,587,3389,143,199,445,8080,80)
[2010-03-17 17:23:50]: Continuation of TCP x-mas scan from 172.16.220.124 to
 66.102.13.104 (ports:443,1025,139,1723,554,5900,113,53,80,8080,995,23)
...

# IDLE scan detection

[2010-03-17 17:24:37]: TCP syn scan (flags:2) from 172.16.220.150 to 209.191.122.70 
(ports:21,53,8080,445,443,993,3306,995,110,5900,1720,23)
[2010-03-17 17:24:37]: Continuation of TCP syn scan from 172.16.220.150 to 209.191.122.70
 (ports:199,8888,554,25,256,22,135,1025,111,587,143)
[2010-03-17 17:24:38]: Continuation of TCP syn scan from 172.16.220.150 to 209.191.122.70 
(ports:80,1723,113,3389,139,3828,555,21,53,8080,445,443)
[2010-03-17 17:24:39]: Continuation of TCP syn scan from 172.16.220.150 to 209.191.122.70
 (ports:993,3306,995,110,5900,1720,23,199,8888,554,21,53)
[2010-03-17 17:24:45]: Idle scan (flags: 4) from 172.16.220.124 to 209.191.122.70 (ports: 
[21, 53, 8080, 445, 443, 993, 3306, 995, 110, 5900, 1720, 23]) using zombie host 
172.16.220.150
...

# Slow scan detection

[2010-03-17 17:32:19]: Possible slow TCP x-mas scan (flags:41) from 172.16.220.124 
to 64.208.187.107 (ports:1720,113,139,23), average timediff 10.26s
```