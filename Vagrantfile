# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"
  config.vm.box_version = "20190807.0.0"
  config.vm.box_check_update = false
  config.vm.network :private_network, ip: "192.168.222.222"
  config.ssh.forward_agent = true

  config.vm.provider "virtualbox" do |vb|
    vb.customize ['modifyvm', :id, '--accelerate3d', 'on', '--audioout', 'on', '--graphicscontroller', 'vboxsvga']
    vb.gui = true
    vb.memory = "2048"
  end

  config.vm.provision "shell", inline: <<-SHELL
    mkdir /builds
    chmod -R 777 /builds
    apt-get update
    apt-get install -y unzip
    apt-get install -y build-essential openssh-server clang libssl-dev libxrandr-dev libxxf86vm-dev libopenal-dev libgl1-mesa-dev libglu1-mesa-dev zlib1g-dev libcurl4-openssl-dev
    apt-get install -y libcurl4 libopenal1
    apt-get install -y ubuntu-desktop gdm3 --no-install-recommends
    echo -e "[daemon]\nAutomaticLoginEnable = true\nAutomaticLogin = vagrant\n\n[security]\n\n[xdmcp]\n\n[chooser]\n\n[debug]\n\n" > /etc/gdm3/custom.conf
    service gdm start
    echo -e "Match User vagrant\n\tPasswordAuthentication yes" >> /etc/ssh/sshd_config
    /etc/init.d/ssh restart
  SHELL
end
