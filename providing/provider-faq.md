# Provider FAQ

### Contents

- [Setup](#setting-up-a-provider-node)
  - [Setting up a node](#setting-up-a-node)
- [Payment FaQ](#payment-faq)
  - [Where can I see my earnings](#where-can-i-see-my-earnings)
  - [Can I just put my normal ethereum address into my node](#can-i-just-put-my-normal-ethereum-address-into-my-node)
  - [How much can I earn](#how-much-can-i-earn)
  - [How are payments calculated](#how-are-payments-calculated)
- [General FaQ](#general-faq)
  - [What hardware is needed to get started](#what-hardware-is-needed-to-get-started)
  - [How can I set up multiple nodes](#how-can-i-set-up-multiple-nodes)
- [Credits](#credits)

## Setup

### Setting up a provider node
Refer to the [setup guide](https://github.com/figurestudios/community-golem-docs/blob/main/providing/provider-setup.md) for this.

## Payment FaQ

### Where can I see my earnings?
You can see your earnings by entering `golemsp status` when your node is online, or logging in on [zkWallet](https://wallet.zksync.io/).

### Can I just put my normal ethereum address into my node?
Yes and no. You need to make sure you can login to [zkWallet](https://wallet.zksync.io/) with your wallet, but if you can make sure that works then your normal address is fine.

### How much can I earn?
Earnings are generated on a supply & demand basis; there's no sure way to know how much you're going to earn. You can lower price-settings to receive more tasks, you can higher price-settings to get more per task. You can also lower the allocated resources per node to get more nodes out, and also higher the allocated resources to get more heavy tasks.

You can ask around in the [discord](https://chat.golem.network) to see what settings, hardware, and earnings other providers are currently having. You can also refer to the [stats page](https://stats.golem.network/) to see more objective and diverse information regarding settings, hardware, and earnings.

### How are payments calculated?
There are three price variables currently available, and you can see in this chart how they work:
```css
--env-per-hour      Hourly cost for downloading, uploading, and finalizing a result. For a task it is multiplied by time(h).
--cpu-per-hour      Cost of renting 1 core for 1 hour. For a task it is multiplied by time(h) and the amount of allocated cores. It starts when the task is starting to get calculated.
--starting-fee      Base cost of starting a calculation.
```

##### Example
With the settings { --env-per-hour 0.1, --cpu-per-hour 0.1, starting-fee 0.1 } and the task details { 3 minutes total time, 2 minutes computation time } and node details { 4 cores } we can see how the total cost adds up like this:

`(3-2) / 60 * 0.1 + 2 / 60 * 4  * 0.1 + 0.1 = 0.0394433 GLM`

##### Formula
`(totalMinutes - computeMinutes) / 60 * env-per-hour + computeMinutes / 60 * cpu-per-hour * cores + starting-fee = cost`

## General FaQ
### What hardware is needed to get started?
There are no hardware limitations set by Golem, so aslong as you have a processor, a disk of any kind, and also an internet connection you should be good to go!

The only thing is that some requestors might want better hardware than you're providing, but to start your own node you don't need anything fancy at all.

### How can I set up multiple nodes?
On Linux you can setup more nodes by using something like the [scaleable golem provider](https://github.com/cryptobench/scaleable-golem-provider).

On Windows, you can do the same in your VM or simply create more VM instances.

##### Can they be named the same?
Yes. Just make sure that the yagna id's differentiate by running this command:

`yagna id create`

## Credits
Written by figurestudios
Suggestion by @Matt80#1385
