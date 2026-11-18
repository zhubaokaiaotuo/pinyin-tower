# Pin Hao Bing

**Three Kingdoms: Battle of Chinese Characters**

[简体中文](README.md) | **English**

A water-ink spelling duel set in the Three Kingdoms. You stand at a gate. The enemy sends Chinese characters at you, and the only way to hold the line is to read them.

**Play in your browser:** https://zhubaokaiaotuo.github.io/pinyin-tower/

One HTML file, Canvas 2D, no dependencies, no network calls, no account. Progress is saved in your own browser.

> The interface is in Chinese, because this game was first built for Chinese six- and seven-year-olds learning pinyin. The characters and pinyin painted on the tablets are the lesson itself. An English interface is on the roadmap.

## A duel, in five seconds

1. A wooden tablet slides in from the right, carrying one Chinese character and its pinyin.
2. Tap two letter tiles to build the syllable (`zh` + `i` → `zhi`). Three-part syllables use a single combined tile (`j` + `ian` → `jian`), so you cannot take a wrong turn halfway.
3. Only the tones that genuinely exist for that syllable are offered. Pick the right one.
4. Pick the one character that matches among three or four that share the same sound.
5. Get it right and a flame leaves your hand and burns the enemy general. Get it wrong and the tablet keeps walking until it hits your wall.

It looks like a defense game. It is really a reading drill that happens to have stakes.

## Three doors, one ladder

| Door | For | Rules |
|---|---|---|
| **First Lessons** (蒙学) | Absolute beginners | Tablets move slowly, no clock, a wrong answer costs only time, every cleared level gives a heart back |
| **Provincial Exam** (会试) | Players who want a race | Clock on, opponent pace tuned to your own reading speed, three straight losses and the next round eases off |
| **Palace Exam** (殿试) | The hard line | No healing, no mercy, every run starts at level one, fastest tablet interval pinned to the edge of human reaction |

## From private to general

Promotion every twenty levels, and the drawing actually changes: headband, armor plates, helmet, helmet spike, pheasant plumes. No new sprite sheets, just equipment layered onto one skeleton.

| Level | Rank | What changes on screen |
|---|---|---|
| 1–19 | private | A wooden stick, nothing else |
| 20 | squad leader | Cloth tunic, headband ribbons, a curved blade |
| 40 | centurion | Grey armor with plate rows, iron helmet, that general's own weapon |
| 60 | chiliarch | Gold armor, two rows of plates, helmet spike |
| 80 | general | Gold armor, gold breastplate mirror, twin pheasant plumes |

## Two characters make a commander, four make a Great General

| You spell | Unit | Damage (First Lessons / Exam modes) |
|---|---|---|
| one character | soldier | 1 grid / 3 points |
| a two-character word (白云 white cloud) | battalion commander | 2 grids / 5 points |
| a four-character idiom (一心一意 wholehearted) | Great General | 3 grids, one hit / 15 points, one grid |

The idioms are not filler. They are the ones Chinese children grow up hearing: waiting by a stump for a hare to run into it, drawing legs on a snake you already finished, mending the fold after the sheep is lost.

## Why the tones matter

Chinese gives you *shi* with four tones, and they are four different words: **诗** poem, **十** ten, **使** to make, **是** to be. Same letters. Four words. The tone decides which one you meant, and the game will not let you slide past that. You feel the difference in your fingers long before you can explain it.

## What is in the box

| | Count |
|---|---|
| Everyday characters | 161, drawn from numbers, weather, family, animals, school, food |
| Two-character words | 187 |
| Four-character idioms | 60 |
| Three Kingdoms generals | 20, from four factions (Shu, Wei, Wu, Dong), each with the weapon history gave him |
| Difficulty modes | 3 |
| Military ranks | 5, one every 20 levels |

You will not finish this game fluent. You will finish it able to sound out a sign, recognize a character you have never seen, and hear four tones as four different things. That is the doorway; the rest of the language is on the other side of it.

## Design notes

- **One skeleton, layered equipment.** Ranks are drawn on top of the same simple ink figure rather than swapped for new art, in the flat-fill, single-outline style of 1980s Shanghai Animation Film Studio.
- **Each mode keeps its own records.** Best score, streak, title and learned characters never mix between First Lessons, Provincial Exam and Palace Exam.
- **Progress is permanent in the first two doors.** Leave at level 19, come back at level 19. A half-finished run is also saved, with hearts and streak intact. Palace Exam deliberately always starts at level one.
- **The opponent is tuned to you.** The game measures your own spelling pace and matches the enemy to it, so a slow reader gets a slow enemy rather than a wall.
- **The combined medial-final tile** keeps three-part syllables in one piece (`ian`, `uan`, `iao`), matching how Chinese textbooks present them.
- **The character set climbs from everyday to uncommon**, graded against the standard primary-school writing lists. No invented pronunciations.
- Everything on screen is drawn in code: tablets, character grids, backdrop, sound effects. No image or audio files.

## Tech

- Single HTML file, Canvas 2D, zero external dependencies
- Progress lives in `localStorage` only; nothing is uploaded, nothing is collected
- Sound is synthesized at runtime with the Web Audio API

## A note on the text

A small practice game made at home, shared for learning. The character set is compiled from the standard primary-school Chinese writing lists; corrections on readings and tones are welcome.
