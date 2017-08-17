# Distributed Ledger Technologies / Blockchain : Software Design Patterns

Written conform to the [principles and terminology](principles_terms.md) of Blockchain.

## Data Patterns

### Merkle Tree

#### Structure

![Merkle Tree](/images/merkle_tree.png "Merkle Tree")

#### Instance

![Merkle Tree](/images/merkle_tree_inst.png "Merkle Tree")

Where node[1.1].signature = hash(concatenate(node[1.1.1].toString(),node[1.1.2].toString())))
etc.

#### Applications
+ Git
+ Modern File Systems

### Merkle Trie / Blockchain

#### Structure

![Merkle Trie](/images/merkle_trie.png "Merkle Trie")

#### Instance

![Merkle Trie](/images/merkle_trie_inst.png "Merkle Trie")

Where root[i+1].signature = hash(concatenate(root[i].toString(),block[i].toString()))
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

#### Structure

![Observer](/images/observer.png "Observer")

#### Usage

![Observer](/images/observer_seq.png "Observer")

A more detailed UML and implementation: [ontrack-dapp](https://github.com/loredanacirstea/ontrack-dapp)

## Composite Patterns

### Twin Contracts

Twin smart contracts usually are born and die together. Also the transcations they initiate are born in synchronicity and atomically in mirror on their respective newtorks.

![Twin Contracts](/images/twin.png "Twin Contracts")

### Contract Factory

![Contract Factory](/images/factory.png "Contract Factory")

### Contract of Contracts

A contract that implements contract factory for any number of contracts.


## Thanks
Diagrams drawn using [Nomnoml](http://nomnoml.com/) and [JS Sequence Diagrams](https://bramp.github.io/js-sequence-diagrams/).

