Vagrant.configure("2") do |config|

    config.vm.provider "virtualbox" do |v|
      v.memory = 2048
      v.cpus = 2
    end
    
    config.vm.define "local", primary: true do |local|

        local.vm.box = "ubuntu/trusty64"

        local.vm.network :private_network, ip: "192.168.33.102"

        local.vm.synced_folder "./", "/vagrant"
        
        config.vm.provision "ansible" do |ansible|
            ansible.playbook = "ansible/playbook.yml"
        end
    end
end
