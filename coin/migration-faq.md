# Migration FAQ

### Contents

- [General FaQ](#faq)
  - [How do I migrate?](#how-do-i-migrate)
  - [What gas should I set?](#what-gas-should-i-set)
  - [I sent GLM/GNT to an exchange which only supports the other token, what can I do?](#i-sent-glmgnt-to-an-exchange-which-only-supports-the-only-token-what-can-i-do)
  - [Gas is so expensive! What can I do?](#gas-is-so-expensive-what-can-i-do)
- [Ledger FaQ](#ledger-faq)
  - [I'm getting errors whilst migrating from my Ledger device, what can I do?](#im-getting-errors-whilst-migrating-from-my-ledger-device-what-can-i-do)
- [MetaMask FaQ]()
  - [How do I migrate with an Ethereum-address using MetaMask?](#how-do-i-migrate-with-an-ethereum-address-using-metamask)
  - [My GLM is not visible on MetaMask, how can I add it?](#my-glm-is-not-visible-on-metamask-how-can-i-add-it)
- [MyCrypto FaQ](#mycrypto-faq)
  - [How do I migrate through MyCrypto?](#how-do-i-migrate-through-mycrypto)
- [MyEtherWallet FaQ](#myetherwallet-faq)
  - [How do I migrate through MyEtherWallet?](#how-do-i-migrate-through-myetherwallet)

### General FaQ
##### How do I migrate?
> Try reading the migration guides for [MetaMask](#how-do-i-migrate-with-an-ethereum-address-using-metamask), [MyCrypto](#how-do-i-migrate-through-mycrypto), or [MyEtherWallet](#how-do-i-migrate-through-myetherwallet) to begin with. If you come across errors or need help, read the [FaQ](#contents) first and then if that doesn't work, ask for help in the [discord](https://chat.golem.network).
##### What gas should I set?
> 120k gas limit or 80 GWEI should be fine. Keep in mind that setting the gas limit higher doesn't hurt your transaction's cost - but setting it lower can make it risk getting failed.
##### I sent GLM/GNT to an exchange which only supports the other token, what can I do?
> The exchanges are the ones in control over those tokens. Locate their support & contact them for help.
##### Gas is so expensive! What can I do?
> Gas has historically showed to be cheaper on weekends, but even that can be expensive. There's no time-limit on migrations, so you could wait for a few of [these](https://www.reddit.com/r/ethereum/comments/liiiwh/eth_has_an_advantage_over_btc_as_a_store_of_value/gn46iui?utm_source=share&utm_medium=web2x&context=3) points to come to the Ethereum-chain for cheaper fees.

### Ledger FaQ
##### I'm getting errors whilst migrating from my Ledger device, what can I do?
> The most common error is that the `contract data` field in the settings is set to disabled, try enabling that.

### MetaMask FaQ
##### How do I migrate with an Ethereum-address using MetaMask?
> You can follow [this](https://www.youtube.com/watch?v=DYX9Xn2HyWw) for a video walk-through.
##### My GLM is not visible on MetaMask, how can I add it?
> Use [this](https://bit.ly/AddGLMmetamask) quicklink or add the token address manually: `0x7dd9c5cba05e151c895fde1cf355c9a1d5da6429`.

### MyCrypto FaQ
##### How do I migrate through MyCrypto?
> The [MyCrypto Migration Tool for Golem](https://app.mycrypto.com/migrate/golem) has on-screen instructions you could follow. You could also follow these instructions:
```
1. Look for the GNT migration notification or find the "Your Action Items" sections on the left to begin.
2. In the "Migrate your GNT to GLM" section, click on Migrate.
3. Select the amount of old GNT that you wish to migrate to GLM and click Migrate Golem Tokens.
4. See the details of your transaction and click Confirm and Send.
```

### MyEtherWallet FaQ
##### How do I migrate through MyEtherWallet?
> Follow these instructions to migrate your GNT tokens:
```
1. Go to https://www.myetherwallet.com/. After connecting your wallet, on the main landing page "Dashboard" you will see "Golem Migrator - Migrate your old golem tokens today" in the DApps section.
2. Select how much GNT you wish to migrate to GLM (remember that migration is one-way, once you've migrated the GNT is burned).
3. Confirm the transaction and make sure you set an appropriate gas price (usually the default provided is suitable but you can also check ethgasstation).
```
