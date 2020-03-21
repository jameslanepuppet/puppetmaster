Vagrant.configure("2") do |config|

  config.vm.define "master.vm" do |master|
    master.vm.box = "centos/7"
    master.vm.hostname = "master.vm"
    master.vm.network "private_network", ip: "192.168.50.4"
    master.vm.provider "virtualbox" do |v|
      v.memory = 4096
      v.cpus = 2
    end
  end 

  config.vm.define "windows.vm" do |windows|
    windows.vm.box = "kensykora/windows_2012_r2_standard"
    windows.vm.communicator = "winrm"
    windows.vm.hostname = "windows"
    windows.vm.network "private_network", ip: "192.168.50.5"
    windows.vm.provider "virtualbox" do |v|
      v.memory = 2048
    end
  end

  config.vm.define "linux.vm" do |linux|
    linux.vm.box = "centos/7"
    linux.vm.hostname = "linux.vm"
    linux.vm.network "private_network", ip: "192.168.50.6"
    linux.vm.provider "virtualbox" do |v|
      v.memory = 2048
    end
  end
end

