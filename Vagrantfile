# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "insaneworks/almalinux9-aarch64"
  config.vm.provision :shell, inline: <<-EOS
    yum -y install -y yum-utils xz
    yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
    yum -y install docker-ce docker-ce-cli containerd.io
    systemctl start docker
    /vagrant/mkimage-yum.sh insaneworks/almalinux9-aarch64
  EOS
end
