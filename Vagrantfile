IP = "192.168.12.10"
NOME_IMAGEM = "centos/7"

ssh_pub_key = File.readlines("#{Dir.home}/.ssh/id_rsa.pub").first.strip

Vagrant.configure("2") do |config|
    config.ssh.insert_key = false

    config.vm.provider "virtualbox" do |v|
        v.memory = 4096
        v.cpus = 2
    end
      
    config.vm.define "vm" do |vm|
        vm.vm.box = NOME_IMAGEM
        vm.vm.network "private_network", ip: "#{IP}"
        vm.vm.hostname = "vm"     

        config.vm.provision 'shell', inline: "echo #{ssh_pub_key} >> /home/vagrant/.ssh/authorized_keys", privileged: false
        
        #config.vm.provision "ansible" do |ansible|
        #    ansible.limit = "all"
        #    ansible.playbook = "roles/main.yml"
        #    ansible.inventory_path = "roles/hosts"
        #end
    end    
end