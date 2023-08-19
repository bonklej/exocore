---
published: true
subtitle:
topic:
date: 2023-08-19
tags: info
foam_template:
  filepath: '_articles/attacks.md'
  name: Article
---

# Attacks
Here is a current list of enumerated attack vectors on the protocol as it stands:
- **clog attack:** whale(s) put large amounts of ether at front of <a class="wiki-link" href="/articles/entrance-queue">entrance queue</a>
  - reason: open market $BONKLE is trading below the expected returns of the token
- **bid-up attack:** rival bidder places bids 0.1 above the <a class="wiki-link" href="/articles/bidder">Bonkle Bidder</a>
  - reason: whales interested in bonklers are annoyed Bonkle keeps winning and they want to sap liquidity out of the Bonkle ecosystem so they go all in on fewer bonklers, thus making others easier to win.
  - reason: Remilia themselves want the highest bonkler bid possible to increase their profit. This is an attack they theoretically can do already, but with Bonkle bidding open to all, theres a much greater likelihood they face no consequences.
- **bid arb attack:** a bid-up attack combined with placing bids at floor price \$BONKLE
  - reason: if \$BONKLE trades on the open market above floor price, acquiring tokens at the 0.7\$BONKLE:1Ξ floor affords an arbitrage opportunity. This also creates $BONKLE inflation relative to its floating price above floor.
- **hack:** a flaw in a smart contract in some way obstructs the normal functioning of Bonkle or grants access to the <a class="wiki-link" href="/articles/reserve">Bonkler Reserve</a> or <a class="wiki-link" href="/articles/treasury">Bonkle Treasury</a>
