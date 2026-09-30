# Loose Pixels

**Builder:** [@floflo777](https://github.com/floflo777)
**Categories:** Character Spotlight · Token Activity · Economy Potential

**One sentence:** Your Rare Friend's own 16×16 on-chain pixels are its health: every hit knocks a pixel off, time heals it, and $RAREFRIENDS regrows it — inside a Club Penguin-like hub, The Sky.

- **Play:** https://loose-pixels.florent-g.workers.dev
- **Source:** https://github.com/floflo777/pixel-life

## How to play
- **Fling:** drag back and release to launch your Friend at the Munchies (pixel-eating creatures).
- **Grab back:** a bite knocks pixels off your Friend. Sweep over them within 2 s or they're lost.
- **Scars persist** on your Friend between runs and heal for free over time (0.5 px/h).
- **The Sky:** walk around the hub with other players' Friends, use emotes, and enter venues.
- **Mend:** help a stranger's scarred Friend.

No wallet needed: **Play now** starts with a loaned real Friend. With your own Friend (Robinhood Chain, Generations gen ≥ 1), the FriendSDK checks ownership, then progress is saved.

## $RAREFRIENDS (simulated in this MVP, contracts spec'd for live)
| Action | Price | Where the RF goes |
|---|---|---|
| Regrow your Friend | 0.5 RF / px | 50% burned · 50% to active Friends (`ActivationManager.fund`) |
| Mend another Friend | 1 RF / px | 50% burned · 50% **into that Friend's ERC-6551 wallet** |
| Seed Pack (FriendSDK chance game) | 5 RF | Published odds, EV 4.48 RF. The top prize is a **Gold Pixel**: wear it or redeem it |
| Gold Pixel market | 5% fee | 2% burned · 2% to the Friend that grew it · 1% creator |

The soft currency (Bits) is earned by playing, buys cosmetics and home decor, and never converts to RF. No RF is minted, and none moves from loser to winner.

## Stack
- **Game:** TypeScript and three.js (voxel Friend from its on-chain sprite), with a deterministic sim shared by client and server.
- **FriendSDK v0.1.4:** wallet, ownership gate, sprites, and the Seed Pack as a stock SDK venue (`friendsdk check`/`test` pass).
- **Backend:** Node, Fastify, WebSockets and PostgreSQL, behind a Cloudflare Worker.
- **Contracts:** `PixelLifeSink` and `GoldPixelMarket` (Foundry, 22 tests), not deployed.

## Status
- **Tests:** ~890 automated tests pass. The sim replays identically in Chromium, WebKit and Firefox.
- **Integration:** the live preview is still being wired end to end, and this entry will be updated.
- **Guest mode:** it runs outside the SDK runtime. We'll switch it off if the organizers prefer.

**Credits:** Rare Friends artwork via FriendSDK (Apache-2.0) · Kenney 1-Bit Pack (CC0) · Silkscreen font (OFL).
