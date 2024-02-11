# vagrant-srv_web
Servidor Web Nginx - Vagrant
Criação de um Servidor Web Nginx aprovisionado pelo Vagrant

Seguem as definições exploradas no Vagranfile:

  # Define o nome da máquina como srv-web
  # Exposição do nginx na porta 8085
  # Configuração da rede como bridge e define o IP fixo
  # Configura a box do Ubuntu Trusty64
  # Configura a quantidade de CPU e o tamanho do disco
  # Instalação de pacotes
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
  

