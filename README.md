# LogParser
Integration of multiple information security products or security events for joint defense with Check Point Firewall via R81.20

![](https://cp.birdlex.net/cp/static-files/logparser-0.png)

## Features
- Using RegEx to parse the client's src-IP form received syslog
- Manually add IPs that need to be blocked
- TTL (Time To Live) function to set the live time of IP
- Management integrated in SmartConsole
- Instant notification when syslog hit the RegEx (IFTTT)

### LogParser's VM image OOB installation
- Download link: `https://cp.birdlex.net/cp/`
- VM Default Password: `root:Cpwins1!`
- SmartConsole Extenion URL: `https://<IP>/CheckPoint-LogParser-SmartConsoleExt/extension.json`
  ![](https://cp.birdlex.net/cp/static-files/logparser-1.png)
- Network Feed URL: `https://<IP>/networkfeed`
- UDP Syslog Server: `<IP>:6514`
  ![](https://cp.birdlex.net/cp/static-files/logparser-2.png)

### SmartConsole Ext installation
- Add to SmartConsole Ext
  ![](https://cp.birdlex.net/cp/static-files/logparser-3.png)

### Add to Network Feed Obj
- Find the LogParser's URL
  ![](https://cp.birdlex.net/cp/static-files/logparser-4.png)
- Add a Network Feed Obj
  ![](https://cp.birdlex.net/cp/static-files/logparser-5.png)
- Test Feed
  ![](https://cp.birdlex.net/cp/static-files/logparser-6.png)