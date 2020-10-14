Vagrant.configure("2") do |config|
    config.vm.box = "bento/ubuntu-18.04"
    config.vm.box_check_update = false
    config.vm.define "webdev", primary: true do |machine|
        machine.vm.hostname = "webdev"
        machine.vm.network "private_network", ip: "192.168.33.11"
        machine.vm.provider "virtualbox" do |vb|
            vb.name = "webdev"
            vb.gui = false
            vb.memory = 8092
            vb.cpus = 4
        end
        machine.vm.provision :ansible_local do |ansible|
            ansible.verbose = "v"
            ansible.playbook = "./ansible/playbook.yml"
        end
    end
end