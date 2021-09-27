# Troubleshooting

### Contents

- [Introduction](#introduction)
- [FAQ](#faq)
ugh ill make this tomorrow
- [Credits](#credits)
this too but its basically the content from nzemel and tiaxthegrand, with some reformatting and additions from me

### Introduction
These are community manufactured answers to frequent troubleshooting found. Feel free to use the [official FAQ](https://www.thorg.io/faq) as reference too.

### FAQ

##### Both of my GPU have lost hashrate on Thorg, what should I do?

A)

1. Restart your computer.
2. Update the drivers for your computer.
3. Ensure that your GPU is set to Maximum under `Settings > GPU > Mode`.

##### Why is my hashrate lower than what other people have for the same GPU?

A)

1) Some people overclock their GPUs.
2) Some people tinker with their cards through MSI afterburner.
3) LHR graphics cards bring performance down.
4) Using your PC at the same time will make the hashrate lower, as other programs will also be using your graphics card.

##### I can’t see my funds in my Metamask wallet, why is that?

A)

1. You're probably looking at your normal wallet. Your funds are stored on Polygon, and can be viewed at https://polygonscan.com/. These funds can be withdrawn to your wallet, but this requires a fee.
2. Right now, rewards are paid every second hour, meaning that you won't see your rewards realtime on Polygon.

##### Why does it say that my hardware isn't supported?

A)

1) Your graphics card needs to have at least 6 GB VRAM at this current stage.
2) Your anti-virus might be blocking "GolemUI.exe" or "EthDcrMiner64.exe".
i)If you do not have an aftermarket antivirus software installed you can unblock this by going to your Windows Security settings, and then clicking on Virus and Threat Protections.
![allow01](/thorg/img/allow-01.jpg)
3) You might not have a graphics card in your PC.

##### Where can I view my GLM balance?

A)

You can see your balance at https://polygonscan.com. If you need to withdraw, you can do so in the GolemUI client.

##### How do I switch my Metamask wallet over to the Polygon Network?

A)

Ensure that Metamask is installed in your browser. Then near the top there will be a button for the currently connected network. Click this and change it to Polygon.

![MetaMask01](/thorg/img/metamask-01.jpg) ![MetaMask02](/thorg/img/metamask-02.jpg)

Then, add the GLM by going to `Assets > Add Token` and adding the contract address from the [Polyscan Contract Page](https://polygonscan.com/token/0x0b220b82f3ea3b7f6d9a1d8ab58930c064a2b5bf).

![MetaMask03](/thorg/img/metamask-03.jpg) [MetaMask04](/thorg/img/metamask-04.jpg)

##### How do I import the wallet that Thorg created for me into Metamask?

A)

If you don't have MetaMask in your browser, [download the MetaMask](https://metamask.io/download.html) plugin. Click 'Get Started'. Press 'Import an existing wallet using the seed phrase'. Enter the seed phrase / Secret Recovery Phrase (the 12 words) given to you when you made your Thorg setup.

In case you already have MetaMask, then you have a few options:
1) Change your Thorg address to your MetaMask address.
2) You'd need to install MetaMask in a browser that doesn't already have it so that you can import the Secret Recovery Phrase you created in Thorg.
3) Extract the first generated private key of the Secret Recovery Phrase. There are lots of tools to do this, for example opening the Mnemonic Phrase in MyCrypto, and after opening your address and on the View & Send dashboard, click the 'Select' button and select Wallet Info. From there you can grab your private key.
This private key can be imported to MetaMask by going Import Account.

##### What's the minimum payout?

A)

The minimum payout is 0.00000000000000001 GLM.

##### My browser says that Thorg isn't safe to use, why is that?

A)

Some malware contains mining software that mines on a victims device, drawing energy and creating heat for someone else’s benefit. For this reason most antivirus softwares flag any mining software as malware, and leave it up to the end user to unblock it if they so choose.

##### What's the minimum VRAM requirement on GPUs?

A)

It's currently 6 GB.

##### How do I check how much VRAM my GPU has?

A)

Navigate to `Control Panel > Display > Screen Resolution > Advanced Setting > Display Adapter Properties`. You will be able to read your VRAM by reading the amount of dedicated video memory in there. A little less than 6 GB or more usually works.

##### Why does my benchmark stop in seconds after clicking 'Run Benchmark'?

A)

1) Restart your computer.
2) If using a 580 and restarting doesn't work, try reinstalling your drivers after deleting them first.

##### How do I overclock my GPU?

A)

If you have MSI Afterburner, use [these settings](https://www.nicehash.com/blog/post/nvidia-and-amd-graphics-card-oc-settings-for-mining).

##### Will XXX token mining or XXX algorithm or XXX pool be supported in the future?

A)

Potentially. Right now they are trying to implement the Golem Provider Client in the software and bringing the VRAM requirement down, but seeing how Thorg's main mission is reliable rewards, it's definitely possible.

##### What algorithm are we mining with?

A)

EThash.

##### How can I get it working on Mac or Linux?

A)

Unfortunately there are no plans to support either of these as of now.

##### How does the ETH get converted into GLM?

Thorg is a provider application allowing Windows users to compute tasks, creating what's referred to as “shares” which are collected and used to mine Ethereum. For the computation of creating these shares, the Thorg user earns GLM which is the token used for selling and buying computation on the Golem Network.

##### Can I see my stats online, similar to https://stats.golem.network?

A)

Not at the moment, but there is a private PoC built already.
