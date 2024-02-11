# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # Define o nome da máquina como srv-web
  config.vm.define "srv-web"

  # Exposição do nginx na porta 8085
  config.vm.network "forwarded_port", guest: 80, host: 8085

  # Configuração da rede como bridge e define o IP fixo
  config.vm.network "public_network", bridge: "Realtek 8811CU Wireless LAN 802.11ac USB NIC", ip: "192.168.3.115"

  # Configura a box do Ubuntu Trusty64
  config.vm.box = "ubuntu/trusty64"

  # Configura a quantidade de CPU e o tamanho do disco
  config.vm.provider "virtualbox" do |vb|
    vb.name = "srv-web"
    vb.memory = "1024"
    vb.cpus = 2
  end

  # Instalação de pacotes e configuração
  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
    sudo apt-get install vim curl telnet unzip wget net-tools nmap nginx -y

    # Baixa as Guest Additions
    sudo apt-get install -y virtualbox-guest-utils virtualbox-guest-dkms

    # Monta o CD das Guest Additions
    sudo mount -o loop /usr/share/virtualbox/VBoxGuestAdditions.iso /mnt

    # Executa o instalador
    sudo sh /mnt/VBoxLinuxAdditions.run

    # Desmonta o CD
    sudo umount /mnt

    # Criação de usuário e definição da senha
    sudo useradd -m -s /bin/bash arimateiajunior
    echo "arimateiajunior:Deus@2024" | sudo chpasswd
  SHELL
end
