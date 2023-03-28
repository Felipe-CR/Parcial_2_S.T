Vagrant.configure("2") do |config|

  if Vagrant.has_plugin? "vagrant-vbguest"
     config.vbguest.no_install = true
     config.vbguest.auto_update = false
     config.vbguest.no_remote = true
  end
  config.vm.define :esclavo do |esclavo|
    esclavo.vm.box = "bento/centos-7.9"
    esclavo.vm.network :private_network, ip: "192.168.100.5"
    #esclavo.vm.provision "shell", path: "script-esclavo.sh.txt"
    esclavo.vm.hostname = "esclavo"
    esclavo.vm.provider "virtualbox" do |v|
      v.cpus = 2 
    end
  end
  config.vm.define :firewalld do |firewalld|
    firewalld.vm.box = "bento/centos-7.9"
    firewalld.vm.network :private_network, ip: "209.191.100.3"
    firewalld.vm.network :private_network, ip: "192.168.100.3"
    #firewalld.vm.provision "shell", path: "script-firewall.sh.txt"
    firewalld.vm.hostname = "firewall"
    firewalld.vm.provider "virtualbox" do |v|
      v.cpus = 2 
    end
  end
  config.vm.define :maestro do |maestro|
    maestro.vm.box = "bento/centos-7.9"
    maestro.vm.network :private_network, ip: "192.168.100.4"
    #maestro.vm.provision "shell", path: "script-maestro.sh.txt"
    maestro.vm.hostname = "maestro"
    maestro.vm.provider "virtualbox" do |v|
      v.cpus = 2 
    end
  end
end
