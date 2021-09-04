Vagrant.configure("2") do |config|
  config.vm.define 'ubuntu' do |ubuntu_victim|
    ubuntu_victim.vm.box = "generic/ubuntu1804"
    ubuntu_victim.vm.network "public_network"
    ubuntu_victim.vm.network "private_network", type: "dhcp"

    # Prevent SharedFoldersEnableSymlinksCreate errors
    ubuntu_victim.vm.synced_folder ".", "/vagrant", disabled: true
  end
  
  config.vm.define 'kali' do |kali_attacker|
    kali_attacker.vm.box = "kalilinux/rolling"
    kali_attacker.vm.network "public_network"
    kali_attacker.vm.network "private_network", type: "dhcp"
    
    # Prevent SharedFoldersEnableSymlinksCreate errors
    kali_attacker.vm.synced_folder ".", "/vagrant", disabled: true
  end  

end
