VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "centos/7"
  config.vm.box_check_update = false

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
  end

  # NGINX
  config.vm.define "vlingx01" do |vlingx01|
    vlingx01.vm.hostname = "vlingx01"
    vlingx01.vm.network "private_network", ip: "172.10.0.3"
    vlingx01.vm.network "forwarded_port", guest: 8081, host: 8081
  end
  # End vlingx01

  # ZK & KAFKA
  config.vm.define "vlikfk01" do |vlikfk01|
    vlikfk01.vm.hostname = "vlikfk01"
    vlikfk01.vm.network "private_network", ip: "172.10.0.11"
  end
  # End vlikfk01

  config.vm.define "vlikfk02" do |vlikfk02|
    vlikfk02.vm.hostname = "vlikfk02"
    vlikfk02.vm.network "private_network", ip: "172.10.0.12"
  end
  # End vlikfk02

  config.vm.define "vlikfk03" do |vlikfk03|
    vlikfk03.vm.hostname = "vlikfk03"
    vlikfk03.vm.network "private_network", ip: "172.10.0.13"
  end
  # End vlikfk03

end
