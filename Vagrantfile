Vagrant.configure("2") do |config|
  config.vm.provider :libvirt do |v,override|
    override.vm.box = "centos/7"
  end
  
  config.vm.provider :libvirt do |lv|
    lv.memory = 1024
    lv.cpus = 2
  end

  config.vm.define "dbserver" do |m|
    m.vm.hostname ="dbserver.local"
    m.vm.network "private_network", ip: "192.168.0.100"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "validacao.yml"
  end

  end