Vagrant.configure("2") do |c|
  c.berkshelf.enabled = false if Vagrant.has_plugin?("vagrant-berkshelf")
  c.vm.box = "mwrock/Windows2016"
  c.vm.hostname = "win2016"
  c.vm.communicator = "winrm"
  c.vm.network(:private_network, {:ip=>"172.28.128.12"})
  c.vm.synced_folder ".", "/vagrant", disabled: true
  c.vm.provider :virtualbox do |p|
    p.name = "kitchen-ansible-windows-hardening-win-win-2016"
    p.gui = false
    p.linked_clone = true
  end
  c.vm.provision :shell do |shell|
    shell.path = "https://raw.githubusercontent.com/ansible/ansible/devel/examples/scripts/ConfigureRemotingForAnsible.ps1"
  end
end
