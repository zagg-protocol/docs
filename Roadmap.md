
ZAGG Protocol is building a novel privacy-preserving Blockchain. Innovations in ZAGG Protocol bring privacy to public blockchain through a hybrid model of tracking assets and values on the blockchain with both Accounts and UTXOs.This solution adapts the privacy and robustness of the UTXO model’s construct to build a flexible and programmable account-based blockchain.

ZAGG Protocol is a fork of [stellar](https://github.com/stellar) adding a UTXO layer along with Zero-Knowledge Proofs to achieve privacy with verifiability. 

## Development Approach

ZAGG Protocol is starting the development from the stable build of Stellar. In the first phase, ZAGG intends to add UTXOs model to existing accounts based stellar. In the next phase, ZAGG Protocol team to build Zero-Knowledge Proofs along with other primitives to achieve transaction privacy.

The full-fledged development plan is as follows:

### Protocol V0.0.1 | 
> Integration of bitcoin code base into the stellar fork to achieve dual accounts balance and UTXO balances.

**Assumptions:**
* Dual Ledgers with Dual accounts 
* Dual consensus 

**Description:**
After this step, User will be able to create a transaction via CLI. Use the data as input to the UTXO route. The communication is not in XDR and it's in either plain text or hex format. Stellar code invokes a call to Bitcoin code base and registers the transaction. The bitcoin mining in a loop as a script. This step is the first step to create one merged running instance of both the protocols as foundation for next level innovations.


### Protocol V0.0.2 | 
> Both Account balance transactions and UTXO based transaction will go through Stellar consensus protocol (SCP) and transaction set is applied on the ledger after the consensus. This will add a new transaction to Stellar and the system will support both accounts state changes and UTXOs on the global ledger(s). There will be only one (Stellar) Consensus mechanism on the network.
 
**Assumptions:**
* Dual Ledgers with Dual accounts
* Single consensus
* Multiple Nodes

### Protocol V0.0.3 | 
> Add Account To UTXO and UTXO to Account conversions
This step will allow the user to move assets (multiple types) from her account into UTXOs (multiple types) and back and execute transfer of those assets/UTXOs to other users on the network over SCP. This step will also ensure no double spending and assets/resource consistency across both the types for any given user and on the network.

### Protocol V0.0.4
> Replace Bitcoin with ZCash
The above three steps of changes will then be applied to ZCash Sapling code base and it will be merged with Stellar code base. Subsequent code changes will be on the Zero Knowledge Proofs, Commitments and Nullifiers functionality so that the system will be able to support shielded ZKP transactions on Stellar consensus.

### Protocol V0.0.5
> Integrating the ledgers
The accounts and shielded UTXOs transactions will be merged so that all the transactions will be recorded and retrieved from one global ledger.

### Protocol V0.0.6
> Adding Private networks

### Protocol V0.0.7
> Adding Smart contracts







