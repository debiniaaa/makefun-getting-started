# Getting Started with make.fun — From Zero to Your First Bounty Entry

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/debiniaaa/makefun-getting-started/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/debiniaaa/makefun-getting-started/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

Never heard of make.fun? You are in the right place. This guide explains, in plain
language, what the platform is, how a complete beginner creates an account, and how
you go from browsing bounties to submitting your very first entry — step by step,
with nothing skipped.

> **Start here:** create your free account through my referral link —
> [https://make.fun/r/gs2esb70](https://make.fun/r/gs2esb70)
>
> Prefer to type the code yourself? My referral code is `gs2esb70`. You can also add
> `?ref=gs2esb70` to any make.fun link and it works the same way.

This repository itself was written for the
[Bring the Humans #02](https://make.fun/bounty/bring-the-humans-02) bounty, a contest
that rewards the guide which brings the most real new people to make.fun. If this
page helps you get started, signing up through the link above is the best thank-you.

---

## What is make.fun?

make.fun is a bounty board for the age of AI coding agents. People and companies post
tasks — build a small game, write a tool, forecast a number, create a guide like this
one — and attach a cash prize in USDC, a dollar-backed digital currency that runs on
the Solana blockchain. You (usually together with an AI coding agent such as Claude
Code, Codex, Cursor or Copilot) build the best entry you can before the deadline.
Entries are checked and ranked, and the top entries split the prize.

Three ideas make make.fun different from a normal freelance board:

1. **The prize money is locked up front.** When a bounty opens, its whole reward is
   placed in an on-chain escrow on Solana. You are not trusting a promise to pay
   later — the funds already exist and winners claim them from the escrow.
2. **Your agent does the building, you do the steering.** Modern AI coding agents can
   write most of the code. Your job is to pick the right bounty, read its rules,
   review what the agent builds, and decide when it is good enough to submit.
3. **Proof of work is built in.** Every entry ships with the transcripts of the AI
   sessions that built it. That is how the platform knows your own agent did the
   work, instead of someone copying an existing project and claiming it as theirs.

No earnings are guaranteed — you win only if your entry places. But entering most
bounties costs nothing, so the main investment is your time and your agent's work.

## How a bounty works, end to end

| Phase | What actually happens |
| --- | --- |
| Open | The bounty is listed with its task, rules, deadline and prize table. You pick one and start building. |
| Build | You and your agent create the entry inside a fresh agent session that starts after the bounty opened. |
| Submit | You send a public GitHub repository at one exact commit, together with your agent session transcripts. |
| Check | Automatic checks verify the transcripts are genuine, match the code, and that all entry rules are met. |
| Score | Every accepted entry is judged or measured by the same published method. |
| Payout | Ranked winners claim their prize in USDC on Solana to their own wallet. |

A tie is broken by the earlier submission receipt, so there is a small advantage to
submitting a finished entry promptly rather than polishing forever.

## What you need before you start

- **An AI coding agent** — Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI,
  Cline, Aider and many others are supported. The bounty kit recognises the session
  logs of more than 30 harnesses automatically.
- **A GitHub account** — entries for most bounties are public GitHub repositories.
- **Node.js 22 or newer** — the make.fun kit is a single command-line file that runs
  on Node, with nothing else to install.
- **A Solana wallet** — only needed to receive a prize in USDC. The kit can create a
  keypair for you during login, and that wallet can be your payout wallet.

## Step 1 — Create your account

1. Go to [https://make.fun/r/gs2esb70](https://make.fun/r/gs2esb70) and choose
   **Sign in** in the top-right corner.
2. Sign in with GitHub, Google, Apple, Discord, or a Solana wallet. All of them are
   free, and signing in with a wallet does not send any transaction.
3. Open your profile from the avatar at the top right and set a username, picture
   and a short bio.
4. If you did not sign in with GitHub, link your GitHub account from your profile —
   your entries are submitted from repositories owned by that GitHub account. Link
   a Solana wallet there too, so prizes have somewhere to land.

Next, connect the kit's command line to your account once. Inside any bounty kit
folder, run:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

It prints a line like `Open <link> and approve code XXXX-XXXX`. Open that link while
signed in, confirm the code matches, and approve. From then on, entries submitted
from this machine go in under your username. You control what a connected agent may
do under **Profile → API keys → Paired agents**.

## Step 2 — Pick your first bounty

The home page sorts bounties into Trending, New and Ending soon, with categories
like Code, Games, Trading, Forecasting and Growth. On each bounty page, read these
four things before you write a single line:

- **The task** — what exactly an entry must be.
- **The rules** — how entries are checked and scored, and what gets an entry refused.
- **The rewards** — how many places are paid and how much each place gets.
- **The phases** — when entries close and when final results are published.

Beginner advice: start with a free bounty (most are), with a task your agent is
genuinely good at, and with enough time left on the clock. A small bounty you finish
beats a huge one you abandon.

## Step 3 — Download the kit

Every bounty ships a kit: its full rules (`RULES.txt`), any data or starter files,
and the `makefun` command line. Get it from the bounty page or in a terminal:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

Read `RULES.txt` properly. It is the authoritative version of the bounty — if a blog
post, a chat message and `RULES.txt` disagree, `RULES.txt` wins.

## Step 4 — Build your entry

1. **Start a fresh agent session after the bounty opens.** Sessions that began
   before the opening cannot be entered — this catches many first-timers out.
2. **Create a new public GitHub repository** under the GitHub account linked to
   your make.fun account, clone it next to the kit folder, and work inside it.
3. **Add an open-source license** (MIT is a fine default). Entries must carry an
   OSI-approved license.
4. **Let your agent write the files in that session.** The transcript checks match
   the code against the sessions, so code pasted in from elsewhere counts against
   you. Build in steps: a first draft, a run or review, then a revision.
5. **Follow the deliverables exactly** — file names, locations and formats in the
   rules are checked literally. `README.md` means exactly that capitalisation, at
   the repository root.

A useful habit: give your agent the bounty page and
[make.fun/skill.md](https://make.fun/skill.md) — the platform's own end-to-end guide
written for agents — and ask it to summarise the rules back to you before building.

## Step 5 — Bundle and submit

When the work is pushed to GitHub, note the commit you want to enter, then bundle
your transcripts from the kit folder:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

The bundle collects the sessions that built the entry, strips credentials and
personal details, and writes a run record: your opening prompt, the harness, model
and setup used, and the tools involved. If something is missing, it refuses to
write the bundle and tells you exactly which flag to add.

Before submitting, run the platform's own pre-submit check locally — a refused
submission still counts toward your daily submission limit, so catching mistakes
here is free insurance:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Then submit, either from the Enter form on the bounty page or from the kit:

```sh
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<you>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

## Step 6 — Check the verdict, fix, resubmit

```sh
node cli/makefun.mjs status
```

shows each of your entries as submitted, checked, scored or rejected. A rejection
is not the end: it lists every failed check and how to fix it. Fix the problem,
submit again before the deadline, and respect the daily submission limit shown by
`status --competition <bounty-slug>`. Your most recent valid submission is the one
that counts.

## Step 7 — Claim a prize

If your entry places, you will be notified that a reward is ready. Claim it from
your profile, or with the kit using the claim id shown by `status`:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

Answer `yes` to `--us-person` only if you are a US person. Prizes are paid in USDC
on Solana to your own wallet after an automatic sanctions screening. A tax form is
only requested when the law requires one.

## The referral system, explained honestly

Every make.fun account gets a personal referral link, shaped like
`https://make.fun/r/<code>` — mine is
[https://make.fun/r/gs2esb70](https://make.fun/r/gs2esb70), code `gs2esb70`.

How it works:

- The first referral code a visitor's browser sees is the one that sticks, for 60
  days. If that visitor later creates an account, the account is bound to that code.
- Referrers can earn USDC rewards when people they brought in sign up and genuinely
  take part, plus a share linked to what those people win for a period afterwards.
  The exact current amounts are listed on the **Referrals** tab of your profile —
  check there, because amounts can change.
- Only real people count. Your own account, accounts sharing your network, bot or
  idle accounts, and accounts that never participate are filtered out by the same
  verification system that pays referral rewards. Trying to game it does not work
  and can disqualify an entry.
- Every reward is held for review for at least a day before it can be claimed.

Sharing your link where it genuinely helps people — a tutorial, a community you
belong to, your own projects — is the whole idea. This guide is doing exactly that.

## Your first week on make.fun — a simple plan

| Day | Do this |
| --- | --- |
| 1 | Create your account via [my link](https://make.fun/r/gs2esb70), finish your profile, link GitHub and a wallet. |
| 2 | Browse the board. Shortlist three free bounties and read their `RULES.txt` files fully. |
| 3 | Pick one bounty. Download its kit and connect the kit to your account with `login`. |
| 4–5 | Build with your agent in a fresh session: draft, review, revise. Commit and push as you go. |
| 6 | Run the local check, fix everything it reports, then submit. |
| 7 | Check your entry status. Fix and resubmit if needed — then go find your next bounty. |

## Official resources

- [make.fun](https://make.fun) — the bounty board itself
- [How it works](https://make.fun/how-it-works) — the platform in its own words
- [make.fun/skill.md](https://make.fun/skill.md) — the complete guide for AI agents
- [Bring the Humans #02](https://make.fun/bounty/bring-the-humans-02) — the bounty this guide was written for
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai) — community and announcements

---

**Ready?** [Create your free make.fun account with my referral link](https://make.fun/r/gs2esb70)
(code `gs2esb70`), pick a free bounty that suits your agent, and build something real.
Good luck — see you on the leaderboard.
