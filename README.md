# zyxworks.github.io

### The open source index for [ZyxWorks](https://zyxworks.com).

One page, listing the tools the studio built for its own work and gave away.
Live at **[zyxworks.github.io](https://zyxworks.github.io/)**.

![One file](https://img.shields.io/badge/files-1%20html%20%2B%203%20fonts-111111)
![No build step](https://img.shields.io/badge/build%20step-none-666666)
![No dependencies](https://img.shields.io/badge/dependencies-0-666666)
![No external requests](https://img.shields.io/badge/external%20requests-0-666666)

## What is listed here

| | |
|---|---|
| **[MurmurFlow](https://zyxworks.github.io/murmurflow/)** | Press-to-talk dictation that runs on your own machine. Hold a key, say it, let go, and the words land at your cursor in any app. macOS and Windows. [Source](https://github.com/ZyxWorks/murmurflow) |
| **[Agent Office](https://zyxworks.github.io/agent-office/)** | A workspace for your coding agents, each in its own git worktree. You see at a glance which one waits for you. macOS and Linux. [Source](https://github.com/ZyxWorks/agent-office) |

Both came out of the work on [Zyx](https://zyxworks.com).
Each one keeps its own product page in its own repo under `docs/`, so a tool and
the page selling it ship together and can never drift apart. This repo owns the
index, nothing else. It used to own the host's `robots.txt` as well, because it
used to serve the host root; see the note below for what the repo rename changed.

## How it is built

`index.html` plus three self-hosted `woff2` files (Atkinson Hyperlegible Next and Mono, OFL,
licences beside them). That is the whole site:
no build step, no framework, no package manager, no Google Fonts request, nothing
to run before deploying and nothing that can rot between deploys. GitHub Pages
serves the repo root on every push to `main`.

The same rule holds on the two product pages, and it is the same promise the
products themselves make: a page selling a tool that phones home to nobody should
not phone home either.

Design decisions live in comments inside `index.html`, next to the code they
explain: where the signal yellow shows (the cube mark and the shadow under a card you point at) and where it does not, how the language switch keeps
both copies in step, why Zyx comes after the tools.

## A note on the robots policy

The site is deliberately not indexed yet, and both halves of that are on purpose:

- `robots.txt` lets **Googlebot and Bingbot crawl**. Blocking a crawler cannot
  remove a URL from an index, it only freezes whatever is already in there.
- the `noindex` meta tag in the HTML is what actually removes the page, and a
  crawler has to be let in to read it.
- everyone else, AI crawlers included, is disallowed on all paths.

Lift this once there is a proper Impressum. **Any new page in this repo needs the
same two tags**, or it becomes the one indexed page here.

**This file is back at the host root.** A user site has to be the repo named
`<owner>.github.io`, and under the personal account this repo was a project page
whose `robots.txt` the host never read. Owned by the **ZyxWorks** organization it
is that organization's user site, so `zyxworks.github.io/robots.txt` is served and
the "everyone else, stay out" rule covers the host and its sibling project pages
again (`/murmurflow`, `/agent-office`).

## Where this comes from

**[ZyxWorks](https://zyxworks.com)** makes Zyx. These are the things we built for
ourselves and gave away.

**Tools:** [MurmurFlow](https://zyxworks.github.io/murmurflow/) ·
[Agent Office](https://zyxworks.github.io/agent-office/)

**ZyxWorks:** [Zyx, in private beta](https://zyxworks.com) ·
[GitHub](https://github.com/ZyxWorks)

**Legal:** [imprint and privacy](https://zyxworks.com/legal/)
