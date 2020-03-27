# puppetmaster

Simple vagrant file that spins up:

- Linux VM (host)

- Linux VM (agent)

- Windows VM (agent)


 # ssh into each box individually 

- vagrant ssh /master/

- vagrant ssh /linux/

- vagrant ssh /windows/

# Setting up Master 

1. ssh in master.vm
```
vagrant ssh /master/
```
2. download package for centos/7 -
```
sudo curl -JLO 'https://pm.puppet.com/cgi-bin/download.cgi?dist=el&rel=7&arch=x86_64&ver=latest'
```
3. unpack package
```
tar -xf puppet-enterprise-2019.5.0-el-7-x86_64.tar.gz
```
4. cd into repository
```
cd puppet-enterprise-2019.5.0-el-7-x86_64
```
5. run puppet installer
```
sudo ./puppet-enterprise-installer
```
----------------------------------------
6. check hostname for machhine, it should be master.vm
```
hostname
```
7. edit ~/etc/hosts
```
sudo vi ~/etc/hosts
```
8. add this into the file
```
192.168.50.4 master.vm master
```
9. edit puppet config file 
```
sudo vi ~/etc/puppetlabs/puppet/puppet.config
```
10. make changes in file
```
certname = master.vm
```
# Setting up Linux Agent

1. remote onto linux vm
```
vagrant ssh /linux/
```
2. add line into etc/hosts file 
```
192.168.50.6 linux.vm linux
```
3. Disable firewalld
```
systemctl stop firewalld
systemctl disable firewalld
```
