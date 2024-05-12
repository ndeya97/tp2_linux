Vagrant.configure("2") do |config|

  config.vm.define "control-plane" do |controlplane|

    controlplane.vm.box = "bento/ubuntu-22.04"

    controlplane.vm.box_check_update = false

    controlplane.vm.network "forwarded_port", guest: 8080, host: 8084

    controlplane.vm.network "private_network", type: "static", ip: "192.168.0.12"

    controlplane.vm.synced_folder "./tomcatwebapps", "/opt/tomcat/webapps"

    controlplane.vm.provider "virtualbox" do |vb|

      vb.gui = false
      vb.name = "control-plane"
      vb.memory = "1024"
    end
  end

  config.vm.define "node1" do |node1|

    node1.vm.box = "bento/ubuntu-22.04"

    node1.vm.box_check_update = false

    node1.vm.network "forwarded_port", guest: 8080, host: 8085

    node1.vm.network "private_network", type: "static", ip: "192.168.0.13"

    node1.vm.synced_folder "./tomcatwebapps", "/opt/tomcat/webapps"

    node1.vm.provider "virtualbox" do |vb|

      vb.gui = false
      vb.name = "node1"
      vb.memory = "1024"
    end
  end
end
