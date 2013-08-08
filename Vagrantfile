# -*- mode: ruby -*-
# vi: set ft=ruby :

# GITHUB CONFIGURATION
# Set the following environment variables using export before running vagrant up
GITHUB_CLIENT_ID = ENV["RCLOUD_GITHUB_CLIENT_ID"] || "GITHUB CLIENT ID NOT SET"
GITHUB_SECRET = ENV["RCLOUD_GITHUB_SECRET"] || "GITHUB SECRET NOT SET"

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu"
  config.vm.box_url = "http://files.vagrantup.com/precise64_vmware_fusion.box"

  config.vm.network :forwarded_port, guest: 8080, host: 8080
  config.vm.network :forwarded_port, guest: 8081, host: 8081
  
  # Provision
  provision_cmd = "sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys E084DAB9;" \
    "sudo echo 'deb http://cran.rstudio.com/bin/linux/ubuntu precise/' >> /etc/apt/sources.list;" \
    "sudo apt-get update;" \
    "sudo apt-get install -y r-base-dev libxt-dev libcurl4-gnutls-dev libcairo2-dev;" \
    "sudo apt-get install -y unzip; "\
    "wget https://github.com/cscheid/rcloud/archive/master.zip; unzip master.zip; cd rcloud-master;" \
    "echo -e 'Cookie.Domain: 127.0.0.1' > ./conf/rcloud.conf;" \
    "echo -e '#{GITHUB_CLIENT_ID}\n#{GITHUB_SECRET}\nhttps://github.com/\nhttps://api.github.com/' > ./conf/github_info.txt; " \
    "sudo sh ./scripts/fresh_start.sh"

  config.vm.provision :shell,
    :inline => provision_cmd
end
