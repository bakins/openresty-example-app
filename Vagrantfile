Vagrant.configure("2") do |config|
  config.vm.box = "precise64"
  config.vm.box_url = "http://files.vagrantup.com/precise64.box"
  config.omnibus.chef_version = :latest
  config.vm.network :forwarded_port, guest: 5000, host: 5000
  config.ssh.forward_agent = true

  config.vm.provision :shell, :inline => <<EOF
cd /tmp
apt-get install -y git-core curl
git clone https://github.com/bakins/openresty-buildpack.git
/tmp/openresty-buildpack/bin/compile /vagrant
EOF

end
