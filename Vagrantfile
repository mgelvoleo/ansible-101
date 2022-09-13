Vagrant.configure("2") do |config|
  
  config.vm.box = "bento/ubuntu-22.04"

  config.ssh.insert_key = false

  config.vm.synced_folder ".", "/vagrant", disabled: false

  config.vm.provider :virtualbox do |v|
    v.memory = 512
    v.linked_clone = true
  end

  # workstation
  config.vm.define "workstation" do |workstation|
     workstation.vm.hostname = "workstation"
     workstation.vm.network :private_network, ip: "192.168.60.10"
 end


  # server1
  config.vm.define "server1" do |server1|
    server1.vm.hostname = "server1"
    server1.vm.network :private_network, ip: "192.168.60.11"
   
    server1.vm.provider "virtualbox" do |server1|
	server1.memory = 512
    end
  end

  #server2
  config.vm.define "server2" do |server2|
    server2.vm.hostname = "server2"
    server2.vm.network :private_network, ip: "192.168.60.12"

    server2.vm.provider "virtualbox" do |server2|
        server2.memory = 512
    end
  end

  #server3
  config.vm.define "server3" do |server3|
    server3.vm.hostname = "server3"
    server3.vm.network :private_network, ip: "192.168.60.13"
    server3.vm.box = "bento/centos-stream-8"
    server3.vm.provider "virtualbox" do |server3|
        server3.memory = 512
    end
  end
 

end
