## Block Explorer Setup

sudo apt-get update
sudo apt install nodejs:i386
sudo apt-get install npm
sudo apt-get install
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv EA312927
echo "deb http://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.2.list
sudo apt-get update
sudo apt-get install -y mongodb-org
sudo systemctl start mongod
sudo npm install forever -g
mongo 
use explorerdb
db.createUser( { user: "iquidus", pwd: "3xp!0reR", roles: [ "readWrite" ] } )
exit
git clone https://github.com/farsider350/explorer-aus explorer
git checkout auscash
cd explorer && npm install --production
cp ./settings.json.template ./settings.json

Change settings in settings.json ------------------

conf file for auscash needs
server = 1
rpcuser = auscash
rpcpassword = a password you choose
rpcallowip = 127.0.0.1
reindex = 1
txindex = 1


Start daemon or QT

cd ~/explorer/
npm start
node scripts/sync.js index reindex
node scripts/sync.js index update

setup system crontab for the node update script to run every minute or two.
