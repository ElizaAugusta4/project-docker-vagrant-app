# Vagrantfile

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64" # Escolha uma box do Ubuntu 18.04 LTS

  config.vm.network "private_network", ip: "192.168.33.10"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024" # Defina a quantidade de memória desejada
    vb.cpus = 2 # Defina a quantidade de CPUs desejada
  end

  config.vm.provision "shell", inline: <<-SHELL
    # Instalação do Docker
    sudo apt-get update
    sudo apt-get install -y docker.io

    # Adiciona seu usuário ao grupo do Docker para executar comandos sem sudo
    sudo usermod -aG docker $USER
  SHELL
end
