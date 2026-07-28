<p align="center">
  <a href="https://twetch.com">
    <img src="https://twetch.com/twetch-unfurl-thumbnail-og-image.png" alt="Twetch — the on-chain social network" width="820">
  </a>
</p>

<p align="center">
  <a href="https://twetch.com"><b>twetch.com</b></a> ·
  <a href="https://twetch.com/market">Market</a> ·
  <a href="https://twetch.com/meme-library">Meme Library</a> ·
  <a href="https://twetch.com/leaderboard">Leaderboard</a> ·
  <a href="https://twetch.com/search">Search</a> ·
  <a href="https://x.com/twetchapp">@twetchapp</a>
</p>

---

## The on-chain social network

Twetch is the social network where you own your content. Every post, like and
follow is a real Bitcoin transaction, signed by your own identity key — so
nothing can be quietly deleted, deplatformed, or lost when someone else's server
dies.

Around since 2019.

## What's on Twetch

| | |
| --- | --- |
| **[Home](https://twetch.com)** | The on-chain feed — posts, replies, branches, polls. |
| **[Market](https://twetch.com/market)** | Browse and trade on-chain NFT collections. |
| **[Meme Library](https://twetch.com/meme-library)** | The pepe, wojak and apu archive — [thousands of memes](https://twetch.com/meme-library/category/apu-memes) preserved on chain instead of on a host that eventually goes down. |
| **[Leaderboard](https://twetch.com/leaderboard)** | Who's actually posting. |
| **[Search](https://twetch.com/search)** | Posts, people and memes across the whole network. |

## For developers

Reads need nothing. No key, no account, no signup — because indexers,
dashboards and analytics are the easiest things to build and they shouldn't
require permission.

```rust
use twetch::{Client, FeedQuery};

let twetch = Client::new()?;
let feed   = twetch.feed().latest(&FeedQuery::default().limit(25)).await?;
let user   = twetch.users().by_name("npc69").await?;
let thread = twetch.posts().thread(post_id).await?;
```

Writes need an identity, and every one of them lands on chain:

```rust
let me = Client::new()?.identity(Identity::new(user_id, signer));

me.posts().create("gm").send().await?;
me.posts().like(1234).await?;
me.users().follow(99).await?;
```

**[twetch-rs](https://github.com/twetch-inc/twetch-rs)** — the Rust SDK.
Posting, liking, following, reading and every twonk action.

Account creation and chat are deliberately out of scope, permanently: both
involve key material that belongs in a first-party client, not in an SDK
somebody else embeds.

---

<p align="center">
  <a href="https://twetch.com">twetch.com</a> ·
  <a href="https://x.com/twetchapp">@twetchapp</a>
  <br><br>
  <sub>Twetch — the on-chain social network.</sub>
</p>
