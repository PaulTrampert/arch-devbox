Vagrant.configure("2") do |config|
  config.vm.box = "archlinux/archlinux"
  config.vm.hostname = "arch-devbox"

  config.vm.provider "virtualbox" do |v|
    v.name = "Arch Devbox"
    v.memory = 16348
    v.cpus = 6
    v.gui = true
    v.customize ["modifyvm", :id, "--vram", "256"]
    v.customize ["modifyvm", :id, "--clipboard", "bidirectional"]
    v.customize ["modifyvm", :id, "--draganddrop", "bidirectional"]
    v.customize ["modifyvm", :id, "--accelerate3d", "on"]
  end

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "playbook.yml"
  end
end
