Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  #config.vm.network "private_network", ip: "192.168.0.2"
  #config.vm.synced_folder ".", "/vagrant", type: "nfs"

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "main.yml"
  end
end
