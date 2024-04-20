# Delegatecall Attack Demo

This repository contains code demonstrating the delegatecall attack in Ethereum smart contracts. The attack exploits the `.delegatecall()` method in Solidity, allowing an attacker to modify the state of a target contract by manipulating the execution context.

## Overview

The repository consists of three Solidity contracts:

1. **Good.sol**: This contract contains a vulnerability that allows the owner to be changed through a delegatecall attack.
2. **Helper.sol**: A helper contract that is used to facilitate the delegatecall attack.
3. **Attack.sol**: The contract used to execute the delegatecall attack.

## Setup

To run the demo:

1. Clone this repository to your local machine.
2. Ensure you have Node.js and npm installed.
3. Install the required dependencies using `npm install`.
4. Deploy the contracts using a development blockchain environment like Hardhat or Ganache.
5. Execute the attack script to exploit the vulnerability.

## How It Works

The attack exploits the delegatecall method to modify the state of the target contract, Good.sol, by manipulating the execution context. Here's a brief overview of the attack process:

1. **Deploy Contracts**: Deploy the Good, Helper, and Attack contracts.
2. **Execute Attack**: Call the `attack()` function in the Attack contract, triggering the exploit.
3. **Result**: The owner of the Good contract is changed to the attacker's address, demonstrating a successful delegatecall attack.

## Testing

The repository includes automated tests to verify the effectiveness of the attack. These tests ensure that the owner of the Good contract is indeed changed after executing the attack.

## Prevention

To prevent delegatecall attacks, it's essential to use stateless library contracts for delegatecall invocations. This ensures that the called contract cannot modify the state of the calling contract.

---

This repository serves as an educational resource to understand the delegatecall attack and highlights the importance of secure contract development practices in Ethereum.
