centos_ip = '192.168.0.100'
ubuntu_ip = '192.168.0.101'

Vagrant.configure("2") do |config|

  config.vm.define "centos" do |centos|
    centos.vm.box = "centos/7"
    centos.vm.hostname = "centos"
    centos.vm.network "private_network", ip: centos_ip

      centos.vm.provider "libvirt" do |lv|
        lv.memory = 2048
        lv.cpus = 4
      end
  end

  config.vm.define "ubuntu" do |ubuntu|
    ubuntu.vm.box = "generic/ubuntu1804"
    ubuntu.vm.hostname = "ubuntu"
    ubuntu.vm.network "private_network", ip: ubuntu_ip

      ubuntu.vm.provider "libvirt" do |lv|
        lv.memory = 1024
        lv.cpus = 2
      end
  end
  
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "validacao.yml"
  end
 
end
