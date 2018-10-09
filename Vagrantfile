Vagrant.configure("2") do |config|

  config.vm.provider "virtualbox" do |vbox|
    vbox.customize ['modifyvm', :id, '--clipboard', 'bidirectional'] 
    vbox.customize ["modifyvm", :id, "--vram", "64"]
    vbox.memory = 2048
    vbox.cpus = 2
    vbox.gui = true
  end
  config.vm.box = "centos/7"
  #config.vm.network "private_network", ip: "192.168.0.2"
  config.vm.synced_folder ".", "/vagrant", type: "virtualbox"


  config.vm.provision "ansible_local" do |ansible|
    ansible.verbose = "vvv"
    ansible.galaxy_role_file = 'requirements.yml'
    ansible.playbook = "main.yml"
  end
end
