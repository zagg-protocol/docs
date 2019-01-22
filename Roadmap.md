
ZAGG Protocol is building a novel privacy-preserving Blockchain. Innovations in ZAGG Protocol bring privacy to public blockchain through a hybrid model of tracking assets and values on the blockchain with both Accounts and UTXOs.This solution adapts the privacy and robustness of the UTXO model’s construct to build a flexible and programmable account-based blockchain.

ZAGG Protocol is a fork of [stellar](https://github.com/stellar) adding a UTXO layer along with Zero-Knowledge Proofs to achieve privacy with verifiability. 

## Development Approach

ZAGG Protocol is starting the development from the stable build of Stellar. In the first phase, ZAGG wants to achieve UTXOs model on existing accounts based stellar. In the next phase, ZAGG Protocol team & collaborators to build Zero-Knowledge Proofs along with other primitives to achieve enterprise-grade privacy.

The full-fledged development plan is as follows:

### Protocol V0.0.1 | 
> Integration of bitcoin code base into the stellar fork to achieve dual accounts balance and UTXO balances.

**Assumptions:**
* Dual Ledgers with Dual accounts 
* Dual consensus 

**Description:**
After installation, User will be able to create a transaction via CLI. Use the data as input to the UTXO route. The communication is not in XDR and it's in either plain text or hex format. Stellar code makes a call to Bitcoin code base and registers the transaction. We will set up the bitcoin mining in a loop as a script. 


### Protocol V0.0.2 | 
> Both Account balance transactions and UTXO based transaction sets go through Stellar consensus protocol (SCP) and transaction set is applied on the ledger after the consensus.
 
**Assumptions:**
* Dual Ledgers with Dual accounts
* Single consensus
* Multiple Nodes

### Protocol V0.0.3 | 
> Add Account To UTXO and UTXO to Account conversions

### Protocol V0.0.4
> Replace Bitcoin with ZCash

### Protocol V0.0.5
> Integrating the ledgers

### Protocol V0.0.6
> Adding Private networks

### Protocol V0.0.7
> Adding Smart contracts







