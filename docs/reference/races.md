# Races

The races of Medokh's World and their relationship to terrain.

The original Race Reference Cards, which held each race's movement costs and terrain preferences, are lost
(`medocs/docs/reconstructed/race-reference-cards.md`).
What follows is gathered from surviving documents.

## Race list

Tribe numbers are from `medocs/docs/manual/tables/tribes.md` and `medocs/docs/manual/diplomacy.md`.

### Player races

The 42 player tribes cycle through six races in tribe-number order.

| Race      | Player tribes                    | Independent tribe |
|-----------|----------------------------------|-------------------|
| Humans    | 1, 7, 13, 19, 25, 31, 37         | 51                |
| Elves     | 2, 8, 14, 20, 26, 32, 38         | 52                |
| Dwarves   | 3, 9, 15, 21, 27, 33, 39         | 53                |
| Orcs      | 4, 10, 16, 22, 28, 34, 40        | 54                |
| Kobolds   | 5, 11, 17, 23, 29, 35, 41        | 55                |
| Halflings | 6, 12, 18, 24, 30, 36, 42        | 56                |

Starting regions are in [world map: starting regions](world-map.md#starting-regions).

### Non-player races

| Race                 | Tribe |
|----------------------|-------|
| Malkahai             | 43    |
| Mazdrakians          | 44    |
| Centaurs             | 45    |
| Drow                 | 46    |
| Rock Trolls          | 47    |
| Ogres                | 48    |
| Minotaurs            | 49    |
| Dryads               | 50    |
| Babulska             | 57    |
| Curazck              | 58    |

### Blood Guard

The Blood Guard are not a race.
They are fanatical warrior-priest cults, one for each of the six Lesser Gods, whose members come from the various races (`medocs/docs/sheets/religeon.md`).
They gather at Shrines dedicated to their God when the Shrine's tribe has that God as its Creator; for example, Elven Blood Guard muster at Elven Shrines dedicated to Elvirius.

| Name              | Members                                                        |
|-------------------|----------------------------------------------------------------|
| Blood Guard       | Members of the various races, by cult                          |
| Chaos Blood Guard | Undead Mazdrakians (`medocs/docs/sheets/embracing-mazdrak.md`) |

The compendium's movement table lists Blood Guard as a row alongside the races.

## Terrain preferences

From the mercenary sheets (`medocs/docs/sheets/mercenaries-*.md`, `halfling-mercenaries.md`).
The sheets describe mercenary units; the same preferences apply to the tribal races.

| Race        | Prefers                    | Despises        |
|-------------|----------------------------|-----------------|
| Humans      | Plains, Wastelands         | Mountains       |
| Elves       | Forest, Forested Hills     | Wastelands      |
| Dwarves     | Mountains, Hills           | Forest          |
| Orcs        | Hills, Mountains           | Forest          |
| Kobolds     | Wastelands, Mountains      | Plains          |
| Halflings   | Forested Hills, Forest     | Mountains       |
| Centaurs    | Plains, Wastelands         | Mountains       |
| Drow        | Forest, Forested Hills     | Hills           |
| Dryads      | Forested Hills, Forest     | Wastelands      |
| Minotaurs   | Wastelands, Plains         | Forested Hills  |
| Ogres       | Hills, Mountains           | Forest          |
| Rock Trolls | Mountains, Hills           | Plains          |

The sheets' comparisons name the strongest tribal race in each common terrain.
Regions is the number of regions with that [default terrain](world-map.md#regions).

| Terrain        | Strongest tribal race | Regions |
|----------------|-----------------------|---------|
| Plains         | Humans                | 27      |
| Forest         | Elves                 | 13      |
| Mountains      | Dwarves               | 16      |
| Hills          | Orcs                  | 15      |
| Forested Hills | Halflings             | 7       |
| Wastelands     | Kobolds               | 18      |

## Movement costs

Movement points to enter one hex, by race and terrain.
All values are unknown.

| Race        | Plains | Forest | Mountains | Hills | Forested Hills | Wastelands | Desert | Lake | Sea | Flooded | Frozen Lake | Frozen Sea | Frozen Flooded |
|-------------|--------|--------|-----------|-------|----------------|------------|--------|------|-----|---------|-------------|------------|----------------|
| Humans      | ?      | ?      | ?         | ?     | ?              | ?          | ?      | ?    | ?   | ?       | 5           | 5          | ?              |
| Elves       | ?      | ?      | ?         | ?     | ?              | ?          | ?      | ?    | ?   | ?       | 5           | 5          | ?              |
| Dwarves     | ?      | ?      | ?         | ?     | ?              | ?          | ?      | ?    | ?   | ?       | 5           | 5          | ?              |
| Orcs        | ?      | ?      | ?         | ?     | ?              | ?          | ?      | ?    | ?   | ?       | 5           | 5          | ?              |
| Kobolds     | ?      | ?      | ?         | ?     | ?              | ?          | ?      | ?    | ?   | ?       | 5           | 5          | ?              |
| Halflings   | ?      | ?      | ?         | ?     | ?              | ?          | ?      | ?    | ?   | ?       | 5           | 5          | ?              |
| Centaurs    | ?      | ?      | ?         | ?     | ?              | ?          | ?      | ?    | ?   | ?       | 5           | 5          | ?              |
| Drow        | ?      | ?      | ?         | ?     | ?              | ?          | ?      | ?    | ?   | ?       | 5           | 5          | ?              |
| Dryads      | ?      | ?      | ?         | ?     | ?              | ?          | ?      | ?    | ?   | ?       | 5           | 5          | ?              |
| Minotaurs   | ?      | ?      | ?         | ?     | ?              | ?          | ?      | ?    | ?   | ?       | 5           | 5          | ?              |
| Ogres       | ?      | ?      | ?         | ?     | ?              | ?          | ?      | ?    | ?   | ?       | 5           | 5          | ?              |
| Rock Trolls | ?      | ?      | ?         | ?     | ?              | ?          | ?      | ?    | ?   | ?       | 5           | 5          | ?              |
| Mazdrakians | ?      | ?      | ?         | ?     | ?              | ?          | ?      | ?    | ?   | ?       | 5           | 5          | ?              |
| Blood Guard | ?      | ?      | ?         | ?     | ?              | ?          | ?      | ?    | ?   | ?       | 5           | 5          | ?              |
| Curazck     | ?      | ?      | ?         | ?     | ?              | ?          | ?      | ?    | ?   | ?       | 5           | 5          | ?              |
| Malkahai    | ?      | ?      | ?         | ?     | ?              | ?          | ?      | ?    | ?   | ?       | 5           | 5          | ?              |

Frozen lake and sea costs are from `medocs/docs/sheets/chaos-cometh.md`, which sets 5 points for every race.
It does not mention frozen flooded hexes.
The compendium says armies cannot enter lakes or seas.

### Proposed movement costs

**Reconstructed, not authoritative.**
This project wrote the table below to replace the unknown values above.
Only the frozen lake and sea costs and the closed water hexes come from the original documents.

Each race's costs follow its [terrain preferences](#terrain-preferences), taking the first-named preferred terrain as the race's best:

| Terrain for the race | Cost                                            |
|----------------------|-------------------------------------------------|
| Best                 | 3                                               |
| Second               | 4                                               |
| Neutral              | 5                                               |
| Despised             | 8                                               |
| Desert               | Wastelands cost + 1, plus 5 before Chaos Winter |

The values fit the clues in the original documents:

- Frozen water, at 5 for every race, slows the "quicker races" (`medocs/docs/sheets/chaos-cometh.md`); every race's best and second terrain cost less.
- Trackers halve costs to a minimum of 2 (see [movement: trackers](movement.md#trackers)), so the minimum applies on a race's best terrain.
- The compendium's example Forced March covers 8 hexes, about 3.75 points per hex.
- The planned 12-box turncard (`medocs/docs/sheets/army-movement.md`) is filled by a Forced March with a Tracker on best terrain.

Desert is harsh until Chaos Winter arrives (between turns 35 and 55, `medocs/docs/sheets/the-keys-of-power.md`).
From then on it costs 5 points less.

| Race        | Plains | Forest | Mountains | Hills | Forested Hills | Wastelands | Desert | Desert (Chaos Winter) | Lake | Sea | Flooded | Frozen Lake | Frozen Sea | Frozen Flooded |
|-------------|--------|--------|-----------|-------|----------------|------------|--------|-----------------------|------|-----|---------|-------------|------------|----------------|
| Humans      | 3      | 5      | 8         | 5     | 5              | 4          | 10     | 5                     | —    | —   | —       | 5           | 5          | 5              |
| Elves       | 5      | 3      | 5         | 5     | 4              | 8          | 14     | 9                     | —    | —   | —       | 5           | 5          | 5              |
| Dwarves     | 5      | 8      | 3         | 4     | 5              | 5          | 11     | 6                     | —    | —   | —       | 5           | 5          | 5              |
| Orcs        | 5      | 8      | 4         | 3     | 5              | 5          | 11     | 6                     | —    | —   | —       | 5           | 5          | 5              |
| Kobolds     | 8      | 5      | 4         | 5     | 5              | 3          | 9      | 4                     | —    | —   | —       | 5           | 5          | 5              |
| Halflings   | 5      | 4      | 8         | 5     | 3              | 5          | 11     | 6                     | —    | —   | —       | 5           | 5          | 5              |
| Centaurs    | 3      | 5      | 8         | 5     | 5              | 4          | 10     | 5                     | —    | —   | —       | 5           | 5          | 5              |
| Drow        | 5      | 3      | 5         | 8     | 4              | 5          | 11     | 6                     | —    | —   | —       | 5           | 5          | 5              |
| Dryads      | 5      | 4      | 5         | 5     | 3              | 8          | 14     | 9                     | —    | —   | —       | 5           | 5          | 5              |
| Minotaurs   | 4      | 5      | 5         | 5     | 8              | 3          | 9      | 4                     | —    | —   | —       | 5           | 5          | 5              |
| Ogres       | 5      | 8      | 4         | 3     | 5              | 5          | 11     | 6                     | —    | —   | —       | 5           | 5          | 5              |
| Rock Trolls | 8      | 5      | 3         | 4     | 5              | 5          | 11     | 6                     | —    | —   | —       | 5           | 5          | 5              |
| Mazdrakians | ?      | ?      | ?         | ?     | ?              | ?          | ?      | ?                     | —    | —   | —       | 5           | 5          | ?              |
| Curazck     | ?      | ?      | ?         | ?     | ?              | ?          | ?      | ?                     | —    | —   | —       | 5           | 5          | ?              |
| Malkahai    | ?      | ?      | ?         | ?     | ?              | ?          | ?      | ?                     | —    | —   | —       | 5           | 5          | ?              |

`—` means an army cannot enter the hex.

- Frozen Flooded hexes cost the same as frozen lakes and seas.
- Blood Guard have no row of their own: a Blood Guard unit uses the row of its members' race.
- Mazdrakians, Curazck, and Malkahai have no known terrain preferences, so their costs remain unknown.

## Open questions

- Movement costs for Mazdrakians, Curazck, and Malkahai.
- Whether an army of mixed races moves at the pace of its slowest troops; the mercenary sheets say mercenaries "rarely will … slow down any army they're attached to".
- Whether Babulska need movement costs; they are nomadic and have no armies in the documents.
