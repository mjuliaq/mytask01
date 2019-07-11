# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "minimal/centos7"
  config.vm.box_version = "7.0"
  config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"
    config.vm.provision "file", source: "index.html", destination: "$HOME/index.html"
    config.vm.provision "file", source: "Dockerfile", destination: "$HOME/Dockerfile"
    config.vm.provision "ansible" do |ansible|
    ansible.playbook = "helloworld.yml"
  end
end
