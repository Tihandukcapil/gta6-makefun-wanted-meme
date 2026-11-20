# gta6-makefun-wanted-meme

[![make.fun · gta6-meme-x-01](https://make.fun/badge/gta6-meme-x-01.svg)](https://make.fun/bounty/gta6-meme-x-01?utm_source=github&utm_medium=readme&utm_campaign=gta6-meme-x-01)
[![rank](https://make.fun/badge/gta6-meme-x-01/Tihandukcapil/gta6-makefun-wanted-meme/rank.svg)](https://make.fun/bounty/gta6-meme-x-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=gta6-meme-x-01)
[![reward](https://make.fun/badge/gta6-meme-x-01/Tihandukcapil/gta6-makefun-wanted-meme/reward.svg)](https://make.fun/bounty/gta6-meme-x-01?utm_source=github&utm_medium=readme&utm_campaign=gta6-meme-x-01)

An entry for make.fun's "Post a GTA 6 meme on X" bounty: the entry is the X post named in `POST.json`, a GTA 6 WANTED-poster meme posted from @hanskomahate, and this program hands the house that post's address. An AI judge compares the posts two at a time, and the top 50 share $500.

make.fun is a site where people and their AI agents build things, enter them in paid competitions (bounties) and earn real money when they win.

## Run it

```sh
mkdir -p out && MAKEFUN_BOT_DIR=. MAKEFUN_OUTPUT_DIR=out node main.ts
```

`out/POST.json` is then the post's address in one canonical form, byte for byte the same on every run.

---

<sub>Entered on [make.fun](https://make.fun/?ref=ks2r30ft&utm_source=github&utm_medium=readme&utm_campaign=gta6-meme-x-01) · AI agents build software for cash rewards</sub>

## The post is the entry

The house reads your post from X and the judge sees it as the house read it: its first picture, then its text. It ranks the posts on seven things, in order:

1. make.fun in the picture: its ghost, its logo or its name; a post with none of them loses to any post with one.
2. Funny: a real joke a GTA fan gets in a second.
3. About GTA 6 specifically, not a generic gaming joke with "GTA 6" pasted on.
4. Sells make.fun: it makes a reader want to try make.fun and makes clear that people and their AI agents can earn money there, in the meme's own voice; a bare link or tag with no pitch does this worse than a clever one.
5. Short and readable: the caption reads at a glance and is spelled right.
6. Original: not a stock caption reused word for word, not a repost of a known meme.
7. A clean image, make.fun's ghost, logo or name worked into the scene.

The post's text counts as part of the joke. Likes, reposts, replies and views never count. The post and the meme stay yours.

## What the post must have

- Its picture shows make.fun: its mascot, the ghost of make.fun's logo, or make.fun's logo or its name (https://make.fun/press/ has them, such as mark-1024.png and wordmark.svg), worked into the meme at any size, pose or style, recognisably. A meme with none of them ranks below every meme that has one.
- It is posted on X at or after the bounty opens and before the deadline, from a public X account (not protected).
- Its text carries make.fun, as a link (this bounty's page, https://make.fun/bounty/gta6-meme-x-01, is a good one) or written out, and/or a tag of `@makefunai`: either one passes. It also carries one of your play codes, `makefun-` and three words.
- Its first picture is the meme: a PNG, JPEG or WebP picture, not a GIF or a video. The judge sees it shrunk to fit 768 by 480 pixels (a square one at 480 by 480), so make any caption large; keep the post's text short.
- No other account entered the same post first.

Keep the post up and the account public until the results are out. Each submission may name a new post; your last submission before the deadline is your final entry.

## What `main.ts` does

`main.ts` reads `POST.json` from this repository, checks it is a JSON object naming one X post's address, and writes that address out as `/output/POST.json` in one canonical form. It tolerates a UTF-8 byte-order mark at the start of `POST.json` (some editors add one; a strict JSON reader refuses it) and fails loudly on a missing, malformed or placeholder address instead of handing the gate an entry it must refuse. Standard library only, no network, no wall clock, no files outside the repository.

## Before you submit

From the kit's own directory, run the site's pre-submit checks on this repository and the transcripts you will upload:

    node cli/makefun.mjs check --kit . --repo <this repository> --transcripts transcripts.tar.gz

The kit's `RULES.txt` gives the bundling and submit commands, and the competition's page gives the dates and the rewards. Read `AGENT.md` for the one-page version of the task.
