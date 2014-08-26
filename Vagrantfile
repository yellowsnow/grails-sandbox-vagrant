# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
  config.vm.hostname = "grails-vagrant"
  config.vm.box = "ubuntu/trusty64"
  config.vm.provision :shell, :path => "bootstrap.sh"
  config.vm.network :forwarded_port, guest: 8080, host: 28080
  config.vm.network :forwarded_port, guest: 5005, host: 25005
  config.vm.provider :virtualbox do |vb|
    vb.gui = true  
    vb.customize ["modifyvm", :id, "--memory", "3172", "--vram", 32, "--cpus", 2]
    vb.customize ["modifyvm", :id, "--nictype1", "82545EM"]
    vb.customize ["modifyvm", :id, "--natsettings1", "1500,1024,1024,1024,1024"]
  end
  # don't auto-update guest additions
  config.vbguest.auto_update = false
end
