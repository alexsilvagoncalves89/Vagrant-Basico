# Aprendendo Vagrant baseado nos DOCs da HASHICORP
# Projeto WebServer
# - Objetivo
# - Subir uma Vagrant Box no VirtualBox via Vagrantfile
# - Definir um script para implementar na imagem o Apache2 + uma página HTML simples
# - Compartilhar uma porta entre o GUEST e o HOST e acessar pelo no HOST a página HTML
# - Compartilhar a página na Internet via ngrok (Expor na Internet)

# -- Configuração Inicial -- #
Vagrant.configure("2") do |config|

# -- Definindo qual será o image box a ser instalada -- #
  config.vm.box = "hashicorp/bionic64"
  
# -- Definindo a versão diretamente -- #
  config.vm.box_version = "1.0.282"
  
# -- Definindo o nome do host convidado -- #
  config.vm.hostname = "WebServer-bionic64"

# -- Definindo o nome na GUI do VirtualBox -- # 
  config.vm.define "WebServer-bionic64"

# -- Especificando no Provider e o nome na GUI do VirtualBox -- #
# -- Definindo o nome na GUI em vb.name -- #
  config.vm.provider :virtualbox do |vb|
    vb.name = "VM-WebServer"
  end  
# -- Fim do (do) do config.vm.provider -- #
  
# -- Definindo a versão via URL -- #
# config.vm.box_url = "https://vagrantcloud.com/hashicorp/bionic64"
  
# -- Configurando porta de comunicação entre Host e Guest -- #
  config.vm.network :forwarded_port, guest:80, host: 4567
  
# -- Shell Scrip da configuração e instalação no Guest -- #
  config.vm.provision :shell, path: "bootstrap.sh"
end
# -- Fim do (do) Loop do Vagrant.configure -- #