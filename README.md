# BinaryMerkleTree_MelloMM
Python3 implementation of a *binary* Merkle trees provided by MelloMM.

MelloMM set of repos targets the technicals of blockchain, especially Ethereum-based blockchains.

## Content
This repo shows a demo of a *binary* Merkle tree. These are simple, but they are not the trees used in Ethereum, which uses indeed [Merkle Patricia trees](https://blog.ethereum.org/2015/11/15/merkling-in-ethereum/). This repo shows a demo of binary trees, whereas the MelloMM's demo of Patricia trees can be found [here (ToDo)]().

## Short theory
Merkle trees are wodely used to verify any kind of data which are transferred or archived through the use of cryptographic hashes. Briefly, "verifying" means assuring that a certain data block has not been tampered/it really comes from who claims to be the sender of it. Variants of Merkle trees are used in peer-to-peer networks such as Ethereum or Bitcoin.

Merkle tree composition:
* Leaves contains the hash of actual data (e.g., transactions in Ethereum).
* Intermediate nodes (named _inodes_) contains the cryptographic hash of its two children.
* A single root node, the top of the tree, that has the same property of an inode.

The point is being able to demonstrate that a child node is really part of a certain Merkle tree. This is computational expensive because you should compute the hash of all its ancestors, which in `O` notation is `O(L)`, where `L` is the number of leaves in the tree.

Let's translate this data structure in cryptocurrency, like Ethereum (actually, there are slight differences among each of them. This short explanation is _generic enough_ to understand the concept). We assume you already know what a block is and the meaning of each component (hash, nonce, and so on). When we talk about the hash of a block, we talk about the hash of the block header. A block header does not contain data actually (i.e., the ethereum transactions), but only timestamp, nonce, hash of the previous block in the blockchain and the hash of the root of the Merkle tree. 

A Merkle tree stores all the transactions of a block. 

ToDo:
* Back propagation
* Piecemeal
* Maybe attacks


## Useful links
1. [Ethereum whitepaper](https://ethereum.org/en/whitepaper/)
2. [Merkling in ethereum](https://blog.ethereum.org/2015/11/15/merkling-in-ethereum/)
3. [Blockchain demo](https://andersbrownworth.com/blockchain/blockchain)
4. [Solidity bootcamp](https://www.youtube.com/watch?v=M576WGiDBdQ)
