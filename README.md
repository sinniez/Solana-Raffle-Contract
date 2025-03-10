# Raffle Smart contract on Solana

> :warning: If you intend to use this for production use the [v1 branch](https://github.com/sol-raffle-io/sol-raffle/tree/v1) which is matching the mainnet-beta deployment

sol-raffle is a decentralized raffle protocol on Solana, which creates the necessary technical foundation to the sol-raffle Luck Club. sol-raffle is the first of its kind open-source transparent system to allow raffling of any token, in any amount, any mint, unlimited number of participants or number of prizes.


## Program Deployments

| Program | Mainnet Beta | Status | Code |
| --------| ------------ | ------ | ---- |
| [sol-Raffle](/programs/sol-raffle/)     | `rafflesmQiLKjR5dmmdZC9RPX4EQUjqYFB3mWokRuDs` | [Anchor Verified](rafflesmQiLKjR5dmmdZC9RPX4EQUjqYFB3mWokRuDs) | [v1 branch]

## Components

- The sol-raffle program, to manage raffles
- The sol-raffle cli, to be able to interact with all the sol-raffle commands to create raffle and add prizes
- The community staking program, to allow user to stake and earn rewards on the sol-raffle community token, which is a free gift for early adopters and will give access to raffles

## Localnet usage

`scripts/start_dev.sh` sets up an entire environment with the program raffles and NFTs in order to functionaly test the app

Before running it make sure the programs are built with `anchor build`

When `start_dev.sh` is running the react app will show a set of test raffles with various prizes and raffle end times

## Notes

- metaplex-token-metadata-test-client needs to be executable chmod +x scripts/metaplex-token-metadata-test-client, build it from source for other OSes than linux with [metaplex-program-library](https://github.com/metaplex-foundation/metaplex-program-library) using `cargo build --release`
- install gdata on MacOS in order to be able to run start_dev.sh https://www.shell-tips.com/linux/how-to-format-date-and-time-in-linux-macos-and-bash/
- To use your own deployment, create a new program keypair, update declare_id! in [programs/sol-raffle/src/lib.rs](programs/sol-raffle/src/lib.rs) and use the (cli commands)[cli/README.md] with your program id! Run the react app with `REACT_APP_sol-raffle_PROGRAM_ID` set to your new program id.
