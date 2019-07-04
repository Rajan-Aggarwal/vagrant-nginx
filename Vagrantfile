Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/trusty64"
	
	config.vm.provider "virtualbox" do |v|
		vb.memory = 2048 # 2 GB of memory
		vb.cpus = 4
	end

	# Network forwarding
	config.vm.network "private_network", ip: "192.168.33.10"
	# in order to add a dns
	# add an entry in /etc/hosts

	# sync with index file of localmachine
	config.vm.synced_folder ".", "/var/www/html", :nfs => {
		:mount_options => ["dmode=777", "fmode=666"]
	}
	
	config.vm.provision "shell", path: "setup.sh"

end
