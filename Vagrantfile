# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.define :centos7 do |vagrant|
    vagrant.vm.box = "centos-7.3.virtualbox.box"
    vagrant.vm.box_url = "./builds/centos-7.3.virtualbox.box"
    vagrant.vm.network "private_network", ip: "192.168.33.7"
    vagrant.vm.provision :shell, :path => "bootstrap-centos7.sh"
    vagrant.vm.provision :shell, :path => "bootstrap.sh"
    vagrant.vm.provision "ansible" do |ansible|
      ansible.playbook = "tasks/centos7.yml"
      ansible.inventory_path = "hosts"
      ansible.limit = 'centos7'
    end
  end

  config.vm.define :centos6 do |vagrant|
    vagrant.vm.box = "centos-6.7.virtualbox.box"
    vagrant.vm.box_url = "./builds/centos-6.7.virtualbox.box"
    vagrant.vm.network "private_network", ip: "192.168.33.6"
    vagrant.vm.provision :shell, :path => "bootstrap-centos6.sh"
    vagrant.vm.provision :shell, :path => "bootstrap.sh"
    vagrant.vm.provision "ansible" do |ansible|
      ansible.playbook = "tasks/centos6.yml"
      ansible.inventory_path = "hosts"
      ansible.limit = 'centos6'
    end
  end

  config.vm.define :centos5 do |vagrant|
    vagrant.vm.box = "centos-5.11.virtualbox.box"
    vagrant.vm.box_url = "./builds/centos-5.11.virtualbox.box"
    vagrant.vm.network "private_network", ip: "192.168.33.5"
    vagrant.vm.provision :shell, :path => "bootstrap_centos5.sh"
    vagrant.vm.provision :shell, :path => "bootstrap.sh"
    vagrant.vm.provision "ansible" do |ansible|
      ansible.playbook = "tasks/centos5.yml"
      ansible.inventory_path = "hosts"
      ansible.limit = 'centos5'
    end
  end
end
