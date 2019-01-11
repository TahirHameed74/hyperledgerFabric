# hyperledgerFabric


How to start this network:
You will need to install some components to run this project:

Note: Install npm first then do following.

1) npm install -g composer-cli@0.20

2) npm install -g composer-rest-server@0.20

3) npm install -g generator-hyperledger-composer@0.20

4) npm install -g yo

5) npm install -g composer-playground@0.20

Now, In a directory of your choice run this command now:

6) mkdir ~/fabric-dev-servers && cd ~/fabric-dev-servers

curl -O https://raw.githubusercontent.com/hyperledger/composer-tools/master/packages/fabric-dev-servers/fabric-dev-servers.tar.gz
tar -xvf fabric-dev-servers.tar.gz

Now, go this directory named "fabric-dev-servers" to do this run:

7) cd ~/fabric-dev-servers
export FABRIC_VERSION=hlfv12
./downloadFabric.sh

8)     cd ~/fabric-dev-servers
    export FABRIC_VERSION=hlfv12
    ./startFabric.sh
    ./createPeerAdminCard.sh

9)    composer-playground   


Now as i provided this hyperledger fabric you need to run this command from terminal in myapprose directory to do this:

10) composer archive create -t dir -n .

11) composer network install --card PeerAdmin@hlfv1 --archiveFile environmentapi@0.0.1.bna

12) composer network start --networkName environmentapi --networkVersion 0.0.1 --networkAdmin admin --networkAdminEnrollSecret adminpw --card PeerAdmin@hlfv1 --file networkadmin.card

13) composer card import --file networkadmin.card

14) composer network ping --card admin@environmentapi

Now you have install all things you need for this spevific project:

To run your REST API run following command:
composer-rest-server -c admin@environmentapi -n never -a true -m true -u true -d N -w true

To run angular app goto environmentapi folder within environmentapi folder(both folders with same name) and run:

npm start

Thats it! We are done :)







