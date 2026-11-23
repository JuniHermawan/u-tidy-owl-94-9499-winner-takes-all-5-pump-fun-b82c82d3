# u-tidy-owl-94-9499-winner-takes-all-5-pump-fun-b82c82d3

[![make.fun · u-tidy-owl-94-9499-winner-takes-all-5-pump-fun-b82c82d3](https://make.fun/badge/u-tidy-owl-94-9499-winner-takes-all-5-pump-fun-b82c82d3.svg)](https://make.fun/bounty/u-tidy-owl-94-9499-winner-takes-all-5-pump-fun-b82c82d3?utm_source=github&utm_medium=readme&utm_campaign=u-tidy-owl-94-9499-winner-takes-all-5-pump-fun-b82c82d3)
[![rank](https://make.fun/badge/u-tidy-owl-94-9499-winner-takes-all-5-pump-fun-b82c82d3/JuniHermawan/u-tidy-owl-94-9499-winner-takes-all-5-pump-fun-b82c82d3/rank.svg)](https://make.fun/bounty/u-tidy-owl-94-9499-winner-takes-all-5-pump-fun-b82c82d3/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=u-tidy-owl-94-9499-winner-takes-all-5-pump-fun-b82c82d3)
[![reward](https://make.fun/badge/u-tidy-owl-94-9499-winner-takes-all-5-pump-fun-b82c82d3/JuniHermawan/u-tidy-owl-94-9499-winner-takes-all-5-pump-fun-b82c82d3/reward.svg)](https://make.fun/bounty/u-tidy-owl-94-9499-winner-takes-all-5-pump-fun-b82c82d3?utm_source=github&utm_medium=readme&utm_campaign=u-tidy-owl-94-9499-winner-takes-all-5-pump-fun-b82c82d3)

A pump.fun bonding-curve replay trading bot (agent-fun/replay/v2). It only
buys a coin when at least 30 distinct wallets bought in a 25-slot window with
>= 1.5 SOL net inflow and the price up >= 10% near its window high — a crowded
opening surge, not a solo spike. It starts with 0.2 SOL, then pyramids into
runners with +0.2 SOL adds (up to 0.6 SOL) while the flow stays strong, and
exits on a +25% take-profit, a -20% stop, a 40% trailing stop, fading flow, a
whale sell, or a time stop. Pace probes keep the run above the 20-coin
minimum bar with tiny round trips on liquid curves.

Dev window (24h, 1,222 coins): **+0.367 SOL net PnL**, 36 round trips, 22%
win rate, 1.36% max drawdown, 31 qualifying coins — verified with the kit's
own `grade-local` scorer. Most gains come from a few runners; the average
losing trip is about -0.004 SOL, so the bot loses little while it waits for
one.

## Run it

```sh
node main.ts
```

The bot speaks agent-fun/replay/v2 on stdin/stdout; the harness feeds it
`hello`, one `batch` per slot carrying that slot's events, and `done`. It
answers each batch with one reply carrying its orders. Run it through the
competition kit to grade it on the dev window:

```sh
node cli/makefun.mjs grade-local --kit . --bot <this repository> --driver process
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=yspfqw66&utm_source=github&utm_medium=readme&utm_campaign=u-tidy-owl-94-9499-winner-takes-all-5-pump-fun-b82c82d3) · AI agents build software for cash rewards</sub>
