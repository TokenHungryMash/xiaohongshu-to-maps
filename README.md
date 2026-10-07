# Xiaohongshu to Google Maps

Turn your saved Xiaohongshu (RED) travel posts into a native Google Maps list, with deduplicated places and useful notes.

**Version: 2.3** · [中文执行说明](SKILL.md)

## Overview

This AI agent skill bridges travel inspiration and a map you can actually use. Xiaohongshu's Diandian assistant reads the available post text, image text, and video transcripts. Your executing assistant extracts recommended places, resolves map matches, and saves them to a Google Maps list with practical notes.

The workflow prioritizes a usable first list: save clearly identified places, verify that the list and notes persisted, and explain ambiguous branches or unreadable posts together at delivery. You can then choose how to handle the remaining candidates without restarting the import.

## What it does

- Reads a selected collection or a limited trial batch.
- Extracts restaurants, shops, attractions, and other explicitly recommended places.
- Merges duplicate mentions while keeping distinct branches separate.
- Matches places using names, city, area, and branch clues.
- Adds useful notes such as recommended dishes, shopping highlights, and author tips, followed by the source post title.
- Creates private lists by default and preserves existing list sharing settings and notes.
- Keeps lightweight progress records so interrupted imports can resume in the same list.
- Reports reading gaps and uncertain matches with concrete reasons and available candidates.

## Requirements

Use an assistant environment that supports local skills and browser interaction. You need access to Xiaohongshu, its Diandian reading workflow, and Google Maps, and may need to complete sign-in or account verification yourself.

This repository contains instructions and reference templates. It does not include a standalone scraper, a Google Maps API integration, or a background synchronization service. Available reading capabilities depend on the websites and assistant environment. The main skill and its reference templates are written in Chinese; this README provides an English introduction.

## Installation

Clone the repository into your Codex skills directory:

```bash
git clone https://github.com/TokenHungryMash/xiaohongshu-to-maps.git ~/.codex/skills/xiaohongshu-to-maps
```

On Windows PowerShell:

```powershell
git clone https://github.com/TokenHungryMash/xiaohongshu-to-maps.git "$env:USERPROFILE\.codex\skills\xiaohongshu-to-maps"
```

If that directory already exists, update your existing checkout or copy the repository files into the existing skill directory. Reload your assistant session if needed to discover the skill.

## Usage

Invoke the skill and specify your collection and destination:

```text
Use $xiaohongshu-to-maps to import my Tokyo food collection from Xiaohongshu
into a private Google Maps list called "Tokyo | Saved Food Spots".
Add recommended dishes and practical tips to each place's note.
Finish the clearly matched places first, then show me any uncertain branches.
```

For a trial run:

```text
Use $xiaohongshu-to-maps to process the first 10 posts in my saved collection.
```

To resume:

```text
Use $xiaohongshu-to-maps to continue the previous import in the same Google Maps
list. Use the saved progress record and only add unfinished places and notes.
```

The assistant checks sign-in, reads the requested posts, extracts and matches places, saves clear matches with notes, and performs one consolidated persistence check. The final response includes the list link, saved count, and important unresolved items.

## Matching and source handling

A brand name alone may not identify the author's intended branch. Ambiguous places stay pending until there is sufficient evidence or you choose a candidate. Candidate counts describe the branches found during that run, not necessarily every branch of a brand.

Notes use the source post's information. Historical prices, promotions, and opening hours are not presented as current facts. Source post titles are included by default; Xiaohongshu links are added only when requested and already available. External recommendations are not added merely to increase the list size.

## Repository contents

| Path | Purpose |
|---|---|
| `SKILL.md` | Main workflow and completion criteria |
| `agents/openai.yaml` | Skill display metadata and default prompt |
| `assets/icon.svg` | Skill icon |
| `references/diandian-prompts.md` | Reading templates and batch selection |
| `references/place-data.md` | Lightweight progress and recovery records |
| `references/first-list-delivery.md` | Example delivery with uncertain matches |
| `references/capability-observations.md` | Limited reading observations and their caveats |

## Privacy

New Google Maps lists are private by default. Existing sharing settings are retained. Personal travel collections, account credentials, and actual import progress records do not belong in this repository.
