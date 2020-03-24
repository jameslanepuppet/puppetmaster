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
