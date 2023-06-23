# dockerinstall

'''

#!/bin/bash

docker -v

if command -v docker &>/dev/null; then
    echo "already installed"
    echo "uninstalling"
    sudo docker stop $(sudo docker ps -aq)
    sudo docker rm $(sudo docker ps -aq)
    sudo docker rmi $(sudo docker images -q)
    sudo apt-get purge -y docker-ce docker-ce-cli containerd.io
    sudo apt-get autoremove -y --purge docker-ce docker-ce-cli containerd.io
    sudo rm -rf /var/lib/docker
    sudo groupdel docker
fi

echo "installing"

sudo apt-get update
# sudo apt ins

sudo apt-get update
# sudo apt install -y apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" -y
sudo apt-get update
sudo apt install -y docker-ce
sudo apt install docker-compose -y
sudo service docker start

docker -v

if command -v docker &>/dev/null; then
    echo "installation done!"
else
    echo "installation failed!"
fi

'''
