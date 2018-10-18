Bitcoind for Docker
===================

Requirements
------------

* At least 100 GB to store the block chain files (and always growing!)
* At least 1 GB RAM + 2 GB swap file

docker build -t coinbold/bitcoind .

docker run -v bitcoind-data:/bitcoin 
                --name=bitcoind-node -d      
                -p 8333:8333
                -p 127.0.0.1:8332:8332
                -e DISABLEWALLET=0
                -e PRINTTOCONSOLE=1
                -e RPCUSER=mysecretrpcuser
                -e RPCPASSWORD=mysecretrpcpassword 
                coinbold/bitcoind


docker logs bitcoind-node