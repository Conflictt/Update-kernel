# -*- mode: ruby -*-
# vim: set ft=ruby :

ENV["LC_ALL"] = "en_US.UTF-8"

Vagrant.configure("2") do |config|
  # Вибір боксу
  config.vm.box = "debian/bullseye64"
  config.vm.box_check_update = false
  config.vm.hostname = "01-upd-kernel"
  
  # ім'я в `vagrant global-status`
  config.vm.define "Deb-Update-kernel"

  config.vm.provider "virtualbox" do |v|
    # ім'я в `VirtualBox`
    v.name = "Deb-Update-kernel" 
    v.gui = false
    v.memory = 1024
    v.cpus = 2
  end

  config.vm.provision "shell", type: "shell", inline: <<-SHELL
    sudo apt-get update -yy
    sudo apt-get install linux-image-6.1.0-0.deb11.7-amd64 -yy
    sudo reboot
  SHELL
end