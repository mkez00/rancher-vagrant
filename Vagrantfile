Vagrant.configure("2") do |config|

  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "2048", "--cpus", "2"]
  end

  config.vm.define "rancher" do |c|
    c.vm.box = "ubuntu/xenial64"
    c.vm.hostname = "rancher"
    c.vm.network "private_network", ip: "192.168.56.101"
    c.vm.synced_folder "data", "/data"

    c.vm.provision "shell", inline: <<-SHELL
      sudo su
      apt update
      apt install docker.io -y
      docker image pull rancher/server:stable
      docker run -d --restart=unless-stopped -p 8080:8080 rancher/server:stable
    SHELL
  end

  config.vm.define "node1" do |c|
    c.vm.box = "ubuntu/xenial64"
    c.vm.hostname = "node1"
    c.vm.network "private_network", ip: "192.168.56.102"
    c.vm.synced_folder "data", "/data"

    c.vm.provision "shell", inline: <<-SHELL
      sudo su
      apt update
      apt install docker.io -y
    SHELL
  end

  config.vm.define "node2" do |c|
    c.vm.box = "ubuntu/xenial64"
    c.vm.hostname = "node2"
    c.vm.network "private_network", ip: "192.168.56.103"
    c.vm.synced_folder "data", "/data"

    c.vm.provision "shell", inline: <<-SHELL
      sudo su
      apt update
      apt install docker.io -y
    SHELL
  end

 end
