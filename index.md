![Lightning Logo](images/Lightning_Network.svg)

These are helpful notes I have compiled about the Bitcoin Lightning Network. This covers everything from basic info, which wallets support lightning, and even advanced information about running a lightning node.

Special thanks to everyone who has been contributing to Lightning for years and the community who has helped me find all of this info online and IRL.

[Introduction](#introduction)

[Basics of Lightning](#basics-of-lightning)

> [Terminology](#terminology)
>
> [Wallets](#wallets)

[Running a Lightning Node](#running-a-lightning-node)

> [System Requirements](#system-requirements)
>
> [Installation Options](#installation-options)
>
> [Tutorials](#tutorials)
>
> [Install using apt](#install-using-apt)
>
> [Blue Wallet / Umbrel Non-Custodial
> Walkthrough](#blue-wallet-umbrel-non-custodial-walkthrough)
>
> [Install btc / lnd and torrent the bootstrap from Jeff
> Garzik](#install-btc-lnd-and-torrent-the-bootstrap-from-jeff-garzik)
>
[Nodes](#nodes)
>
> [Node Ratings and Info](#node-ratings-and-info)
>
> * [Lightning Node Websites](#lightning-node-websites)
>
> *  [Lighting Terminal Ratings](#lighting-terminal-ratings)
>
> *  [Moneni Node Match](#moneni-node-match)
>
>  * [LN Node Insight](#ln-node-insight)
>
> [Node Management (Web)](#node-management-web)
>
> * [Lightning Terminal - by lightning
> labs](#lightning-terminal---by-lightning-labs)
>
> *  [Walkthrough of "Lightning
> Terminal"](#walkthrough-of-lightning-terminal)
>
> *  [Ride the Lightning - fantastic web
> ui](#ride-the-lightning---fantastic-web-ui)
>
> *  [Thunderhub - web ui with new features for
> rebalancing](#thunderhub---web-ui-with-new-features-for-rebalancing)
>
> [Node Management (CLI)](#node-management-cli)
>
> *  [Balance of Satoshis - Alex Bosworth's
> tools](#balance-of-satoshis---alex-bosworths-tools)
>
> *  [Suez - pretty printing and optimizing
> channels](#suez---pretty-printing-and-optimizing-channels)
>
[Channels](#channels)
>
> [Lightning Noderunner Groups](#lightning-noderunner-groups)
>
> *  [Rings of Fire](#rings-of-fire)
>
> *  [Plebnet](#plebnet)
>
> [Lightning Channel Creation
> Sites](#lightning-channel-creation-sites)
>
> *  [Lightning Network Plus](#lightning-network-plus)
>
> *  [Lightning Conductor](#lightning-conductor)
>
> *  [LNBIG nodes](#lnbig-nodes)
>
> [Pending channel - how to see](#pending-channel---how-to-see)
>
> [Setting Channel Fees](#setting-channel-fees)

[Technical Sites](#technical-sites)

> [Loop](#loop)

[Other Notes](#other-notes)

> [Channel Advice](#channel-advice)
>
> [Keysend and MPP](#keysend-and-mpp)

# Introduction

Lightning is a micropayment system for sending bitcoin cheaply and
quickly. Since bitcoin transactions are relatively slow and expensive.
Lightning enables people to send and receive small payments to and from
other people. Lightning is considered a scaling solution for bitcoin or
a "layer-2" solution. It uses the bitcoin network to track and execute
certain commands. Bitcoin can never leave the bitcoin chain, but
lightning nodes can transact between themselves and then settle their
balances on bitcoin at a later time.

# Basics of Lightning

First thing you should do is read a bit of the documents here and get
familiar with the terminology below. This will help you understand
everything else in this document.

[https://lightning.network/lightning-network-summary.pdf](https://lightning.network/lightning-network-summary.pdf)

[https://bitcoiner.guide/lightning/](https://bitcoiner.guide/lightning/)

## Terminology

-   **On-chain** - a transaction or balance on the bitcoin blockchain

-   **Node** - a server that runs an implementation of lightning which
    > can create channels to other nodes.

-   **Alias** - a public "display name" identifier for your node

-   **Peer** - a node that you are able or have connected to connect to
    > via a channel

-   **Channel** - a connection between 2 lightning nodes which can be
    > private or public. A channel is just a special bitcoin
    > transaction. it makes a 2-of-2 multisig that both parties have to
    > sign to do anything with on-chain

-   **Overall Capacity** - the amount of BTC that is locked into the
    > channel

-   **Remote Capacity (*inbound liquidity*)** - the amount of Lightning
    > BTC available to be sent TO your node on a channel

-   **Local Capacity (*outbound liquidity)*** - the amount of Lightning
    > BTC available to be sent FROM your node on a channel

-   **Rebalance** - the process of creating or restoring a balanced
    > state in the ratio of your remote and local capacity

-   **Tanuki Node** - a Lightning node with total local capacity of at
    > least 0.615 BTC.

-   **WUMBO channel** - channel of more than 16M sats and require 6
    > confirmations

-   **Keysend** - sending a payment to a lightning node id instead of an
    > invoice

-   **Invoice** - most lightning payments are sent to an invoice which
    > determines the amount and the node to send to

## Wallets

These wallets allow you to use the Lightning network for sending and
receiving payments - most also support regular bitcoin transactions.

1.  Muun - noncustodial wallet supports lightning and BTC in a single
    balance

2.  Breez - noncustodial wallet, runs a lightning node on your phone

3.  Zap - useful for controlling your node

4.  Wallet of satoshi

5.  Blue wallet

6.  Phoenix (android only) - noncustodial wallet, runs a lightning node
    on your phone

# Running a Lightning Node

## System Requirements

-   500+ GB Storage (2 drives recommended)

-   2GB RAM (16GB recommended)

-   \+ CPU cores help sync speed

-   Bandwidth requirements are minimal / latency and uptime are
    > important

## Installation Options

[https://mynodebtc.com/](https://mynodebtc.com/)

[https://getumbrel.com/](https://getumbrel.com/)

Install from apt like a miniboss

Compile from source like a boss using my
[gists](https://gist.github.com/bensig)

## Tutorials

### Install using apt

[https://stopanddecrypt.medium.com/a-complete-beginners-guide-to-installing-a-lightning-node-on-linux-2021-edition-ece227cfc35d#66eb](https://stopanddecrypt.medium.com/a-complete-beginners-guide-to-installing-a-lightning-node-on-linux-2021-edition-ece227cfc35d#66eb)

### Blue Wallet / Umbrel Non-Custodial Walkthrough

[https://www.youtube.com/watch?v=iVPNk2ZZ63w&t=1s](https://www.youtube.com/watch?v=iVPNk2ZZ63w&t=1s)

### Install btc / lnd and torrent the bootstrap from Jeff Garzik 

[https://www.reddit.com/r/Bitcoin/comments/2f9o9p/quick_guide_run_a\_full_node_with_btcd_an/](https://www.reddit.com/r/Bitcoin/comments/2f9o9p/quick_guide_run_a_full_node_with_btcd_an/)

## Nodes

### Node Ratings and Info

#### Lightning Node Websites

##### Lighting Terminal Ratings

> [https://terminal.lightning.engineering/](https://terminal.lightning.engineering/)

##### Moneni Node Match

> [https://moneni.com/nodematch](https://moneni.com/nodematch)

##### LN Node Insight

> [https://lnnodeinsight.com/](https://lnnodeinsight.com/)

### Node Management (Web)

#### **Lightning Terminal** - by lightning labs

[https://github.com/lightninglabs/lightning-terminal/blob/master/doc/config-lnd-remote.md](https://github.com/lightninglabs/lightning-terminal/blob/master/doc/config-lnd-remote.md)

##### Walkthrough of "Lightning Terminal"

> [https://github.com/lightninglabs/lightning-terminal/blob/master/doc/WALKTHROUGH.md](https://github.com/lightninglabs/lightning-terminal/blob/master/doc/WALKTHROUGH.md)

#### **Ride the Lightning** - fantastic web ui 

[https://github.com/Ride-The-Lightning/RTL#install](https://github.com/Ride-The-Lightning/RTL#install)

#### **Thunderhub** - web ui with new features for rebalancing

[https://github.com/apotdevin/thunderhub](https://github.com/apotdevin/thunderhub)

### Node Management (CLI)

#### **Balance of Satoshis** - Alex Bosworth's tools

[https://github.com/alexbosworth/balanceofsatoshis](https://github.com/alexbosworth/balanceofsatoshis)

#### **Suez** - pretty printing and optimizing channels 

[https://github.com/prusnak/suez](https://github.com/prusnak/suez)

## Channels

There are lots of great resources to find nodes to peer with and create
channels. 

Channels must be opened with a bitcoin transaction. 

Bitcoin transactions are priced in sats / virtual byte.

Channels cost 0.00000154 BTC if you price at the lowest price of 1 sats/virtual Byte (vB). 

Pending transactions on bitcoin are stored in the [mempool which you can view here on mempool.space](https://mempool.space/).

If the mempool is empty, then you can get transactions included for 1 sat / vB, but the larger the mempool becomes - the pricing to include a transaction becomes more expensive. The most expensive bitcoin transaction fees ([not paid by mistake](https://themerkle.com/3-largest-bitcoin-transaction-fees-ever-recorded/)) was on Dec 21, 2017 at 1400+ sats/vB according to [Johoe](https://jochen-hoenicke.de/queue/#BTC,all,fee).

You can see the current Bitcoin Fee Estimates here: https://bitcoiner.live/

### Lightning Noderunner Groups

#### Rings of Fire

> [https://t.me/theRingsOfFire](https://t.me/theRingsOfFire)

#### Plebnet

> [https://github.com/PLEBNET/wiki](https://github.com/PLEBNET/wiki)
>
> [https://t.me/plebnet](https://t.me/plebnet)

### Lightning Channel Creation Sites

#### Lightning Network Plus

> Great platform for creating channels of all sizes
>
> [https://lightningnetwork.plus/](https://lightningnetwork.plus/)

#### Lightning Conductor

> This service will open a channel channel back to you with 500k sats
> capacity
>
> [https://mainnet.lightningconductor.net/channels](https://mainnet.lightningconductor.net/channels)

#### LNBIG nodes

> Buy inbound liquidity from LNBIG to rebalance your channels
>
> [https://lnbig.com/](https://lnbig.com/#/)

#### Pending channel - how to see

> When LND, use these commands:

-   lncli pendingchannels

-   lookup channel_point in the result

-   paste the part before the colon (the hex stuph) into blockchain.info

-   check if there are confirmations / fee per byte

### Setting Channel Fees 

-outbound channels that get used frequently, you increase fees.

-outbound channels that get used infrequently, you decrease your fees

Look in your routing tab in RTL to determine channel usage.

-If you have a high local balance on a channel, you want to decrease
your fees in order to encourage routing through that channel

-if you have a higher remote balance, then you increase your fees to
discourage routing through that channel

-if you open to a big drainer channel like bitrefill or loop, you crank
your fees. Look at their other channels to determine competitive rates.

-setting fees will only get you so far. You'll most like need to
rebalance too if a channel gets used frequently. Some channels really
only move one-way regardless of how you set your fees so rebalance to
get more traffic. And make sure you're setting your fees in such a way
that you make more than what it costs to rebalance.

-it's good to set your fee rates in your lnd conf file, otherwise every
channel opened to you will be at the default. This is fine if you're
just starting out.

# Technical Sites

## Loop

[https://lightning.engineering/loop/](https://lightning.engineering/loop/)

# Other Notes

## Channel Advice

From :prem: ghinde:

I started off small and joined a number of 1M rings but found next to no traffic. I'm a member of a private group who are trying to create a super node for want of a better term and we started with 1M channels internally too but were doing alright in terms of traffic. I recently joined a 5M ring and found my traffic through my node exploded so now I am focused on being more selective with who I open channels to but making the channels larger. This change has fed into our super node setup too and we're taking advantage of the low fees to close our chaneels and reopen at 2M to see what difference that makes. Just my own personal philosophy based on my learnings so far. Could be right, could be wrong. Also I'm more interested in creating a more decentralised network so when looking for bigger nodes to connect with I'll start at position 100 on the top nodes lists to research from.


Advice from AZHodl:

Personally, I would open up 5-10 channels to the best professional nodes
from around the world and do another 5-10 rings. Keep your channels size
between 1-10M. Finally, purchase liquidity from LN BIG and rebalance
your channels like its your day job, close those channels when you empty
and open new channels to peers.

[https://azhodl.com/](https://azhodl.com/)

From Xenonfun:

Once you have multiple channels if someone routes payments - one side
will increase the other will decrease. the lightning network is a closed
system, so your node doesn\'t really lose/gain sats beyond the fees the
sender pays

you get paid fees for liquidity moving from your side to the remote side

yes, that was the fee to get it in the chain

well you now will be able to send micropayments for way way cheaper

the channels under 16Msats take 3 confirmations before they are open

and then if your path looks good a remote lnd server might pick your
node to route thru and you will be paid for that liquidity moving from
one side of the channel to another.

I must stress, make copies of your LND Seed, and make channel backup any
time you add/remove a channel

your net balance of the whole server will not change, but balance
between channels does

## Keysend and MPP

From Xenonfun:

and with 0.13 version they enabled AMP and MPP by default (splitting
payments across multiple channels) which will help payment success

it\'s in an earlier version but not default on. only thunderhub uses it,
RTL will not try doing MPP payments

AMP is MPP but for keysend payments

well your nodeID, can be consider an \"address\" in that with just that
someone should be able to keysend a payment to you

you can make a very long duration invoice as well

like this one
lnbc10n1psdzjhnpp59256waht5vw6qyfaqns6aau0hkl4haxs7qwjdaxr8uyrmhvpx4nsdqqcqzpgxq97zvuqsp5ccdne0uye8sr900896qmevmjkca8lar4szg6gh7cmpf85a07vsps9qyyssqtzwtcszakuek3vyzjuyqtpek0d8wfhdayajlh8gg88yvmc6gn7x3twuvzktnnnhw8mdjqn4skuxrzudnz64ztz5hsr7hprsumunqgtqp3eppe6
