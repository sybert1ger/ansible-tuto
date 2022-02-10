# -*- mode: ruby -*-
# vi: set ft=ruby :

hosts = {
  "host0" => "10.10.100.10",
  "host1" => "10.10.100.11",
  "host2" => "10.10.100.12"
}

Vagrant.configure("2") do |config|
  hosts.each do |name, ip|
    config.vm.define name do |machine|
      machine.vm.box = "ubuntu/bionic64"
      machine.vm.hostname = "%s" % name
      machine.vm.network :private_network, ip: ip
      machine.vm.provider "virtualbox" do |v|
          v.name = name
          v.customize ["modifyvm", :id, "--memory", 256]
      end
    end
  end
end
