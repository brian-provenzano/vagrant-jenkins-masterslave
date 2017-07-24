# Defines our Vagrant environment
#
# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  #create a jenkins master server
   config.vm.define :jenkins do |jenkins_config|
      jenkins_config.vm.box = "centos/7"
      jenkins_config.vm.hostname = "jenkins"
      jenkins_config.vm.network :private_network, ip: "10.0.15.12"
      jenkins_config.vm.network "forwarded_port", guest: 8080, host: 8888
      jenkins_config.vm.provider "virtualbox" do |vb|
        vb.memory = "1024"
      end
      jenkins_config.vm.provision :shell, path: "bootstrap-jenkins-master.sh"
  end
  #create a jenkins slave
   config.vm.define :jenkinsslave do |jenkinsslave_config|
      jenkinsslave_config.vm.box = "centos/7"
      jenkinsslave_config.vm.hostname = "jenkins-slave"
      jenkinsslave_config.vm.network :private_network, ip: "10.0.15.13"
      jenkinsslave_config.vm.provider "virtualbox" do |vb|
        vb.memory = "1024"
      end
      jenkinsslave_config.vm.provision :shell, path: "bootstrap-jenkins-slave.sh"
  end
end
