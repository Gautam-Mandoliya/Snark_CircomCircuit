# zk-Snark Circom Circuit

## Description
Designed a new zkSNARK circuit that implements some logical operations. I have implemented the circuit and deployed a verifier on-chain to verify proofs generated from this circuit

## Quick Start

Compile the zkcircuit/circuit.circom and verify it against a smart contract verifier.

### Installation

Install npm : `npm i`
   #### ` I recommend doing next step in WSL(window subsystem for linux) or in gitpod so that you won't encounter error related to circom `
   
### Compile

`npx hardhat circom` 

This will generate the `out` file with circuit intermediaries and geneate the `ZkcircuitVerifier.sol` contract

### Prove and Deploy

`npx hardhat run scripts/deploy.ts`

This script does 4 things  
1. Deploys the MultiplierVerifier.sol contract
2. Generates a proof from circuit intermediaries with `generateProof()`
3. Generates calldata with `generateCallData()`
4. Calls `verifyProof()` on the verifier contract with calldata

`With two commands you can compile a ZKP, generate a proof, deploy a verifier, and verify the proof 🎉`

**adding circuits**   
To add a new circuit, you can run the `newcircuit` hardhat task to autogenerate configuration and directories i.e  

```
npx hardhat newcircuit --name newcircuit
```
# Author
Gautam Mandoliya

# License
