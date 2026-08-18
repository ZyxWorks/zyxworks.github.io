# hannesreinsch.github.io

### The open source index for [exwyezed](https://runzyx.xyz).

One page, listing the tools the studio built for its own work and gave away.
Live at **[hannesreinsch.github.io](https://hannesreinsch.github.io/)**.

![One file](https://img.shields.io/badge/files-1%20html%20%2B%203%20fonts-c9903f)
![No build step](https://img.shields.io/badge/build%20step-none-6a6c77)
![No dependencies](https://img.shields.io/badge/dependencies-0-6a6c77)
![No external requests](https://img.shields.io/badge/external%20requests-0-6a6c77)

## What is listed here

| | |
|---|---|
| **[MurmurFlow](https://hannesreinsch.github.io/murmurflow/)** | Press-to-talk dictation that runs on your own machine. Hold a key, say it, let go, and the words land at your cursor in any app. macOS and Windows. [Source](https://github.com/hannesreinsch/murmurflow) |
| **[Agent Office](https://hannesreinsch.github.io/agent-office/)** | Four coding agents in one tmux window, each in its own git worktree. The one that has stopped and is waiting on you says so on its border. [Source](https://github.com/hannesreinsch/agent-office) |

Both came out of [Zyx](https://runzyx.xyz#zyx), the runtime the studio runs on.
Each one keeps its own product page in its own repo under `docs/`, so a tool and
the page selling it ship together and can never drift apart. This repo owns the
index and the host's `robots.txt`, nothing else.

## How it is built

`index.html` plus three self-hosted `woff2` files. That is the whole site: 54 kB,
no build step, no framework, no package manager, no Google Fonts request, nothing
to run before deploying and nothing that can rot between deploys. GitHub Pages
serves the repo root on every push to `main`.

The same rule holds on the two product pages, and it is the same promise the
products themselves make: a page selling a tool that phones home to nobody should
not phone home either.

Design decisions live in comments inside `index.html`, next to the code they
explain: why the site is dark only, why the backdrop field has a separate narrow
placement for phones, why it is served from a personal account rather than an
organisation.

## A note on the robots policy

The site is deliberately not indexed yet, and both halves of that are on purpose:

- `robots.txt` lets **Googlebot and Bingbot crawl**. Blocking a crawler cannot
  remove a URL from an index, it only freezes whatever is already in there.
- the `noindex` meta tag in the HTML is what actually removes the page, and a
  crawler has to be let in to read it.
- everyone else, AI crawlers included, is disallowed on all paths.

Lift this once there is a proper Impressum. **Any new page in this repo needs the
same two tags**, or it becomes the one indexed page on the host.

## Where this comes from

**[exwyezed](https://runzyx.xyz)** is a product studio and forward deployed
engineering practice. These are the things we built for ourselves and gave away.

**Tools:** [MurmurFlow](https://hannesreinsch.github.io/murmurflow/) ·
[Agent Office](https://hannesreinsch.github.io/agent-office/)

**Studio:** [what we do for companies](https://runzyx.xyz) ·
[Zyx](https://runzyx.xyz#zyx) ·
[working with us](https://runzyx.xyz#fde) ·
[GitHub](https://github.com/hannesreinsch)

**Legal:** [imprint](https://runzyx.xyz/legal#imprint) ·
[privacy](https://runzyx.xyz/legal#privacy)
