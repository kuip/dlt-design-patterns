# Distributed Ledger Technologies / Blockchain : Software Design Patterns


## Principles

### Immutability

Blockchains are immutable.

### Atomicity

Entire operation runs or none of it does.

### Asynchrony

Blockchains are designed to run on any number of computers/nodes.

### Consensus

Uses algorithms to reach Distributed Consensus.

### Reliability

Algorithms assume that network is not reliable.

### Synchrony

No two operations can interfere with each other.

### Provenance

All method calls can be inspected to determine caller address.


## Data Patterns

### Merkel Tree

![Merkel Tree](/images/merkel_tree.png "Merkel Tree")


Where node[1.1].hash = hash(concatenate(node[1.1.1].hash,node[1.1.2].hash))
etc.

#### Applications
+ Git
+ Modern File Systems

### Merkel Trie / Blockchain

![Merkel Trie](/images/merkel_trie.png "Merkel Trie")

Where root[i+1].hash = hash(concatenate(root[i].hash,block[i].hash))
etc.

#### Applications
+ Blockchain

### Block

![Block](/images/block.png "Block")


#### Applications
+ Blockchain

### Transaction

![Transaction](/images/transaction.png "Transaction")

#### Applications
+ Blockchain

## Behavior Patterns

### Singleton

![Singleton](/images/singleton.png "Singleton")

One single instance of:
+ data
+ behavior
+ events

#### Applications
+ Blockchain

### (Smart) Contract

![Contract](/images/contract.png "Contract")

#### Mortal Contract

By default the contracts are immortal. They could trap funds if they cannot be stopped from operation.


![Mortal Contract](/images/mortal.png "Mortal Contract")

### Contract Interoperativity

![ERC20](/images/erc20.png "ERC20")
Contract1, 2, 3 are interoperable

### Oracle

![Oracle](/images/oracle.png "Oracle")

### Observer/Judge

![Observer](/images/observer.png "Observer")

A more detailed UML and implementation: [ontrack-dapp](https://github.com/loredanacirstea/ontrack-dapp)

## Composite Patterns

### Twin Contracts

Twin smart contracts usually are born and die together. Also the transcations they initiate are born in synchronicity and atomically in mirror on their respective newtorks.

![Twin Contracts](/images/twin.png "Twin Contracts")

### Contract Factory

![Contract Factory](/images/factory.png "Contract Factory")

### Contract of Contracts

A contract that implements contract factory for any number of contracts.


## Terminology (from Ethereum)

### External Actor
A person or other entity able to interface to an Ethereum node, but external to the world of Ethereum. It can interact with Ethereum through depositing signed Transactions and inspecting the blockchain and associated state. Has one (or more) intrinsic Accounts.
### Address
A 160-bit code used for identifying Accounts.
### Account
Accounts have an intrinsic balance and transaction count maintained as part of the Ethereum state. They also have some (possibly empty) EVM Code and a (possibly empty) Storage State associated with them. Though homogenous, it makes sense to distinguish between two practical types of account: those with empty associated EVM Code (thus the account balance is controlled, if at all, by some external entity) and those with non-empty associated EVM Code (thus the account represents an Autonomous Object). Each Account has a single Address that identifies it.
### Transaction
A piece of data, signed by an External Actor. It represents either a Message or a new Autonomous Object. Transactions are recorded into each block of the blockchain.
### Autonomous Object
A notional object existent only within the hypothetical state of Ethereum. Has an intrinsic address and thus an associated account; the account will have non-empty associated EVM Code. Incorporated only as the Storage State of that account.
### Storage State
The information particular to a given Account that is maintained between the times that the Account’s associated EVM Code runs.
### Message
Data (as a set of bytes) and Value (specified as Ether) that is passed between two Accounts, either through the deterministic operation of an Autonomous Object or the cryptographically secure signature of the Transaction.
### Message Call
The act of passing a message from one Account to another. If the destination account is associated with non-empty EVM Code, then the VM will be started with the state of said Object and the Message acted upon. If the message sender is an Autonomous Object, then the Call passes any data returned from the VM operation.
### Gas
The fundamental network cost unit. Paid for exclusively by Ether (as of PoC-4), which is converted freely to and from Gas as required. Gas does not exist outside of the internal Ethereum computation engine; its price is set by the Transaction and miners are free to ignore Transactions whose Gas price is too low.
### Contract
Informal term used to mean both a piece of EVM Code that may be associated with an Account or an Autonomous Object.
### Object
Synonym for Autonomous Object.
### ETHEREUM
A SECURE DECENTRALISED GENERALISED TRANSACTION LEDGER EIP-150 REVISION 16
### App
An end-user-visible application hosted in the Ethereum Browser.
### Ethereum Browser:
(aka Ethereum Reference Client) A cross-platform GUI of an interface similar to a simplified browser (a la Chrome) that is able to host sandboxed applications whose backend is purely on the Ethereum protocol.
### Ethereum Virtual Machine
(aka EVM) The virtual machine that forms the key part of the execution model for an Account’s associated EVM Code.
### Ethereum Runtime Environment
(aka ERE) The environment which is provided to an Autonomous Object executing in the EVM. Includes the EVM but also the structure of the world state on which the EVM relies for certain I/O instructions including CALL &amp; CREATE.
### EVM Code
The bytecode that the EVM can natively execute. Used to formally specify the meaning and ramifications of a message to an Account.
### EVM Assembly
The human-readable form of EVM-code.
### LLL
The Lisp-like Low-level Language, a human-writable language used for authoring simple contracts and general low-level language toolkit for trans-compiling to.

