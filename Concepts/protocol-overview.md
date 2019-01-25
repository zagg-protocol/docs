Overview
========
ZAGG Protocol proposes a hybrid model of Accounts and UTXOs for storage of assets and value. This solution leverages the privacy and robustness of the UTXOs construct into a flexible and powerful account-based blockchain. A user can convert a certain amount of balance into UTXOs and vice versa. UTXOs can be transacted in privacy subchains with spend receipts (similar to Nullifiers in ZCash or Key Images in Monero) maintained across public and private subchains to avoid double spending. We call these privacy-enabled UTXOs “SUTXOs” - Shielded UTXOs.

*Account Balance → UTXO/SUTXO → Account Balance Analogy*
*Bank account balance → Withdraw currency from the account in denominations → Spend the currency in the denominations→ Receiver deposits the currency into Bank account*

<Image>

Every user holds an account on the public blockchain which holds both account balances and also her unspent UTXOs. When the user wishes to exchange these assets in private, the user can initiate a transaction to convert a fixed amount of their assets into UTXOs with a value of their choice. For example, if a user, Alice, has assets worth 1000 in her wallet, she can withdraw 200 worth of assets and generate two UTXOs, each of value 100.

Conversion of value in Accounts to UTXOs will generate Zero-Knowledge Proof of the computation and output Shielded UTXOs ( SUTXOCommitments ) that will be sent to the shielded address of the user. Proof of Conversion (Zero Knowledge Proof) is attached to the withdrawal transaction on the public ledger without revealing the exact number or the value of the UTXOs generated. (The public chain only validates that x amount is converted into UTXOs, and that no new currency is created, nor any is destroyed). Commitments corresponding to the UTXOs are added to commitment Merkle tree. This mechanism is independent of the consensus used to put these UTXOs and commitments on to the public ledger.

A withdrawal transaction reduces the balance ( v) from t−addr and generates the S U T X OC ommitments (cm) . Commitment schemes being used will be WindowedPedersenCommitment and Homomor-phicPedersenCommit. 

Commitment Merkle tree and spend receipt sets are shared between all the Private subchains and the Public chain. Commitments and spend receipts are stored as hashes, to avoid disclosing any information about the commitments, as to which spend receipts relate to which commitments.
A user can then spend these UTXOs on the private subchains by creating spend receipts and new commitments. Every transaction on the private subchain updates commitments and spend receipts. Every transaction carries an attached ZK proof. Currently, the speed of transactions on the private chains is limited by the speed of consensus used for commitment and spend receipts Merkle trees.
This privacy approach is agnostic to the underlying ledger consensus mechanism. The privacy framework is portable across all accounts based blockchains with POS, POW, FBA, and other Layer 1 consensus. All the transactions related to shielded UTXOs like creation, spend and deposit to the accounts are validated by all the nodes on the public chain using the Zero- Knowledge Proofs and spend receipts.
For the first reference implementation of ZAGG Protocol, we have chosen to implement this privacy framework on the Stellar Consensus Protocol11. To obtain the public verifiability and avoid double spending across the network for the private transactions, the Zero Knowledge Proofs algorithms we will be using are ZK-SNARKS12. The following section describes the first implementation of this version of the protocol.



