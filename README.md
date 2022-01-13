# Hyperledger Fabric Tutorial:

The hyper ledger is a project in which you have diff frameworks and tools avalible.
one of this is hyperledger fabric


### About Public Blockchain:
- `bitcoin blockchain:` It only store trasactions / data .This network cannot be used to do programming. 

- Change the existing internet to new internet which is the decetralised internet. To achive that we have to write softwares which run on this decentralised internet. These softwares are called Dapps.

- In Etherium, not only data but also softwares which run on blockchain network.

- The main problem of public blockchain is that it is transparent.
- The main advantage of public blockchain is consennsus protocol 
  - proof of work and proof of stake


### About Private Network: 
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

- The network N, accessed by a set of users defined by a Certificate Authority CA4, who have a set of rights over the resources in the network N as described by policies contained inside a network configuration NC4. All of this is made real when we configure and start the ordering service node O4.

- Think of smart contracts as governing transactions, whereas chaincode governs how smart contracts are packaged for deployment.

