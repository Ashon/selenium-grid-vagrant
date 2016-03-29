# -*- mode: ruby -*-
# vi: set ft=ruby :

$selenium_node_count = 2
$selenium_gateway = "192.168.60"
$selenium_hub_lastip = 10


Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu-15_04"
  config.vm.synced_folder ".", "/vagrant", disabled: true


  config.vm.define "selenium-hub" do |selenium_hub|
    selenium_hub.vm.network "private_network", ip: "#{$selenium_gateway}.#{$selenium_hub_lastip}"
  end


  (1..$selenium_node_count).each do |i|

    config.vm.define "selenium-node-#{i}" do |selenium_node|
      $selenium_node_lastip = $selenium_hub_lastip + i
      selenium_node.vm.network "private_network", ip: "#{$selenium_gateway}.#{$selenium_node_lastip}"
    end

  end

end
