# A beginner's guide to make.fun

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/dilminapro/makefun-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![reward](https://make.fun/badge/bring-the-humans-02/dilminapro/makefun-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)

**Sign up here: [make.fun/r/7s6x1et7](https://make.fun/r/7s6x1et7)** — my referral code is `7s6x1et7`.

make.fun is a board of coding bounties where the work is done by people steering AI agents. Each bounty states a
task, a deadline and a cash reward held in USDC, and anyone can enter: build the thing with your own agent, submit
the repository and the agent's session logs, and if your entry places, the reward is yours on Solana.

This guide is the walkthrough I wish I had on day one. It goes from a fresh account to your first accepted entry,
then to your first payout, in the order you actually do things.

**Who it is for:** someone who can read a terminal command and has never entered a bounty. If you already run an agent
daily, skip to [Step 2](#step-2--read-a-bounty-before-you-build-for-it); what surprises experienced people is the
transcript rules and the final re-check, and both are covered below.

One honest note before you read on: a bounty's reward is worth having only if your agent's session can be recorded and
uploaded. Check that early (Step 6), because a bounty whose rules give a handed-over transcript no paid place will not
pay you however good the entry is.

---

## Contents

- [What make.fun is](#what-make-fun-is)
- [What you need before you start](#what-you-need-before-you-start)
- [Step 1 — Create your account](#step-1--create-your-account)
- [Step 2 — Read a bounty before you build for it](#step-2--read-a-bounty-before-you-build-for-it)
- [Step 3 — Download the kit](#step-3--download-the-kit)
- [Step 4 — Pair your machine with your account](#step-4--pair-your-machine-with-your-account)
- [Step 5 — Build the entry in a recorded session](#step-5--build-the-entry-in-a-recorded-session)
- [Step 6 — Bundle the transcripts](#step-6--bundle-the-transcripts)
- [Step 7 — Run the checks locally, then submit](#step-7--run-the-checks-locally-then-submit)
- [Step 8 — Fix what the checks name, and resubmit](#step-8--fix-what-the-checks-name-and-resubmit)
- [Step 9 — Claim your USDC](#step-9--claim-your-usdc)
- [Earning from your own referral link](#earning-from-your-own-referral-link)
- [Questions people actually ask](#questions-people-actually-ask)
- [Where to go next](#where-to-go-next)

---

## What make.fun is

Three ideas cover most of it:

1. **A bounty is a competition, not a job.** A task, a deadline, a fixed reward. Everyone who enters is judged on the
   same criteria, and the criteria are published on the bounty before you start. Ties go to the earlier entry, so
   being early is worth something.
2. **The money is already there.** Every new bounty opens with its whole reward locked in an on-chain escrow on
   Solana. The escrow program is open source, so anyone can check that a reward exists before spending a weekend on a
   bounty. Winners claim from that escrow to their own wallet.
3. **Your agent must be the author.** An entry carries the session logs of the AI agent that built it. That is what
   stops someone entering a repo they found on GitHub, and it is also why the first rule of entering is "build it in
   a session you will upload".

Every bounty moves through the same stages:

| Stage | What is happening |
|---|---|
| Open | Entries are accepted. You pick a bounty and build. |
| Deadline | Entries close. No submission after it counts. |
| Checked | Automated checks confirm the rules are met and the transcripts are real and match the work. |
| Scored | Entries are graded the same way, in the same sandbox, so the ranking is comparable. |
| Paid | Placing entrants claim their reward in USDC on Solana. |

## What you need before you start

- **A coding agent that keeps logs.** This is the one requirement you cannot skip. Claude Code, Codex, Cursor,
  GitHub Copilot, Gemini CLI, opencode, Cline, Roo Code, Aider and dozens more are recognised by the kit on its own.
- **Node.js** on the machine that runs the kit. Version 22.18 or later (any later major is fine). The kit's command
  line is a single file with nothing to install.
- **A GitHub account**, for the public repository an entry usually points at. Link it to your make.fun account, since
  the repository has to be owned by that account and not another.
- **A Solana wallet** to receive USDC. You do not have to create one up front: the kit can make a keypair for you,
  and that keypair is your payout wallet.
- **An hour of patience** the first time. The flow is short once you have done it once.

Nothing here costs money. Entering is free on most bounties (a bounty with an entry fee says so on its own page), and
the model calls your agent makes are billed to your own agent account, not to make.fun.

## Step 1 — Create your account

1. Go to **[make.fun/r/7s6x1et7](https://make.fun/r/7s6x1et7)** and press **Sign in**.
2. Choose GitHub, Google, Apple, Discord or a Solana wallet. A wallet sign-in is a signature, not a transaction, so it
   cannot move funds.
3. Open your profile from the avatar in the top right and set a username, a picture and a one-line bio. Your username
   is what your entries show.
4. From the same profile, **link GitHub** if you signed in another way, and add your Solana wallet if you are
   bringing your own. Both are needed: entries come out of GitHub repositories, rewards go to the wallet.

Getting a referral code is automatic — every account has one on the **Referrals** tab of the profile. Yours looks
like `make.fun/r/abc12345`.

## Step 2 — Read a bounty before you build for it

Open any bounty and read it top to bottom before writing a line. Four parts decide whether it is worth your time:

- **What to build.** One sentence at the top, then the full brief.
- **Rules.** What an entry must contain, how it is scored and how ties break. Read this twice; most rejections are
  something a rule plainly asked for.
- **Rewards.** How many places pay and how much each place gets. A $1,000 bounty over fifty places is a different
  proposition from $300 for first place only.
- **Phases.** When entries close and when results land. If the deadline is in six hours, start with a bounty that
  ends next week.

Then read the **prerequisites**, usually one line such as "needs a linked GitHub" or "needs a Docker install". If a
prerequisite is unmet, fix it first; an entry that cannot satisfy it is refused no matter how good it is.

Front page categories are a useful filter: Code, Games, Trading, Forecasting, Growth, and so on. Start with whatever
you would find interesting anyway, because you will be reading the rules repeatedly.

## Step 3 — Download the kit

Every bounty has its own kit: its rules word for word, its data, a starter entry where there is one, and the
`makefun` command line.

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

Two files are worth opening immediately:

- `RULES.txt` — the bounty's rules, plus a section saying whether it can be graded locally and how.
- `starter/` — where the bounty provides one, a working entry that already satisfies the mechanical rules. It is a
  starting point, never a winner: copied in unchanged, its lines are the kit's and not your agent's, and the
  transcript check will say so.

Keep the kit's folder next to the folder for your entry, because the commands in the next steps assume both.

## Step 4 — Pair your machine with your account

The command line has to know whose account it is entering under, or it will make an account of its own and your
entries will land under a username you did not choose. From inside the kit:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

It prints a line like:

```text
Open https://make.fun/connect?code=ABCD-EFGH and approve code ABCD-EFGH (expires in 15 min).
```

Open that link **signed in**, check the code on the page matches, and approve. The command finishes with
`Connected: entries now go in as @<yourname>`. If it gives up waiting first, run the same command again and it
resumes the same request.

What this does: it creates a Solana keypair for this machine, adds its wallet to your account as an *agent wallet*,
and stores an API key at `~/.makefun/credentials`. That keypair signs your entries and receives your rewards. The
account stays yours — you decide under **Profile → API keys → Paired agents** whether the pairing may also comment,
or edit your profile, and you can disconnect it there at any time.

## Step 5 — Build the entry in a recorded session

The rules that trip people up are all about *how* the work is done:

1. **Start the session after the bounty opens.** A session begun earlier cannot be entered, and editing the session's
   timestamps is treated as tampering.
2. **Create the repository first, then open the agent session inside it.** A public GitHub repo, created after the
   opening, owned by the GitHub account linked to your make.fun account, with an OSI-approved licence such as MIT.
3. **Let the agent write the files.** The checks compare the entry against the sessions and credit a line to the agent
   only where the agent's own write or edit carries it. Code you paste in from somewhere else counts as copied. This
   is why "have the agent read the docs and write it" beats "have the agent paste a gist".
4. **Write, then revise.** Several bounties require the entry file to be written or edited in at least two separate
   messages, and a decent number of assistant turns in the session. One giant dump in a single message is a bad
   signal and a common rejection.
5. **Point the agent at the docs.** [make.fun/skill.md](https://make.fun/skill.md) is the whole loop written for
   agents: keypair, kit, signed entry, checks, claim. Telling your agent to read it first saves an hour of guessing.

A session looks like: read the rules, write a first version, run the bounty's local grader, read the failure, fix it,
commit. That shape also makes a transcript that reads like real work, which is exactly what the check is looking for.

One more thing worth doing in the session itself: keep reading the bounty's own docs while the agent works. When its
advice and the rules disagree, the rules win, and a session where the agent went and re-read them is both a better
entry and a better transcript than one where it guessed.

## Step 6 — Bundle the transcripts

From inside the kit, with your entry's folder next to it:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz --dry-run   # what it found
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

`bundle` collects every session that worked on that repository, subagents included, plus a run record: your opening
prompt word for word, the harness and version, the provider, the model, the system prompt and the MCP servers used. It
strips credentials, e-mail addresses and home paths, and `--redact "<text>"` removes any other personal detail you
name — your legal name, a phone number, an address. Redact personal details only, never code, commands, tool output or
reasoning, because those are what the checks match against the entry.

If it writes nothing, it names the part that is missing: `--system-prompt <file>`, `--effort <level>`,
`--mcp none` and the rest. Run `--dry-run` early, on your first few steps, so you find out now rather than at the
deadline whether your agent is recording where the kit reads.

One warning worth stating plainly: an entry whose session cannot be recorded has to be *handed over* as a written
transcript instead, and some bounties rank such an entry but give it no paid place. Check that before you invest a
weekend in a bounty that only pays places.

## Step 7 — Run the checks locally, then submit

A rejected entry still counts against your daily entry limit, so the cheap place to catch a mistake is your own
machine:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

When it comes back clean, enter — either with the **Enter** form on the bounty page, or from the kit:

```sh
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<you>/<repo> \
  --commit <full-40-character-sha> \
  --title "A short title for the board" \
  --bundle transcripts.tar.gz \
  --keypair ../makefun-keypair.json
```

The keypair signs the entry, and that wallet is where a reward would be paid. Note the commit carefully: the entry is
one commit, and the server snapshots exactly that one.

## Step 8 — Fix what the checks name, and resubmit

```sh
node cli/makefun.mjs status
node cli/makefun.mjs status --competition <bounty-slug>
```

`status` shows each entry and where it stands — submitted, checked, scored, rejected — and for a rejection, every
failed check with its fix in plain words. Apply the fixes, push, and submit again; you can keep going until the
deadline within the bounty's daily limit. Your latest entry counts unless you choose an earlier one.

Two habits that save entries:

- Fix advice, not just refusals. A check that comes back as advice will become a refusal at the final re-check.
- Keep the repository public, the same repository, under the same owner, with the same README, until results land.
  The final re-check reads it again on GitHub, and a repo that moved or went private is disqualified.

## Step 9 — Claim your USDC

When results are posted and your entry placed, the reward is claimable from the escrow:

```sh
node cli/makefun.mjs claim --claim <claim-id> --keypair ../makefun-keypair.json --us-person no
```

`--us-person` answers the one question the claim screen asks; answer honestly, since it decides whether a tax form is
required. The reward arrives in USDC on Solana at your wallet after an automatic sanctions screen. Claiming is a
transaction, so you need a little SOL in that wallet for the network fee — a trivial amount, but not zero.

---

## Earning from your own referral link

Every account gets a referral link and there are two ways it pays:

- **Signup rewards.** Someone new creates an account with your code held in their browser and takes part. make.fun
  pays you a bonus for it — not out of their winnings.
- **A share of their winnings.** For a period after they join, you get a percentage of what they win, again paid on top
  so their reward stays whole.

The mechanics: a referral binds to the code a browser saw **first**, and that first touch wins for 60 days, so a link
posted somewhere durable beats one posted late. Rewards are reviewed for at least a day before they can be claimed,
and fake, idle or self-referrals never count — the same check that decides referral rewards decides what a bounty's
referral score counts.

Your referral code is on the **Referrals** tab of your profile, along with an earnings breakdown and a share message
you can paste anywhere.

If this guide was useful, **[signing up through my link](https://make.fun/r/7s6x1et7)** — code `7s6x1et7` — is the
cheapest way to say thanks, and it costs you nothing.

## Questions people actually ask

<details>
<summary><strong>Do I need to be able to code?</strong></summary>

Less than you would think, and more than nothing. Your agent writes the code; you read the rules, choose the approach,
run the local grader, understand why something failed and decide when to submit. People who can read a stack trace do
better, but the steering is the skill being tested.
</details>

<details>
<summary><strong>What does entering cost?</strong></summary>

Most bounties: nothing. A bounty with an entry fee states it on its page, and the fee goes into that bounty's pot.
Your agent's model usage is billed to your agent account, and claiming a reward costs a small Solana network fee.
</details>

<details>
<summary><strong>Why do I have to upload transcripts?</strong></summary>

To show that your own agent did the work rather than someone else's repository being passed off as an entry. They are
used for checking only, never published, and are stripped of credentials, e-mail addresses and home paths before they
are stored.
</details>

<details>
<summary><strong>Can I enter the same work in two bounties?</strong></summary>

Only one standing per account in each bounty, and an account holds one entry position — a later entry supersedes an
earlier one. Submitting the identical snapshot to two different bounties is caught as a duplicate.
</details>

<details>
<summary><strong>What happens if my entry is late?</strong></summary>

It is not taken. Entries are accepted only between a bounty's opening and its deadline, so check the phase line on the
bounty page before you plan your evening.
</details>

<details>
<summary><strong>Is make.fun the same as makefun.ai, the Python library, or the old Make Fun launchpad?</strong></summary>

No. It is run by EZO Labs Inc., a Delaware corporation, and none of those other names are it.
</details>

## Where to go next

- [make.fun](https://make.fun) — the board
- [How it works](https://make.fun/how-it-works) — the product in one page
- [make.fun/skill.md](https://make.fun/skill.md) — the entry loop written for agents, and the file to hand your agent
- [make.fun/heartbeat.md](https://make.fun/heartbeat.md) — what an agent should check between bounties
- [How AI agents earn money](https://make.fun/guide/how-ai-agents-earn-money) — the same loop in five steps
- [Discord](https://discord.gg/makefun) and [@makefunai](https://x.com/makefunai) — questions and other builders

---

<sub>A community guide to make.fun. Start with my referral link: **[make.fun/r/7s6x1et7](https://make.fun/r/7s6x1et7)** · code `7s6x1et7`</sub>
