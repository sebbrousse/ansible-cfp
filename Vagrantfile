# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu-14.04-amd64"
  config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"
  config.vm.network :forwarded_port, guest: 8080, host: 8080
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "cfp-playbook.yml"
    ansible.sudo = true
    ansible.verbose = 'vvv'
  end
  config.vm.provider "virtualbox" do |v|
  	v.customize ["modifyvm", :id, "--name", "breizhcamp-cfp"] # name for VirtualBox GUI
  end
end
