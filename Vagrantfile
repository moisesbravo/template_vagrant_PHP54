# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure('2') do |config|

  # Sistema operativo
  config.vm.box = 'ubuntu/trusty64'
  #config.vm.box_url ="https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-juju-vagrant-disk1.box"
  # IP privada
  config.vm.network 'private_network', ip: '10.0.0.100'

  # Configuración de VirtualBox
  config.vm.provider :virtualbox do |vb|

    # Nombre de la máquina virtual
    vb.name = 'desarrollokcc'

    # Memoria
    vb.memory = 2048

    # Número de procesadores
    vb.cpus = 2

  end

config.vm.synced_folder "./", "/vagrant", id: "vagrant-root"
config.vm.synced_folder "./source", "/var/www/html", :nfs => true
  # Habilitar aprovisionamiento por Puppet
  config.vm.provision :puppet do |puppet|
     puppet.manifests_path = "puppet/manifests"
     puppet.module_path = "puppet/modules"
       puppet.options = ['--verbose']

  end

end