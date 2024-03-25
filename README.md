# Solana NFT using Anchor 

An update to the latest version of Anchor, Anchor-SPL(which now includes MPL Token Metadata) and Solana.  It is based on the [Mint Your First NFT](https://calyptus.co/lessons/mint-your-first-nft/) lesson, this project shows how to mint your first NFT on the Solana blockchain using [Anchor](https://www.anchor-lang.com/) and [Metaplex](https://www.anchor-lang.com/).

## Table of Contents
- [Solana NFT using Anchor](#solana-nft-using-anchor)
    - [Table of Contents](#table-of-contents)
    - [Getting Started](#getting-started)
    - [License](#license)

## Getting Started

To use this fork, you need to have [yarn](https://yarnpkg.com/getting-started/install), [Anchor](https://www.anchor-lang.com/docs/installation) and the [Solana cli suite](https://solana.com/developers/guides/getstarted/setup-local-development) installed on your machine. 

It is highly recommended that you start this project from scratch, following along with the tutorial. 

To use the fork, follow the steps outlined below: 

1. Clone your forked repo.

```bash
git clone https://github.com/<YOUR-USERNAME>/solana-nft-anchor
```

2. Change directory into the root of your cloned repo and install missing node packages

```bash
yarn install
```

**NOTE:** You must use yarn to install the dependencies. If you use a different package manager, you will run into issues minting the NFT.

3. Build your anchor project.

```bash
anchor build
```

4. List the project deployment keys and copy the address to a clipboard

```bash
anchor keys list
```

5. Update your [`Anchor.toml`](Anchor.toml) file, by using the address generated in the previous step. 

```toml
[programs.devnet]
solana_nft_anchor = "<ADD YOUR ADDRESS HERE>"
```

6. Update your [`lib.rs`](programs/solana-nft-anchor/src//lib.rs) file by adding the the address generated in step 4 to the `declare_id!()` macro

```rust
    // snip
use mpl_token_metadata::{
    pda::{find_master_edition_account, find_metadata_account},
    state::DataV2,
};

declare_id!("<UPDATE HERE>");
#[program]
pub mod solana_nft_anchor {
    // snip
```

## License

All files within this repository are licensed under the MIT License unless explicitly stated otherwise.

Note: This is a work in progress.  There are still some existing issues.