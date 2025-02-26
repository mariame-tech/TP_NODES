Vagrant.configure("2") do |config|
  config.vm.define "dbserver" do |dbserver|
    dbserver.vm.box = "bento/ubuntu-22.04"
    dbserver.vm.box_check_update = false
    dbserver.vm.network "forwarded_port", guest: 84, host: 9096
    dbserver.vm.network "private_network", ip: "192.168.33.11"
    dbserver.vm.synced_folder "./db", "/var/www/html"
    dbserver.vm.provider "virtualbox" do |vb|
      vb.gui = false
      vb.memory = "1024"
      vb.name = "dbserver"
    end
  end   
  config.vm.define "webserver" do |webserver|
    webserver.vm.box = "bento/ubuntu-22.04"
    webserver.vm.box_check_update = false
    webserver.vm.network "forwarded_port", guest: 82, host: 8086
    webserver.vm.network "private_network", ip: "192.168.33.10"
    webserver.vm.synced_folder "./web", "/var/www/html"
    webserver.vm.provider "virtualbox" do |vb|
      vb.gui = false
      vb.memory = "1024"
      vb.name = "webserver"
    end
  end  
end