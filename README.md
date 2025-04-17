ProfessionalToken - ERC-20 Token with Vesting
This repository contains a Solidity smart contract for an ERC-20 token named ProfessionalToken. It extends the standard ERC-20 functionality with features like vesting schedules, minting, burning, pausing, and reentrancy protection, leveraging OpenZeppelin’s battle-tested libraries.

Features
ERC-20 Compliance: Standard token functionality (transfer, approve, etc.).
Vesting Schedules: Tokens can be locked and released over time with customizable cliff and duration.
Minting: Owner can mint new tokens up to a maximum supply of 1 billion.
Burning: Users can burn their own tokens.
Pausable: Owner can pause/unpause token operations in emergencies.
Reentrancy Protection: Guards against reentrancy attacks during token releases.
Ownership: Restricted functions for the contract owner (e.g., vesting management, minting).
Prerequisites
To deploy and interact with this contract, you'll need:

Solidity ^0.8.29

OpenZeppelin Contracts (version compatible with Solidity ^0.8.26)
Ethereum Development Environment (e.g., Hardhat, Truffle, or Remix)
MetaMask or another Ethereum wallet
Testnet or Mainnet ETH for deployment and gas fees
Contract Details
Token Parameters
Name: Customizable (set during deployment)
Symbol: Customizable (set during deployment)
Max Supply: 1,000,000,000 tokens (1 billion)
Initial Supply: 100,000,000 tokens (100 million, minted to deployer)
Decimals: 18 (standard ERC-20)
Key Functions
createVestingSchedule(address beneficiary, uint256 startTime, uint256 cliffDuration, uint256 duration, uint256 amount): Sets up a vesting schedule (owner only).
releaseVestedTokens(address beneficiary): Releases vested tokens to the beneficiary.
revokeVestingSchedule(address beneficiary): Revokes a vesting schedule and returns unreleased tokens to owner.
mint(address to, uint256 amount): Mints new tokens (owner only).
burn(uint256 amount): Burns tokens from the caller’s balance.
pause() / unpause(): Pauses or resumes token operations (owner only).
Events
VestingScheduleCreated: Emitted when a vesting schedule is created.
VestingScheduleRevoked: Emitted when a vesting schedule is revoked.
TokensMinted: Emitted when tokens are minted.
TokensBurned: Emitted when tokens are burned.
