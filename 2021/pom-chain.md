# Small proofs for invalid blocks

### Supervisor: Leander Jehl

### Prerequisits
- Blockchain technology (DAT650)

### Project
In an open blockchain system, we distinguish between full nodes and light nodes.
Full nodes maintain the complete blockchain state and apply and verify all transactions in new blocks.
Light nodes only maintain a subset of the blockchains state and typically only verify block headers.

The problem arrising is that a light node may accept a block, even if this block contains invalid transactions.
The idea for this project is to design a novel data structure for blocks, that allows to create proofs for blocks containing invalid transactions.
Using this proof, a full node can prove to a light node that a block contains an invalid transaction.

The challenge is to design the size of the proof to be independent of both the size of the system state and the 
number of transactions in a block.

The idea is to realize proofs first for the UTXO model first and invstigate an extension to accounts and smart contracts if time permits.
