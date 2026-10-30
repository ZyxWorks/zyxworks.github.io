# zyxworks.github.io

### The org page of [ZyxWorks](https://github.com/ZyxWorks), the engineering practice that builds Zyx and the open tools.

One page: the ZyxWorks mark, one line about the studio, and three cards for what we make.
Live at **[zyxworks.github.io](https://zyxworks.github.io/)**.

![Few files](https://img.shields.io/badge/files-1%20html%20%2B%20the%20ui%20copy-111111)
![No build step](https://img.shields.io/badge/build%20step-none-555555)
![No dependencies](https://img.shields.io/badge/dependencies-0-555555)
![No external requests](https://img.shields.io/badge/external%20requests-0-555555)

## What is on it

| | |
|---|---|
| **[Zyx](https://zyx.works/en/)** | Our product. Ask your company. On your own server. Answers from your company's own mail, files and apps, with the source. Every risky change waits for a person. Private beta, not open source. |
| **[MurmurFlow](https://zyxworks.github.io/murmurflow/)** | Dictation that runs on your own machine. Tap a key twice, speak, tap again, and the words land at your cursor. macOS and Windows. Free, open source. [Source](https://github.com/ZyxWorks/murmurflow) |
| **[Agent Office](https://zyxworks.github.io/agent-office/)** | A workspace for your coding agents, each in its own git worktree. You see which one waits for you. macOS and Linux. Free, open source. [Source](https://github.com/ZyxWorks/agent-office) |

Each tool keeps its own product page in its own repo under `docs/`, so a tool and its page ship together. This repo owns the org page, the host's favicon and the host's `robots.txt`.

## How it is built

`index.html` and `ui/`, a copy of the ZyxWorks UI library `@zyxworks/ui` 1.1: its tokens, its parts as plain CSS, the axis marks and the self-hosted Geist and Geist Mono faces (SIL Open Font License, licence texts beside them in `ui/fonts/`). No build step, no framework, no package manager, no font CDN. GitHub Pages serves the repo root on every push to `main`.

The look is the minimal ZyxWorks look, the same parts and tokens as the Zyx app: black, white and greys, 1 px lines, Geist at 400 and 500, the axis mark as the one bold thing. Light only.

The look comes from the library, never from this repo. `ui/` is written by the ship script in the library repo; never edit it by hand:

```sh
npm run ship -- <this repo> --static ui
```

The ship script adds and overwrites files but never deletes them, so files that an older version shipped and the new one does not must be removed by hand.

`index.html` keeps only what belongs to this page: its layout, the language switch, and the hero mark size, which the library does not have yet (marked `zyx-ui-allow-block` with the reason). Every colour, edge, size and time reads a `var(--z-*)` token.

English and German: both copies are in the markup, `<html lang>` decides which one shows. `?lang=de` or the EN/DE links switch it, and the choice is remembered. Without JavaScript the page is complete in English.

`favicon.svg` and `favicon.ico` are the library's own files (`ui/brand/`, 1.1), copied to the host root so the sibling pages get the axis too when they set no icon of their own.

## Check before a PR

There is no CI. Run these from this repo, with the library repo checked out beside it:

```sh
node ../zyxworks-ui/bin/zyx-ui.mjs lint index.html                     # tokens only, no class from before 1.0
node ../zyxworks-ui/bin/zyx-ui.mjs check . --static ui --expect 1.1.0  # the copy is 1.1
```

Then look at the page in a browser at 1440, 1024, 390 and 320 px, in English and German (`?lang=de`): no side scroll, the keyboard reaches every link with a visible focus ring, and it reads complete with JavaScript off.

## A note on the robots policy

The site is deliberately not indexed, and both halves of that are on purpose:

- `robots.txt` lets **Googlebot and Bingbot crawl**. Blocking a crawler cannot remove a URL from an index, it only freezes whatever is already in there.
- the `noindex` meta tag in the HTML is what actually removes the page, and a crawler has to be let in to read it.
- everyone else, AI crawlers included, is disallowed on all paths.

**Any new page in this repo needs the same two tags**, or it becomes the one indexed page here.

**This file is at the host root.** This repo is the organization's user site, so `zyxworks.github.io/robots.txt` is served and the "everyone else, stay out" rule covers the host and its sibling project pages too (`/murmurflow`, `/agent-office`).

## Links

**Zyx, our product:** [zyx.works](https://zyx.works/en/) · **ZyxWorks:** [GitHub](https://github.com/ZyxWorks)

Made by ZyxWorks.

**Legal:** [Imprint](https://zyx.works/en/legal/#imprint) · [Privacy](https://zyx.works/en/legal/#privacy)
