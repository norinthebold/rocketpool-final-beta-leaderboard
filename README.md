# Rocketpool Final Beta Leaderboard

This project contains (unofficial) data for Rocketpool's third beta running on the Pyrmont test net.

[data/leaderboard.json](data/leaderboard.json) and [data/leaderboard.csv](data/leaderboard.csv) contain the latest leaderboards for rewards purposes which count only the top performing validator per node.

[data/all_validators.json](data/all_validators.json) and [data/all_validators.csv](data/all_validators.csv) contain the latest data for all validators participating in the beta.

Coming soon are the scripts and instructions which you can use to generate the data locally.

# Methodology

As per the beta [announcement](https://medium.com/rocket-pool/rocket-pool-3-0-beta-finale-fb35c4f8e003) and a subsequent [change](https://discord.com/channels/405159462932971535/405163979141545995/821638183296303114) to the start of the rewards tracking window, the leaderboard was constructed according to the following logic.

* Start of time period for tracking validator rewards: `2020-03-20 00:00:00 UTC` / Epoch 27338
* Validators are counted for inclusion if they created a minipool via this smart contract: `0xe2e718fb37464ba75d31c57509c4699a99a9fd53`

# Field descriptions

ETH amounts in data are denominated in Gwei. 1 ETH = 10e9 Gwei.

**rewards_rank**: Validator rank by **adjusted_balance** but only including one validator per node (**eth1_addr**)

**rank**: Validator rank by **adjusted_balance** including all validators

**index**: Validator index part of Eth2 API

**adjusted_balance**: Sorting criterion. Current balance minus balance at start of rewards window

**block_proposals**: Number of blocks proposed during rewards window

**beta_epochs_missed**: Number of epochs past rewards window start the validator activated

**balance**: Latest balance

**start_balance**: Balance at rewards window start

**eth1_addr**: Eth1 addres which created minipool. Used to track top performing validator per node for **rewards_rank**

**pub**: Validator public key.
