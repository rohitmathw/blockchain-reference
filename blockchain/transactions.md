## Transactions

Transactions are the building blocks of a blockchain system.
It generally moves some amount of cryptocurrency from one place to other. It changes the state of the network and it is collected into the blocks, as they are mined.A transaction contains the previous transactions output as the new transactions inputs. 
Once these transactions are compiled, they are distributed over the nodes, where they are verified,
and included in the block to be published. The transaction is now one block deep. With additional n blocks mined, the transaction becomes n blocks deep. The classic Bitcoin shows confirmed only after a transaction is 6 blocks deep. Then, the transaction becomes irreversible.

A typical transaction consists of:
*	Technical data (like version, no of inputs and outputs etc)
*	Input data(like previous tx hash, unlock script, script length)
*	Output data(like amount, lock script, script length)


 An example of a transaction is: 
```
input:
prev_tx: a6d4bf2dc19434acbf917b9f2dc19d6d1a0e9cea25fd6bc8a
index: 0
scriptsig: bcd8d894639a43090.....d1a0e91d6d1a019d6d–e9cea205bbd7b9f2dc19da19d6dcbfdea8841917b19d6d1a0

output:
value: 800000000
scriptpubkey: OP_DUP OP_HASH160 40917b9f2dc19d....dc19d6d1a0a786abd OP_EQUALVERIFY OP_CHECKSIG
```
Where
* **Input**: Reference to an output from the previous transactions.
* **Previous transaction**: Hash of previous transaction
* **Index**: Specific output (Here, #0)
* **ScriptSig**: It is the first half of the script. The script contains two components, a public key and a signature. The public key is used to verify the signature and also must match the hash given in the script of the output. The signature and key combined are used to validate the owner.This is the unlocking script.
* **Output**: Consists of instructions for sending bitcoins.
* **Value**: Number of Satoshis the output is worth (1 BTC= 10\^8 Sat)
* **ScriptPubKey**: Second half of script. This is the locking script.

In bitcoin, there are two types of transactions, **coinbase transactions** and **regular transactions**. Coinbase transactions are transactions in which new bitcoins are introduced to the system. They are included in every block as the first transaction and is meant for the miner as a reward for solving the ```PoW``` puzzle. On the other hand, regular transactions, are for transferring existing bitcoins among the users.
Every bitcoin transaction, spends null or more bitcoins. The difference between the amount spent and recieved is the **transaction** fee. This fee may be collected by miners who include the transaction in a block. For e.g., if Alice wants to send 2 Bitcoins to Bob and pay 0.1 Bitcoins in transaction fees. She would supply an input with 2.1 Bitcoin's and send 2 to Bob. The remaining amount, if not sent back to her or someone else, will be collected by the miner as transaction fees.


