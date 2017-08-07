
# Distributed Ledger Technologies / Blockchain : Software Design Patterns

First some terminology:

## Principles

### Atomicity

### Asynchrony

### Consensus

### Reliability

### Synchronicity

### Provenance


## Data Patterns

### Merkel Tree

![Merkel Tree](/images/merkel_tree.png "Merkel Tree")

Where node[1.1].hash = hash(concatenate(node[1.1.1].hash,node[1.1.2].hash))
etc.

#### Applications
+ Git
+ Modern File Systems

### Merkel Chain / Blockchain

![Merkel Chain](/images/merkel_chain.png "Merkel Chain")
```

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

One single instance of:
+ data
+ behavior
+ events

### Contract

### Oracle

### Observer/Judge

## Composite Patterns

### Twin Contract


