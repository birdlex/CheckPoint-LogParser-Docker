# LogParser
Integration of multiple information security products events or security events for joint defense with Check Point Firewall via R81.20

![](https://cp.birdlex.net/cp/static-files/logparser-0.png)


## Features
- Using RegEx to parse the client's src-IP form received syslog
- Manually add IPs that need to be blocked
- TTL (Time To Live) function to set the live time of IP
- Management integrated in SmartConsole
- Instant notification when syslog hit the RegEx (IFTTT)

* Installation
  * [VM OOB Install](#logparsers-vm-image-oob-installation)
  * [Docker Install](#logParser-docker-installation)
* Configuration
  * [SmartConsole Ext installation](#smartconsole-ext-installation)
  * [Add to Network Feed Obj](#add-to-network-feed-obj)
  * [LogParser Configs](#logparser-configs)
  * [LogParser syslog test](#logparser-syslog-test)
  * [RegEx](#regex)


### LogParser VM image OOB installation
- Download link: `https://birdlex.cplab.tw/cp/vm_images/CP-LogParser.zip`
  backup link: `https://cp.birdlex.net/cp/vm_images/CP-LogParser.zip`
- VM Default Password: `root:Cpwins1!`
- SmartConsole Extenion URL: `https://<IP>/CheckPoint-LogParser-SmartConsoleExt/extension.json`
  ![](https://cp.birdlex.net/cp/static-files/logparser-1.png)
- Network Feed URL: `https://<IP>/networkfeed`
- UDP Syslog Server: `<IP>:6514`
  ![](https://cp.birdlex.net/cp/static-files/logparser-2.png)


### LogParser docker installation
- Clone this repo: `git clone https://github.com/birdlex/CheckPoint-LogParser-Docker.git`
- `cd CheckPoint-LogParser-Docker`
- `docker compose up -d`
- SmartConsole Extenion URL: `https://<IP>/CheckPoint-LogParser-SmartConsoleExt/extension.json`
- Network Feed URL: `https://<IP>/networkfeed`
- UDP Syslog Server: `<IP>:6514`


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


### LogParser Configs
![](https://cp.birdlex.net/cp/static-files/logparser-7.png)
- interval = 1
  The time unit is minute, minimum 1 minute
- threshold = 1
  Trigger frequency threshold, minimum is 1
- default_ttl = 0
  Default TTL in minutes. If default_ttl = 0, then it is permanent. If default_ttl = 10, the IP will be deleted after 10 minutes.
`IF set to interval = 1, threshold = 3, when the event is triggered thrice in 1 minute, the IP will be added to the list.`


### LogParser syslog test
If you have already set RegEx, you can paste the original log into the syslog test and send the log to test.
![](https://cp.birdlex.net/cp/static-files/logparser-8.png)


### RegEx
- RegEx
  ![](https://cp.birdlex.net/cp/static-files/logparser-10.png)
  `** The names in RegEx cannot be duplicated, and avoid using spaces and special symbols in the names.`
- RegEx Example
  Assuming that `action: "Prevent"` is the keyword in the log, and the IP in `src: "192.168.80.119"` is extracted, the Regex can be written as the following.
  You can go to `https://regex101.com` to test your RegEx.
  ![](https://cp.birdlex.net/cp/static-files/logparser-9.png)

