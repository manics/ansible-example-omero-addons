Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.provider "virtualbox" do |vb|
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "forwarded_port", guest: 443, host: 8443
  config.vm.network "forwarded_port", guest: 4063, host: 4063
  config.vm.network "forwarded_port", guest: 4064, host: 4064
    vb.customize ["modifyvm", :id, "--memory", "2048"]
  end

  config.vm.provision "ansible" do |ansible|   
    ansible.playbook = "playbook.yml"    
    ansible.galaxy_role_file = "../requirements.yml"   
  end
end
