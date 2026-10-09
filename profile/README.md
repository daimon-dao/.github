<div align="center">

<img src="https://raw.githubusercontent.com/daimon-dao/daimon-dao/master/social-assets/brand/daimon-logo-ring-512.png" alt="Daimon DAO" width="140" />

# Daimon DAO

**No owner. No mint. Floor 21B. — DAO on BNB Chain**

[daimon.money](https://daimon.money) · [app.daimon.money](https://app.daimon.money) · [daimon-dao/daimon-dao](https://github.com/daimon-dao/daimon-dao)

</div>

---

Daimon is a BEP-20 token with reflection, vote-escrow staking, on-chain
governance and a public timelock, on BNB Chain / PancakeSwap. Control belongs
to the DAO through a Timelock; the deployer renounced every role after deploy.
The supply can only decrease, never below an immutable floor. Everything the
contracts do is verifiable on-chain, and the full source is public.

## Principles

- **No owner.** No privileged address can move funds or change parameters
  unilaterally. Every action goes through the DAO and the Timelock.
- **No mint.** The token has no mint function. The initial supply is the
  maximum that will ever exist.
- **21B immutable supply floor.** The supply decreases through burns and can
  never fall below `MIN_SUPPLY`, enforced at the code level.
- **7-day timelock on every decision.** Every approved proposal waits at
  least 7 days before it can execute — a public reaction window that applies
  to the DAO itself too.

## Status

**Live on BNB Smart Chain mainnet since 2026-09-29.** The audited code was
deployed unchanged, verified on BscScan and Sourcify, and the deployer
renounced every role in the same run. A 2-of-3 guardian multisig can only
cancel a queued proposal or pause the token for at most 14 days at a time;
its mandate ends on 2029-09-28, enforced by the contracts. Every step of the
launch is recorded in the
[mainnet launch record](https://github.com/daimon-dao/daimon-dao/blob/master/docs/MAINNET_LAUNCH_RECORD.md).

**Audited by Zenith.** The
[full report](https://github.com/zenith-security/reports/blob/main/reports/Daimon%20DAO%20-%20Zenith%20Audit%20Report.pdf)
is public: 37 findings, 29 fixed in code and 8 accepted with a written
rationale. The audited code range is frozen at tag
[`audit-final`](https://github.com/daimon-dao/daimon-dao/releases/tag/audit-final).

**Migration open until 2026-12-28 01:08:44 UTC.** Holders of the old token
(DMX) swap 1:1 for DMN on [app.daimon.money](https://app.daimon.money).
The deadline is immutable (a guardian pause of the token would extend it by
the same length). After the deadline no claim is accepted any more, and the
unclaimed DMN can only be swept, once, to the DAO treasury by the Timelock
(`sweepUnclaimed`): no other destination exists in the contract.

## Protocol paper

**[Protocol paper v0.2 (EN)](https://github.com/daimon-dao/daimon-dao/releases/tag/protocol-paper-v0.2)** —
the post-audit release of 2026-09-11, with the Italian translation, the
changelog and the versioning policy in
[docs/protocol-paper](https://github.com/daimon-dao/daimon-dao/tree/master/docs/protocol-paper).

## Code and contracts

The main repository — contracts, tests, threat model, launch record and dApp:
**[daimon-dao/daimon-dao](https://github.com/daimon-dao/daimon-dao)**

Verified contracts on BNB Smart Chain (chainId 56). Always verify an address
on-chain before interacting:

| Contract | Address |
|---|---|
| **DMN** — the token (`DaimonV2`, UUPS proxy) | [`0x160864F9945C52063A7c9f5dcd57C0C89eacbE6a`](https://bscscan.com/address/0x160864F9945C52063A7c9f5dcd57C0C89eacbE6a) |
| `DaimonMigration` — DMX → DMN, 1:1 | [`0x76368b60514b145617385847aCFF7b7EA9764725`](https://bscscan.com/address/0x76368b60514b145617385847aCFF7b7EA9764725) |
| `DaimonStaking` | [`0xBb596e7308D6C5AED55cEC597D372840Cbe575b1`](https://bscscan.com/address/0xBb596e7308D6C5AED55cEC597D372840Cbe575b1) |
| `DaimonGovernor` | [`0x1397a7d25595B718BE6FEEDd42ed5E60F66E16De`](https://bscscan.com/address/0x1397a7d25595B718BE6FEEDd42ed5E60F66E16De) |
| `DaimonTimelock` — the treasury, holds the LP | [`0xCdaa1CFe783a4DE642ca3Ed98A38bFdC16f30891`](https://bscscan.com/address/0xCdaa1CFe783a4DE642ca3Ed98A38bFdC16f30891) |
| DMX — the old token, migrating to DMN | [`0x36EbA94407B53c631eE822C219e94580fadd67c7`](https://bscscan.com/address/0x36EbA94407B53c631eE822C219e94580fadd67c7) |

The full table, with the launch pool and the guardian, is in the
[main README](https://github.com/daimon-dao/daimon-dao#mainnet-addresses).

## dApp and its mirror

The official dApp is [app.daimon.money](https://app.daimon.money). A
reproducible build of the same dApp is published on IPFS as a backup, reachable
as `daimon.blockchain` in Brave (with "Resolve Unstoppable Domains names" on)
or with the Unstoppable Domains extension. The mirror is identified by its
content hash: the current CID, how it was built and how anyone can reproduce
it are in
[docs/IPFS_MIRROR.md](https://github.com/daimon-dao/daimon-dao/blob/master/docs/IPFS_MIRROR.md).
A different CID is a different site, whoever serves it.

## Official channels

| Channel | Link |
|---|---|
| Website | https://daimon.money |
| dApp | https://app.daimon.money |
| Telegram — announcements | https://t.me/Daimon_one |
| Telegram — community group (EN) | https://t.me/Daimon_Official_Group |
| Telegram — community group (IT) | https://t.me/Daimon_Official_Italian_Group |
| X (Twitter) | https://x.com/DaimonDAO |
| GitHub | https://github.com/daimon-dao |
| Email | info@daimon.money |

Any channel not listed here is not official.

**No admin will ever DM you first. Nobody will ever ask for your seed phrase or
private key. Always verify contract addresses on-chain.**

## Security

Found a vulnerability? **Do not open a public issue.** Use the private channel
(GitHub → Security → Report a vulnerability) — details in
[SECURITY.md](https://github.com/daimon-dao/daimon-dao/blob/master/SECURITY.md).
