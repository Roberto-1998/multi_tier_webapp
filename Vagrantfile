
Vagrant.configure("2") do |config|
  config.hostmanager.enabled = true   #Le dice a Vagrant que modifique el archivo /etc/hosts de tu ordenador anfitrión (host) para que puedas acceder a las VMs por su nombre (hostname) en lugar de la IP.
  config.hostmanager.manage_host = true #Activa el plugin Hostmanager para que funcione en esta máquina.
  config.hostmanager.manage_guest = true


  config.vm.boot_timeout= 600

  #Mysql Server
  config.vm.define "db01" do |db01|
    db01.vm.box = "eurolinux-vagrant/centos-stream-9"
    db01.vm.hostname = "db01"
    #db01.vm.network "public_network"
    db01.vm.network "private_network", ip: "192.168.50.4"
    db01.vm.provider "virtualbox" do |vb|
      vb.memory = "600"
    end
    db01.vm.provision "shell", path: "./provisioning/mysql.sh"
  end




  #Memcache Server
  config.vm.define "mc01" do |mc01|
    mc01.vm.box = "eurolinux-vagrant/centos-stream-9"
    mc01.vm.hostname = "mc01"
    #mc01.vm.network "public_network"
    mc01.vm.network "private_network", ip: "192.168.50.5"
    mc01.vm.provider "virtualbox" do |vb|
      vb.memory = "600"
    end
    mc01.vm.provision "shell", path: "./provisioning/memcached.sh"
  end




  #RabbitMQ Server
  config.vm.define "rmq01" do |rmq01|
    rmq01.vm.box = "eurolinux-vagrant/centos-stream-9"
    rmq01.vm.hostname = "rmq01"
    #rmq01.vm.network "public_network"
    rmq01.vm.network "private_network", ip: "192.168.50.6"
    rmq01.vm.provider "virtualbox" do |vb|
      vb.memory = "600"
    end
    rmq01.vm.provision "shell", path: "./provisioning/rabbitmq.sh"
  end




  #Tomcat Server
  config.vm.define "app01" do |app01|
    app01.vm.box = "eurolinux-vagrant/centos-stream-9"
    app01.vm.hostname = "app01"
    #app01.vm.network "public_network"
    app01.vm.network "private_network", ip: "192.168.50.7"
    app01.vm.provider "virtualbox" do |vb|
      vb.memory = "600"
    end
    app01.vm.provision "shell", path: "./provisioning/tomcat.sh"
  end




  #Web Server
  config.vm.define "web01" do |web01|
    web01.vm.box = "ubuntu/jammy64"
    web01.vm.hostname = "web01"
    #web01.vm.network "public_network"
    web01.vm.network "private_network", ip: "192.168.50.8"
    web01.vm.provider "virtualbox" do |vb|
      #vb.gui = true #significa que la interfaz gráfica de la máquina virtual (VM) estará habilitada cuando se inicie. Es decir, verás una ventana del sistema operativo Ubuntu (como si iniciaras una VM en VirtualBox manualmente).
      vb.memory = "600"
    end
    web01.vm.provision "shell", path: "./provisioning/web.sh"
  end

end
