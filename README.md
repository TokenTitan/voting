# Voting Contract

## Overview

The Voting contract is a simple Ethereum smart contract that allows for the management of candidates and voting in a decentralized manner. This contract includes functionalities to add candidates, vote for them, retrieve candidate information, and reset votes. 

## Features

- **Add Candidate:** The owner can add new candidates to the voting system.
- **Vote:** Users can vote for their preferred candidates.
- **Get All Candidates:** Get the complete list of all candidates.
- **Reset Votes:** The owner can reset the vote counts for all candidates.

## Changes

- candidateNames: Mapped candidate name by candidate Id
    - No need to store candidate ID in structu for all use. Candidate struct is used to get all candidated details only
    - voteCount param in Candidtae struct is moved to another mapping, called candidateVotes
- Create new mapping to store candidate vote count for particular session, candidateVotes.
- Create sessions for all new votings because resetting all candidate vote counts to zero is gas-intensive. Starting a new session will automatically initialize the vote count for all candidates to zero.

## Scripts

### Compile
```shell
npx hardhat compile
```

### Test
```shell
npx hardhat test
```

### Deploy
```shell
npx hardhat run --network localhost scripts/deploy.ts
```

### Start node
```shell
npx hardhat node
```
