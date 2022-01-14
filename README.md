# Hyperledger Fabric Tutorial:

The hyper ledger is a project in which you have diff frameworks and tools avalible.
one of this is hyperledger fabric


## About Public Blockchain:
- `bitcoin blockchain:` It only store trasactions / data .This network cannot be used to do programming. 

- Change the existing internet to new internet which is the decetralised internet. To achive that we have to write softwares which run on this decentralised internet. These softwares are called Dapps.

- In Etherium, not only data but also softwares which run on blockchain network.

- The main problem of public blockchain is that it is transparent.
- The main advantage of public blockchain is consennsus protocol 
  - proof of work and proof of stake


## About Private Network: 

![pvt blockchain channel](Screenshot-pvtblock-1.png)
- Private Blockchain Networks are `private and permissioned`. create a subnet for business to keep their transactions private.
- The HyperLedger is a project open source project by Liux foudation. The HyperLedger fabric is one of that project.   
- Fabric is a pvt blockchain network and it have the subnets features and we call them as `channels`.
- The enrollment to the network can only be done through `MSP(Membership Service Provider)`.The members of a Hyperledger Fabric network enroll through a trusted `Membership Service Provider (MSP)`.
- we can write `smart contracts` in hyperledger fabric with the help of `chaincode`.The chaincode can be written in JS,Java,GO language.The Fabric is build in GO so they prefer using Go language to build chaincode.
- The `Ledger` is kind of like a database but in hyperledger fabric leger is divided into 2 parts : (2 comp of ledger)
  1. `World State:` Current state of data / real state of data can be fetched from world data (who has the asset right now). 
    - Get this by using some RDBMS : couchDB or levelDB.
  3. `Transaction Log:` To find the source of the assest (where). so this is like a transaction logs. This can be stored in simple plain file.

- `If u are wroking with hyperlegder fabic, you have to work with the channel. Each channel will have peers and each peer will have chaincode.`

CCP files = Common Connection Profile(CCP):
Anchor peers:
endorsor peers:
order peers:

## Understanding Key Concepts:

- Network - N
- orgaisation - R
- Network Config - NC
- Certificate Authority - CA : Diff org have diff CA's
- Orderer of peer - O
- Consortium - X : It is the collection of multiple org attaining the same goals. `“a group with a shared destiny”`
- Channel - C
- Channel Config -CC
- Peer - P
- Ledger - L
- Smart Contract - S

![network diagram](networkdiagram1.png)
- The network N, accessed by a set of users defined by a Certificate Authority CA4, who have a set of rights over the resources in the network N as described by policies contained inside a network configuration NC4. All of this is made real when we configure and start the ordering service node O4.

- Think of smart contracts as governing transactions, whereas chaincode governs how smart contracts are packaged for deployment.


### Prerequisites:

> sudo apt-get install git

- cURL
  > sudo apt-get install curl
- install docker
  > sudo apt-get -y install docker-compose
- Make sure the Docker daemon is running.
  > sudo systemctl start docker
- install go
- install JQ (only required if you will be writing Go chaincode or SDK applications).

### Download the latest release of Fabric samples, docker images, and binaries:

> curl -sSL https://bit.ly/2ysbOFE | bash -s [version-no]

## Fabric 1.0:

[fabric-samples/firstt-network/]

> ./byfn.sh
> ./byfn.sh generate
> ./byfn.sh up
> ./byfn.sh down  
> ./byfn.sh up -l java
> docker rm -f $(docker ps -aq)
> docker rmi -f $(docker images | grep fabcar | awk '{print $3}')

## Fabric 2.0 :

Using the Fabric test network:

> ./network.sh down
> ./network.sh up
> docker ps -a
> ./network.sh createChannel -c [channel-name]

### Basic Network 2.0:

https://github.com/adhavpavan/BasicNetwork-2.0.git

#### Network Details:

- Two Organizations
- Two peers in each Orgaisation
- One CA for each Organisation
- 5 Orderer(RAFT)
- State Database: Couch DB
  - why use Couch DB over level DB ? It enables to run complex queries.

#### Folder Structure:

- It is created by taking ref from first network and test network of their official documentation.
- app folder: this is used when we write our API's
- Artifacts folder: one of the most imp folder in fabric network.
  - `channel`
    - configtx.yaml
    - crypto-config.yaml
    - `config`
      - core.yaml
  - `src`: will have our smart contracts that is the chaincode. fabic 2.0 have introduced a contract api for writing the chain code which support multiple smart contacts within a single chain
  - base.yml: this is the common part for starting the peer.
  - `docker-compose.yaml`: will have all the services we require for creating our network.
  - network-config.yaml:diff files which will require for writing the APIs in node
  - org1.yaml: this the connection profile file which will be required for writing the api's
  - `chanel.artifacts`
  - app.js : This is to create a server to interact with the network
  - cleanup.sh:to clean the network
  - `crypto-config` : here we will have all the identities certificate,public , private keys of all the organisations
    - org 1: structure will be common for all our identities.
      - ca
        - ca certificate and pvt key
      - msp
        - admincerts
        - cacerts
        - tlccacerts
      - peers: we can have multiple peers in network of org
        - each peers will have msp and tls.
        - `msp`
          - keystore : were the pvt key gets stored
          - signcerts:this is the certificate of this peer.
      - tlsca(trasport layer security)
      - users
  - config.js and config.json is used to write APIs.
  - depoloyChaincode.sh

#### crypto-config.yaml : Create Idetities

#### configtx.yaml : create channel artifacts

