VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "puphpet/debian75-x64"
  config.vm.network "forwarded_port", guest: 8006, host: 8006
  config.vm.network "forwarded_port", guest: 3128, host: 3128
  config.vm.provider "virtualbox" do |vb|
     vb.name = "proxmoxtest"
     vb.customize ["modifyvm", :id, "--memory", "512"]
  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "proxmox.yaml"
    #ansible.verbose = "vvvv"
  end
end
