# ocserv-docker
You can use this repository to deploy ocserv and use it inside Iran.
## Deploy

 - Install Docker 1.0+
 - `cd ~;git clone https://github.com/satrobit/ocserv-docker.git`

Run:

    docker run -d --privileged --name ocserv-docker -v ~/ocserv-docker/ocserv:/etc/ocserv -p 443:443/tcp wppurking/ocserv
   
   If you don't want to route the traffic inside Iran then:
   

    docker run -d --privileged --name ocserv-docker -v ~/ocserv-docker/ocserv_iran:/etc/ocserv -p 443:443/tcp wppurking/ocserv
 

> Be aware that the subnets in the ocserv.conf file are result of merging CIDRs and to increase performance it may contain IPs from other CIDRs so don't use this for anything important!
> 
> To make sure you're not leaking any information inside Iran use the default ocserv.conf

 ## Usage
 -  Use the default users to connect. (wyatt:616 holly:525)
 - If iptables is enabled make sure both tcp and udp are open to the public on port 443.
 - Download a client. [Windows and macOS](https://github.com/openconnect/openconnect-gui), [Android](https://play.google.com/store/apps/details?id=app.openconnect&hl=en), [iOS](https://itunes.apple.com/us/app/cisco-anyconnect/id1135064690?mt=8)

 

 
 ## Users

Add a new user:
```
$> docker exec -it $(docker ps -a | grep vpn_run | awk '{print $1}') ocpasswd yourname
$> Enter password:
$> Re-enter password:
```

Removing default users:

Open `./ocserv/ocpasswd` and remove the lines containing default usernames.

 ## To-Do
 
 - [x] Translate README.md
 - [x] Add excluded Iranian IPs to ocserv.conf

 ## Information
* Box Size: 164 MB   (originally 380+ MB)
* ubuntu:trusty
* Tested environments:
  * [Linode 1G Ubuntu 14.04 LTS]
  * [Vultr 768MB Ubuntu 14.04 LTS]
  * [DigitalOcean 512MB Docker 1.2.0 on Ubuntu 14.04]

## Refs
* [ocserv 0.8.2 Manual](http://www.infradead.org/ocserv/manual.html)
* [[Original]linode vps debian7.5安装配置ocserv(OpenConnect server)](http://luoqkk.com/linode-vps-debian-installation-and-configuration-ocserv-openconnect-server.html)
* [Install Cisco AnyConnect Server on a Generic Linux Server](https://izhaom.in/2014/08/install-cisco-anyconnect-server-on-a-generic-linux-server/)
* [AnyConnect 带来 iPhone 上的新生活](http://imkevin.me/post/80157872840/anyconnect-iphone)
* [Install Ocserv on CentOS 6.5](https://botu.me/install-ocserv-on-centos6/)
* [Gnutls 3.1.23 on Ubuntu 14.04](http://www.bauer-power.net/2014/06/how-to-install-gnutls-3123-from-source.html)
