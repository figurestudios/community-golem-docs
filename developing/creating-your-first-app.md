# Creating your First Application on Golem

### Contents

- [Introduction](#introduction)
  - [The structure of the Golem Network](#the-structure-of-the-golem-network)
  - [Why would I develop anything on Golem?](#why-would-i-develop-anything-on-golem)
  - [What we will be building](#what-we-will-be-building)

### Introduction
So... You've found Golem, found the technology interesting enough and now you want to create your own application. You'll be learning how to make a simple application, how to run it, and understand the core-structure of Golem.

This guide will make use of [docker](https://www.docker.com/), [javascript](https://www.javascript.com/), and [python](https://www.python.org/), and will break it all down simply enough to make anyone be able to understand it. Learning how these work is not required for this guide but it's recommended if you want to advance after it.

##### The structure of the Golem Network
The structure of the network is one of the fundamentals you'll need to know to start using Golem. 

There are three types of roles within this network:
```
1. Developers - create applications for personal use or others to use.
2. Requestors - use pre-existing applications to complete tasks needing compute.
3. Providers  - computes the tasks that are given by requestors.
```
You will be fulfilling the first two roles by developing your own application, and requesting it to be ran on a provider's node.

##### Why would I develop anything on Golem?

Golem has a few ups and downs in its current state, with the ups being:
```
1. It allows for distribution of tasks, so something that would normally take 1 server an hour, could be spread out into smaller tasks over hundreds of servers to save tons of time.
2. With most providers setting their prices at $0.1 GLM/CPU hour, which translated to USD costs $0.0371 (at the time of writing this) to rent a CPU-core for one whole hour. This makes it relatively cheap to access tons of hardware.
3. You can get rewarded in both hackathons & by community grants - requesting a lot can make you count as a "Super User", making you eligible to win 2,500 GLM by-monthly.
4. As it's decentralized, there are a lot of access points and a lot of failures are needed for the entire network to go down.
5. Golem is cool 😎
```
and the downs being:
```
1. Communication is limited and only between the requestor & the provider. There is no internet access yet.
2. It can take some time to find providers and you don't know how slow their system is - even if they have many cores.
3. There's no support for GPU.
4. There's no support for always-running applications. The maximum time is currently capped at 3 hours.
```
Think of it like this - you can render a 3d scene that would normally take 100 hours(with CPU) in only 1 hour if you spread it across 100 nodes, but the downside is that you can't access GPUs yet, so it may still be effective to render yourself if you have access to one.

For now, requestors pay for tasks, and providers earn by renting out their computing power. In the future it'll be possible for developers to generate income from their applications by letting requestors pay to use it, but the ideas aren't implemented and are subject to change. For now, you will only be able to keep your tasks private, or trust the requestor not to resell your beloved files.

##### What we will be building
As this is your first application on Golem, it shouldn't be too complicated to get it all set up. The first example will showcase how to generate lowercase letters from uppercase ones. This is a very simple example, so hopefully you won't get lost just yet. If you do get lost, please join the [discord](https://chat.golem.network) for troubleshooting - we are happy to help :)
