<div align="center">

<img src="https://raw.githubusercontent.com/daimon-dao/daimon-dao/master/social-assets/logo-512.png" alt="Daimon DAO" width="140" />

# Daimon DAO

**No owner. No mint. Floor 21B. — DAO on BNB Chain**

</div>

---

Daimon is a BEP-20 token with reflection, vote-escrow staking, on-chain
governance and a public timelock, on BNB Chain / PancakeSwap. Control belongs
to the DAO through a Timelock; the deployer renounces every role after deploy.
The supply can only decrease, never below an immutable floor. Everything the
contracts do is verifiable on-chain, and the full source is public.

## Principles

- **No owner.** No privileged address can move funds or change parameters
  unilaterally. Every action goes through the DAO and the Timelock.
- **No mint.** The token has no mint function. The initial supply is the
  maximum that will ever exist.
- **21B immutable supply floor.** The supply decreases through burns and can
  never fall below `MIN_SUPPLY`, enforced at the code level.
- **7-day timelock on every decision.** Every approved proposal waits 7 days
  before it can execute — a public reaction window that applies to the DAO
  itself too.

## Status

Contracts are deployed and verified on **BSC testnet**. An **external audit is
in preparation**. There is **no mainnet date**, and there will not be one until
the audit is complete.

## Whitepaper

**[Whitepaper v0.1 (EN)](https://github.com/daimon-dao/daimon-dao/releases/download/whitepaper-v0.1/Daimon_Whitepaper_EN_v0.1.pdf)** ·
[versione italiana](https://github.com/daimon-dao/daimon-dao/releases/download/whitepaper-v0.1/Daimon_Whitepaper_IT_v0.1.pdf) —
draft pending the external audit; versioning policy in
[docs/whitepaper](https://github.com/daimon-dao/daimon-dao/tree/master/docs/whitepaper).

## Code and contracts

The main repository — contracts, tests, threat model and dApp:
**[daimon-dao/daimon-dao](https://github.com/daimon-dao/daimon-dao)**

Verified contracts on BSC testnet:

| Contract | Address |
|---|---|
| `DaimonV2` | [`0xf9a4…4202`](https://testnet.bscscan.com/address/0xf9a4d8b6ae6e37f198443e9855e3788119c94202#code) |
| `DaimonStaking` | [`0x2f21…3606`](https://testnet.bscscan.com/address/0x2f2135885617cd226214cf8fd3b945fddaea3606#code) |
| `DaimonGovernor` | [`0xe244…9c52`](https://testnet.bscscan.com/address/0xe2445551f1d6c487e6cfb48f8621ccfb4d919c52#code) |
| `DaimonTimelock` | [`0x6a98…27f5`](https://testnet.bscscan.com/address/0x6a98fd0c0306672e4abfbe90fc303726022427f5#code) |
| `DaimonMigration` | [`0x4c6f…5bb2`](https://testnet.bscscan.com/address/0x4c6f45b0148534296d8f9660eba5cc3598855bb2#code) |

## Official channels

| Channel | Link |
|---|---|
| Telegram — announcements | https://t.me/Daimon_one |
| Telegram — community group (EN) | https://t.me/Daimon_Official_Group |
| Telegram — community group (IT) | https://t.me/Daimon_Official_Italian_Group |
| X (Twitter) | https://x.com/DaimonDAO |
| GitHub | https://github.com/daimon-dao |

Additional official channels will be listed here as they go live. Any channel
not listed here is not official.

**No admin will ever DM you first. Nobody will ever ask for your seed phrase or
private key. Always verify contract addresses on-chain.**
