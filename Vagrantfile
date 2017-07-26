# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.hostname = "docker.local"

  config.vm.provider "virtualbox" do |vb| 
    vb.gui = false
    vb.name = "[Vagrant] Docker"
    vb.memory = "1024"
    vb.cpus = "2"
  end

  config.vm.provider "vmware_fusion" do |v|
    v.gui = false
    v.vmx["memsize"] = "1024"
    v.vmx["numvcpus"] = "2"
  end

  config.vm.provision "ansible_local" do |ansible|
    ansible.install = true
    ansible.playbook = "main.yml"
    ansible.provisioning_path = "/vagrant/ansible"
  end
end