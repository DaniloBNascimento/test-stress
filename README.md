# test-stress

# requirements
ubuntu 20.04 LTS

# install node-js

sudo apt update
sudo apt -y upgrade
sudo apt update
sudo apt -y install curl dirmngr apt-transport-https lsb-release ca-certificates
curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
sudo apt -y install nodejs

# install artillery.io

sudo su
npm install -g artillery


Arquivo de teste:

# Crie 80000 usuários virtuais em 60 segundos (aproximadamente um a cada 3 segundos):

config:
  target: "http://191.239.116.63"
  phases:
    - duration: 20
      arrivalCount: 80000
scenarios:
  - flow:
      - get:
          url: "/"
          
# command for run artillery EXAMPLE:
artillery run --output test-1.json test1-stress.yaml
