# BuildingABlockchainApplicationOutsideofComposer

## Instructions for setting the blockchainNetwork

### Open a new terminal and run the following command:
```bash
export FABRIC_CFG_PATH=$(pwd)
chmod +x cryptogen
chmod +x configtxgen
chmod +x generate-certs.sh
chmod +x generate-cfgtx.sh
chmod +x docker-images.sh
chmod +x build.sh
chmod +x clean.sh
./build.sh
```

###  Check the logs

**Command**
```bash
docker logs blockchain-setup
```
**Output:**
```bash
Register CA fitcoin-org
CA registration complete  FabricCAServices : {hostname: fitcoin-ca, port: 7054}
Register CA shop-org
CA registration complete  FabricCAServices : {hostname: shop-ca, port: 7054}
info: [EventHub.js]: _connect - options {"grpc.ssl_target_name_override":"shop-peer","grpc.default_authority":"shop-peer"}
info: [EventHub.js]: _connect - options {"grpc.ssl_target_name_override":"fitcoin-peer","grpc.default_authority":"fitcoin-peer"}
Default channel not found, attempting creation...
Successfully created a new default channel.
Joining peers to the default channel.
Chaincode is not installed, attempting installation...
Base container image present.
info: [packager/Golang.js]: packaging GOLANG from bcfit
info: [packager/Golang.js]: packaging GOLANG from bcfit
Successfully installed chaincode on the default channel.
Successfully instantiated chaincode on all peers.
```


###  Check the blockchainNetwork

Execute the following commands to perform invoke and query operations on network:
```bash
cd configuration
export LOCALCONFIG=true
node config.js
cd ..
cd test/
npm install
node index.js
```
