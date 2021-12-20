# Abracadabra

## Bounty Page

{% embed url="https://www.notion.so/Abracadabra-Bounties-cd84292745254216a5e0f00f1323d65f" %}

## How to approach

```
Credits - Pinehearst#1947
How I would usually approach these bounties is:

1. Homework:
Read up a bit on the protocol docs: https://docs.abracadabra.money/ to get a sense of what the protocol is about, tokenomics and so on 

2. Finding Smart contracts: 
Find smart contracts related to the bounty question of interest. Usually when you are at the documentations page, you can find the relevant smart contracts: https://docs.abracadabra.money/our-ecosystem/our-contracts

3. Etherscan Surfing: 
Head to Etherscan https://etherscan.io/ to track some of these contracts, in this case it would be the Degenbox UST 0xbc36fde44a7fd8f545d459452ef9539d7a14dd63
https://etherscan.io/address/0xbc36fde44a7fd8f545d459452ef9539d7a14dd63 
From there, make sense of what kind of transactions are occurring on the contract. At times I will trace back to the user who initiated the contract to see things like, where he got his funds (UST), when did he do the deposits and so on 

4. Sense-making: 
If I don't understand a thing (usually for new projects) > find youtube videos of people explaining or using the protocol and how they interact with the platform, do they have to approve the contract? do they have to deposit UST? 

5. Finding a sample transaction of interest:
This will be a sample transaction where I will use to explore and structure my query, after I have identified the tx_id that is relevant to my analysis. The transaction has to be reasonable old (probably >1day ago), as Flipside takes a while to update the data tables.

6. Using Velocity to explore the transaction: 
 SELECT * FROM ethereum.udm_events  WHERE tx_id = '.....' 

From there I will figure out what filters and queries I need to extract out the data I need from my analysis

```

## Contract Addresses

### ETH - Spell

{% embed url="https://etherscan.io/token/0x090185f2135308bad17527004364ebcc2d37e5f6" %}
