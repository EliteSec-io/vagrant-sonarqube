$script = <<-SCRIPT
# Install Docker - Instructions: https://docs.docker.com/v17.09/engine/installation/linux/docker-ce/ubuntu/
sudo apt update
sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
sudo apt update
sudo apt install -y docker-ce
sudo usermod -aG docker $USER
sudo systemctl enable docker
sudo sysctl -w vm.max_map_count=262144
sudo sysctl -w fs.file-max=65536
ulimit -n 65536
ulimit -u 4096
docker pull sonarqube
docker run -d --restart always --name sonarqube -p 9000:9000 sonarqube
SCRIPT

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"
  config.vm.network "private_network", type: "dhcp"
  config.vm.network "forwarded_port", guest: 9000, host: 9000
  config.vm.provision "shell", inline: $script
  config.vm.provider "virtualbox" do |v|
    v.name = "Sonarqube"

    # 4GB of RAM with 2 CPUs - adjust as needed
    v.memory = 4096 
    v.cpus = 2
  end
  config.vm.synced_folder ".", "/vagrant", disabled: true
end