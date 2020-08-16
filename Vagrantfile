Vagrant.configure("2") do |config|
  config.ssh.insert_key = false
  config.vm.synced_folder ".", "/vagrant", disabled: true
 
  if Vagrant.has_plugin?("vagrant-hostmanager")
     config.hostmanager.enabled = true
     config.hostmanager.manage_host = true
     config.hostmanager.ignore_private_ip = false
     config.hostmanager.include_offline = true
    end

  config.vm.define "web1", primary: true do |web1|
    web1.vm.box = "geerlingguy/ubuntu2004"
    web1.vm.hostname = "web1"
    web1.vm.network "private_network", ip: "192.168.60.11"
  end
   
  config.vm.define "web2" do |web2|
    web2.vm.box = "geerlingguy/ubuntu2004"
    web2.vm.hostname = "web2"
    web2.vm.network "private_network", ip: "192.168.60.12"
  end
end


