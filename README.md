# ocserv-docker
You can use this repository to deploy ocserv and use it inside Iran.
## Deploy

 1. Install Docker 1.0+
 2. `cd ~;git clone https://github.com/satrobit/ocserv-docker.git`
 3. `docker run -d --privileged --name ocserv-docker -v ~/ocserv-docker/ocserv:/etc/ocserv -p 443:443/tcp wppurking/ocserv`
 ## Usage
 ...
 ## Users
 ...
 ## To-Do
 
 - [x] Translate README.md
 - [ ] Add excluded Iranian IPs to ocserv.conf

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
