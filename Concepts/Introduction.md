Introduction
============
A public blockchain an open, distributed ledger that can record transactions between two parties eciently and in a verifiable and permanent w a y 1. The block transactions are secured through a cryptographic hash of previous blocks, thereby, achieving censorship resistance, immutability, and public enforceability.
The ability to maintain an immutable record of transactions removes the need for trusted intermediary, thereby, decreasing the transaction costs in mediation between the parties involved.
Most public blockchains provide transparency2, immutability3 and a distributed ledger4 of assets and transactions, but they make a compromise on privacy. Most enterprises require privacy from public parties to execute viable business models and be compliant with regula-tions. So, it’s necessary for the adoption of blockchain in real-world use cases to support privacy within the context of an immutable public ledger.
Enterprises are adopting technologies for transaction privacy by setting up permissioned networks. The system relies on the internal participants to verify transactions and the trust
is centralized to few trusted nodes on the network. Though private blockchains are more ecient in terms of scalability and compliance with regulatory requirements, they rely on
the private network for the integrity of the blockchain, so the ledger is more vulnerable to manipulation considering the centralized governance of the network. Because current private blockchains are permissioned, there exist significant b arriers t o e ntry a nd g overnance issues, as well as a clear lack of decentralization.

ZAGG Protocol’s implementation of enterprise-grade privacy on public blockchain is designed to drive blockchain to mainstream enterprise-oriented payment and transaction use cases

User Balances: Accounts vs UTXOs
================================
The Account model is a typical accounts/currency ledger which is easy to develop, maintain, scale and audit. Management doesn’t get complex over time, unlike UTXO based systems. These are some of the reasons why many public blockchains like Ethereum and Stellar support smart contracts using an account based asset/value management on the ledger. An account- based public chain, however, is more prone to information leakage while executing contracts. There is the possibility of revealing source account details like balances.
Traditional blockchains like Bitcoin and new privacy centered blockchains like ZCash and Monero5, support stateless UTXO assets on the ledger. The UTXO model provides us with a trail of transactions which can be leveraged to mask the transaction trail by hiding the source or destination or both addresses of a specificUTXO,andby usingspecialtechniqueslike mixers. Privacy chains like ZCash use Zero-Knowledge Proofs to anonymize the transactions and verify the validity of a non-traceable UTXO spent publicly. This allows for transaction privacy on a decentralized network.6

Dealing with UTXO bloat is also a challenge which involves rebuilding or reindexing UTXOs frequently, in order to achieve low latency querying on UTXOs. Also, the storage requirements arise w.r.t handling data of UTXOs. All the used set of UTXOs and nullifiers cannot be removed from the system since they belong to the transaction flow of the system, thereby, making it a never-ending data store.

The UTXO storage has to be immutable to be a part of the blockchain as a different ledger. ZCash uses nullifierstotrackthestatusofUTXOsspent/unspentanditisessentialthat UTXOs’ nullifierindexupdatesshouldbeefficientandq uick.Inordertoachievesuch efficiency, we need to split and manage indices into spendable UTXO and spent UTXO.

Privacy Methods
===============
One of the ways public chains are dealing with privacy is through side chains7. But in these cases, the arbitration and consensus are limited to the private chain participants only. The public chain is only used for notarization of the transactions off-chain. Improper implemen- tation can lead to a double spend due to transactions taking place on a side chain then moving to the main chain, which might cause the side chain to gain or lose tokens w.r.t its main chain account, especially if multiple side chains are active. Token bonding has to be implemented between the side chain and main chain to prevent double spending. It is important that appropriate smart contracts are needed to achieve stake based ownership on these bonded tokens. New side chain infrastructure and token bonding are resource intensive to implement.
Zero Knowledge Proofs (ZKP) are a set of powerful tools for public chain nodes to participate in the consensus of private transactions without knowing the contents of the transaction. Proof generation of the ZKP for transactions is a time-consuming process, and involvement of public participants in the consensus will add limited but additional latency to the private transactions.
The current implementation of ZKPs using ZK-SNARKS has a prerequisite of a trusted setup at the genesis of the network launch. The participants of this setup have to make sure their private keys used in the generation of setup parameters are destroyed. 
NOTE: ZKPs uses homomorphic encryption internally. One of the many challenges that homomorphic encryption poses is that the data size of the encrypted data as compared to the original data is many times bigger. So it is a prerequisite for ZAGG nodes to handle higher storage requirements.

Smart Contracts on Public and Private chains
============================================
A smart contract is a computer protocol intended to digitally facilitate, verify, or enforce the negotiation or performance of a contract. Smart contracts allow the performance of credible transactions without third parties8.
On Public Chain
Public smart contracts on a public blockchain operate by altering the state of the Accounts as directed by the smart contracts and validated by the nodes (e.g. Ethereum’s implementation9).
On Private (permissioned) Chains
Enforcing of Public smart contracts are carried by redundantly executing the contract on all nodes, where the data required is available to all the nodes. Defining a p rivate smart contract system needs a detailed understanding of the privacy model itself that one intends to support.

Challenges In Smart Contract Engine Development:
1) Achieving DoS attack resistance for network
Having a Turing complete smart contract has a major drawback with a possibility of smart contracts which can hog the network resulting denial of service, or having the need for a cost function to compensate the network participants for computing resources necessary to run the contracts.
2) Insecure smart contract design will lead to loss of revenue to the participating parties
Since the developer community is not mature enough to write secure, efficient Turing- complete smart contracts, execution of badly designed smart contracts might cause loss of funds to the participants. Though technical solutions to this problem are limited, a mechanism has to be achieved where standard security tests are automated in a controlled environment to gauge the quality of a smart contract.
3) Smart contract implementation on private chains
4) Evaluating & leveraging an existing VM and interpreter
A right choice has to be made here w.r.t the current security issues we import on selecting a VM to achieve the smart contract functionality and execution.

5) State and storage management required for smart contract
The blockchain should inherently support storage (and the costs involved in its management) in order to store the state of a smart contract so that the different states of the smart contract are saved at different stages.



