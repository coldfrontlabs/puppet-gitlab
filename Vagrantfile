# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # All Vagrant configuration is done here. The most common configuration
  # options are documented and commented below. For a complete reference,
  # please see the online documentation at vagrantup.com.

config.vm.provider "virtualbox" do |vb|
  vb.customize ["modifyvm", :id, "--memory", 1024]
  vb.customize ["modifyvm", :id, "--cpus", "2"]
  vb.customize ["modifyvm", :id, "--ioapic", "on"] #http://geekbacon.com/2013/02/26/cannot-set-more-than-1-cpu-in-vagrant/
end


  config.vm.hostname  ="gitlab-test"
  config.vm.network :private_network, ip: "192.168.33.10"
  config.vm.synced_folder ".", "/etc/puppet/modules/gitlab"
  
  config.vm.define "centos", primary: true do |centosbox|
    centosbox.vm.box = "centos-6_5-x64-virtualbox_4_3-plain"
    centosbox.vm.box_url = "http://puppet-vagrant-boxes.puppetlabs.com/centos-65-x64-virtualbox-puppet.box"
  end
  
  config.vm.define "ubuntu", autostart: false do |ubuntubox|
    ubuntubox.vm.box = "ubuntu-12_04-x64-virtualbox_4_2_10-plain"
    ubuntubox.vm.box_url = "http://puppet-vagrant-boxes.puppetlabs.com/ubuntu-server-12042-x64-vbox4210.box"
  end
  
  config.vm.define "sles", autostart: false do |slesbox|
    slesbox.vm.box = "sles-11_sp1-x64-virtualbox_4_2_10-plain"
    slesbox.vm.box_url = "http://puppet-vagrant-boxes.puppetlabs.com/sles-11sp1-x64-vbox4210.box"
  end

  config.vm.define "debian", autostart: false do |debianbox|
    debianbox.vm.box = "debian-7_3-x64-virtualbox_4_3-plain"
    debianbox.vm.box_url = "http://puppet-vagrant-boxes.puppetlabs.com/debian-73-x64-virtualbox-puppet.box"
  end


  
end
