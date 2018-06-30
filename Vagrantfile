Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  #config.vm.network "private_network", ip: "192.168.0.2"
  config.vm.synced_folder ".", "/vagrant", type: "virtualbox"


  config.vm.provider "virtualbox" do |vb|
    vb.customize ["modifyvm", :id, "--usb", "on"]
    vb.customize ["modifyvm", :id, "--usbehci", "on"]
    vb.customize ["usbfilter", "add", "0",
    "--target", :id,
    "--name", "Arduino USB",
    "--manufacturer", "Arduino (www.arduino.cc)",
    "--product", "Arduino Uno"]
  end

  config.vm.provision "ansible_local" do |ansible|
    ansible.verbose = "vvv"
    ansible.playbook = "core.yml"
  end
end
