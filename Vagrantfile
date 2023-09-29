Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"

  config.vm.define "vm1" do |vm1|
    vm1.vm.hostname = "vm1"
    vm1.vm.network "public_network"
    vm1.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
    end

    vm1.vm.provision "shell", inline: <<-SCRIPT
      # Instalação do Apache
      sudo apt update
      sudo apt upgrade
      sudo apt install ufw
      sudo ufw enable
      sudo ufw default deny incoming
      sudo ufw default allow outgoing

    SCRIPT
  end

end