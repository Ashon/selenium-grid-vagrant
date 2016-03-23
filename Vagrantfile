# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure(2) do |config|
   
  config.vm.box = "ubuntu-15_04"
  config.vm.network "private_network", ip: "192.168.60.10"
  config.vm.synced_folder ".", "/vagrant", disabled: true
  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
    sudo apt-get install -y openjdk-7-jdk openjdk-7-jre-headless
    sudo apt-get install -y firefox
    sudo apt-get install -y xvfb
    sudo wget http://selenium-release.storage.googleapis.com/2.47/selenium-server-standalone-2.47.1.jar
    sudo xvfb-run java -jar selenium-server-standalone-2.47.1.jar -Djava.security.egd=file:///dev/urandom switch &
  SHELL
end
