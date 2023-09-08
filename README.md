# Blockchain money transfer mechanism

The primary goal is to implement a transaction mechanism and understand the way money is transferred within the blockchain. Since the blockchain mechanism is designed in a way that is dramatically different from traditional bank operations on accounts, a notion of transaction input and subsequent transaction output should be understood in order to get an idea of how a value can be sent from one blockchain wallet to another.

## A concept of distributed ledger is used instead of an account. 
Each block in the blockchain has a record of transactions. That is the only mechanism to check where money came from. It should be known to calculate blockchain wallet balance. Each wallet has it's own database to keep record of transactions where the recipient is the wallet itself. This database called UTXOs or unspent transaction output. This is what this wallet can spend.

## Transaction input. 
This term is used to describe a person who initiated a transfer of funds. Sender creates an input, which is a value that would be transfered to the recipient. Under one condition. Only if the sender has enough funds. 

## Calculate wallet's balance. 
To get a balance of the wallet, we need to look into every block in the blockchain(except the genesis block) and check whether this wallet is mentioned as a recipient. That's it. In order to send money to someone, this wallet should receive it firts.

## Transaction output. 
This is the final step in 2 way step of making a transaction between wallets. A tricky part is that sender sends back to himself a change. Why it needs to be done? Because sender takes as much UTXOs as needed to cover a transaction, sometimes even more. If sender has one record in UTXOs with a value of 100. Only 20 should be send to the recipient. The sender takes his 100, removes it from his UTXOs , send it to the recipient. Then the sender should get the change. This would be another transaction where sender sends money to himself. Later under UTXOs, sender will see a transaction send to himself with the value of 80.



