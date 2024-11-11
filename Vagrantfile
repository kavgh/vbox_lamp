Vagrant.configure("2") do |config|

    ### Enabling "vagrant-hostmanager" plugin ###
    config.hostmanager.enabled = true
    config.hostmanager.manage_host = true

### DataBase ###
    config.vm.define "db01" do |db|
        db.vm.box = "generic/centos9s"
        db.vm.hostname = "db01"
        db.vm.network "private_network", ip:  "192.168.56.102"
        db.vm.provider "virtualbox" do |vb|
            vb.memory = 1024
        end
    end

### Memory cache ###
    config.vm.define "mc01" do |mc|
        mc.vm.box = "generic/centos9s"
        mc.vm.hostname = "mc01"
        mc.vm.network "private_network", ip: "192.168.56.103"
        mc.vm.provider "virtualbox" do |vb|
           vb.memory = 1024
        end
    end

### RabbitMQ ###
    config.vm.define "rmq01" do |rmq|
        rmq.vm.box = "generic/centos9s"
        rmq.vm.hostname = "rmq01"
        rmq.vm.network "private_network", ip: "192.168.56.104"
        rmq.vm.provider "virtualbox" do |vb|
            vb.memory = "1024"
        end
    end

### Tomcat ###
    config.vm.define "app01" do |app|
        app.vm.box = "generic/centos9s"
        app.vm.hostname = "app01"
        app.vm.network "private_network", ip: "192.168.56.105"
        app.vm.provider "virtualbox" do |vb|
            vb.memory = "1024"
        end
    end

### Nginx ###
    config.vm.define "web01" do |web|
        web.vm.box = "ubuntu/focal64"
        web.vm.hostname = "web01"
        web.vm.network "private_network", ip: "192.168.56.106"
        web.vm.network "public_network", bridge: "enp2s0"
        web.vm.provider "virtualbox" do |vb|
            vb.memory = "1024"
        end
    end

    config.vm.provision :ansible do |ansible|
        ansible.playbook = "playbook.yml"
        ansible.groups = {
            "db" => ["db01"],
            "mc" => ["mc01"],
            "rmq" => ["rmq01"],
            "app" => ["app01"],
            "lb" => ["web01"]
        }
    end

end