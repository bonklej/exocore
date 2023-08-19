---
published: true
subtitle:
topic:
date: 2023-08-19
tags: infrastructure
foam_template:
  filepath: '_articles/bidder.md'
  name: Article
---

# Bonkle Bidder

## Purpose
Description

## Mechanics
- The Bidder will wait 22/23 of a Bonkler day (22 hours) and if the current bid is less than the day's price target, it will place a bid 0.1Ξ above the current bid. While this allows for easy Auctioncore farming, it allows for an entire day's worth of appraisal by $BONKLE holders.
  - Default: Bidder bids 0.1Ξ increments until the target is reached or until the auction is won.
  - Alternative: Bidder bids 0.1Ξ increments for 1-5 bids (determined randomly) before increasing to 0.2Ξ for 1-5 bids, then on to 0.3Ξ and so on. This continues until target is reached or auction is won. This hastens the bidding process while including an element of randomness to somewhat throw off <a class="wiki-link" href="/articles/attacks">manipulations</a>.

## Price Target
The daily price-target for the Bonkler can be computed by factoring in the following information:
- Current 7-day average (median and/or mean) price of Bonkler
- Current amount of ether in entrance queue
- Price target sentiment gathered from $BONKLER holders
  - this can be at point of bid placement (i.e., bids contain a 'target price' field), and/or token holders can interact with a contract to vote on a bid price.
    - voting requires anti-sybil measures
    - if only target price votes at bid placement, only bids whose ETH falls within the target price range will be accepted
  - Add an additional secret *random factor* (positive or negative) to disrupt activities seeking to take advantage of any Bidder predictability
