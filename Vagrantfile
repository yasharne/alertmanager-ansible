# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|
  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
  end
  config.vm.define "am1" do |am1|
    am1.vm.box = "hashicorp/bionic64"
    am1.vm.hostname = "am1"
    am1.vm.network "private_network", type: "dhcp"
  end
  config.vm.define "am2" do |am2|
    am2.vm.box = "centos/7"
    am2.vm.hostname = "am2"
    am2.vm.network "private_network", type: "dhcp"
  end

  config.vm.provision "ansible" do |ansible_prometheus|
    ansible_prometheus.playbook = "alertmanager.yml"
    ansible_prometheus.groups = {
      "all" => ["am1", "am2"]
    }
  end


end
