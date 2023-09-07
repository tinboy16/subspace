Manual
Create folder and copy 2 file docker-compose.yaml + .env inside each folder
cd $HOME
mkdir node1
cd node1
wget -O docker-compose.yaml https://raw.githubusercontent.com/tinnguyen162002/subtest/main/docker-compose.yaml
wget -O .env https://raw.githubusercontent.com/tinnguyen162002/subtest/main/.env
you can check which port you are using by this command
lsof -i -P -n | grep LISTEN
After finished download, you need to change variable inside file .env
each file .env should be another ports, another node name, another reward address
nano .env
Some command
start a node
docker compose up -d
show all docker running
docker ps
show logs
docker compose logs -f --tail=100 | grep <container-name>
stop a node
docker compose down
If you want run the second node or n node, just change the code here, node2 --> noden
cd $HOME
mkdir node2
cd node2
wget -O docker-compose.yaml https://raw.githubusercontent.com/owlstake/testnet/main/subspace/docker-compose.yaml
wget -O .env https://raw.githubusercontent.com/tinnguyen162002/subtest/main/.env

Change ports, nodename, reward address inside .env file
nano .env

docker compose up -d
grep 'SS58 Address:' backupkey.txt | sed 's/^.*: //' | sed -r 's/\s+//g'
