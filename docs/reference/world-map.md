# World Map

The world map of Medokh's World: its size, coordinate frame, hex geometry, regions, terrain, and features.

Related references: [movement](movement.md), [portals](portals.md), [races](races.md).

## Dimensions

| Property         | Value                              |
|------------------|------------------------------------|
| Map size         | 100 columns × 100 rows of hexes    |
| Regions          | 100, in a 10 × 10 grid             |
| Region size      | 10 columns × 10 rows of hexes      |
| Hex orientation  | Flat top                           |
| Scale            | 1 hex = 10 leagues                 |

Every region is exactly 10 × 10 hexes.

## Coordinate frame

Locations use global coordinates, written `column,row`.

| Property | Value                                    |
|----------|------------------------------------------|
| Origin   | `1,1` is the upper-left (north-west) hex |
| Columns  | 1–100, increasing to the east            |
| Rows     | 1–100, increasing to the south           |
| North    | Top of the map                           |

There is no region-relative address.
A player works out the region from the global coordinates (see [Regions](#regions)).
The original game's `RX,RY,HX,HY` form is not supported.

### Column offset

Columns alternate in height:

| Column             | Position                |
|--------------------|-------------------------|
| Even (0, 2, 4, …)  | Shifted up half a hex   |
| Odd (1, 3, 5, …)   | Pushed down half a hex  |

Hex `1,1` is in a pushed-down column; its neighbor `2,1` is shifted up.
Regions are an even number of columns wide, so every region begins on an odd column and all regions share the same internal shape.

### Worldographer and hexg

The map is exported to Worldographer.
Hex math uses the `github.com/maloquacious/hexg` package.

Game coordinates are Worldographer coordinates, with no translation: hex `c,r` in the game is hex `c,r` in Worldographer.
The matching hexg layout is `OddQ` (flat top, vertical columns, odd columns shoved down).

## Adjacency

A hex has six neighbors.
The direction numbers are the ones used by army movement and siege orders.

| No. | Direction  | From an odd column | From an even column |
|-----|------------|--------------------|---------------------|
| 1   | North      | `c, r-1`           | `c, r-1`            |
| 2   | North-east | `c+1, r`           | `c+1, r-1`          |
| 3   | South-east | `c+1, r+1`         | `c+1, r`            |
| 4   | South      | `c, r+1`           | `c, r+1`            |
| 5   | South-west | `c-1, r+1`         | `c-1, r`            |
| 6   | North-west | `c-1, r`           | `c-1, r-1`          |

There is no due east or due west.

## Map edge

The map is bounded on all four sides by the World Wall.
No unit may leave the map across any edge.

The World Wall is not a terrain type and is not part of the game map.
In the Worldographer export it fills a one-hex border around the game map, left blank:

| Edge  | Worldographer tiles |
|-------|---------------------|
| North | Row 0               |
| West  | Column 0            |
| South | Row 101             |
| East  | Column 101          |

The exported map is therefore 102 × 102 tiles, `0,0` to `101,101`.

## Regions

A region is addressed `column,row` on the 10 × 10 region grid, with `1,1` in the upper left.

For a hex at `c,r`:

| Quantity      | Formula                    |
|---------------|----------------------------|
| Region column | `(c - 1) / 10 + 1` (integer division) |
| Region row    | `(r - 1) / 10 + 1` (integer division) |

For region `RC,RR`, hex columns run from `(RC-1)*10 + 1` to `RC*10` and hex rows from `(RR-1)*10 + 1` to `RR*10`.

Region names, from `medocs/docs/manual/tables/map-areas.md`, renumbered into this frame.
Names are normalized as follows:

- No name has a leading "The".
- "Khar", not "Skar" (the originals use both).
- "Savannah", not "Savannak".

| Region | Name | Hex columns | Hex rows |
|--------|------|-------------|----------|
| 1,1 | Chasm of the Undead | 1–10 | 1–10 |
| 2,1 | Valley of the Damned | 11–20 | 1–10 |
| 3,1 | Great Plains | 21–30 | 1–10 |
| 4,1 | Forgotten Wastes | 31–40 | 1–10 |
| 5,1 | Great Northern Forest | 41–50 | 1–10 |
| 6,1 | Forbidden Land | 51–60 | 1–10 |
| 7,1 | Northern Peaks | 61–70 | 1–10 |
| 8,1 | Northern Plains of the Farmer | 71–80 | 1–10 |
| 9,1 | Northern Highreaches | 81–90 | 1–10 |
| 10,1 | Great Abyss | 91–100 | 1–10 |
| 1,2 | Sacred Woods | 1–10 | 11–20 |
| 2,2 | High Lands of Balgor | 11–20 | 11–20 |
| 3,2 | Northern Ironrock Mountains | 21–30 | 11–20 |
| 4,2 | Land of the Slayer | 31–40 | 11–20 |
| 5,2 | Dragon's Eye | 41–50 | 11–20 |
| 6,2 | Land of the Fenrith | 51–60 | 11–20 |
| 7,2 | Whispering Dale | 61–70 | 11–20 |
| 8,2 | Borderlands | 71–80 | 11–20 |
| 9,2 | Balziboah Savannah | 81–90 | 11–20 |
| 10,2 | Valley of the Kings | 91–100 | 11–20 |
| 1,3 | Oakendale Valley | 1–10 | 21–30 |
| 2,3 | Badlands | 11–20 | 21–30 |
| 3,3 | Ironrock Mountains | 21–30 | 21–30 |
| 4,3 | Eastern Lake Esgaroth | 31–40 | 21–30 |
| 5,3 | Hills of Malakai | 41–50 | 21–30 |
| 6,3 | Grimdale Downs | 51–60 | 21–30 |
| 7,3 | Sanganoori Wastes | 61–70 | 21–30 |
| 8,3 | Lowlands of the Bachurai | 71–80 | 21–30 |
| 9,3 | Woodlands of Greenholm | 81–90 | 21–30 |
| 10,3 | Deadrock Flatlands | 91–100 | 21–30 |
| 1,4 | Valley of the Ancients | 1–10 | 31–40 |
| 2,4 | Kalihari Steppes | 11–20 | 31–40 |
| 3,4 | Lowlands of Crete | 21–30 | 31–40 |
| 4,4 | Riverrun Forests | 31–40 | 31–40 |
| 5,4 | Malakai's Triumph | 41–50 | 31–40 |
| 6,4 | Mountains of the Moon | 51–60 | 31–40 |
| 7,4 | Reaper's Dale | 61–70 | 31–40 |
| 8,4 | Kyocerian Ridge | 71–80 | 31–40 |
| 9,4 | Vale of the Lost River | 81–90 | 31–40 |
| 10,4 | Howling Valley | 91–100 | 31–40 |
| 1,5 | Great Western Forest | 1–10 | 41–50 |
| 2,5 | Northern Redrun Downs | 11–20 | 41–50 |
| 3,5 | Grasslands of Angar | 21–30 | 41–50 |
| 4,5 | Eastern Angar | 31–40 | 41–50 |
| 5,5 | Devil's Eye | 41–50 | 41–50 |
| 6,5 | Devil's Horn | 51–60 | 41–50 |
| 7,5 | Goldenmist Vale | 61–70 | 41–50 |
| 8,5 | Elder Forest | 71–80 | 41–50 |
| 9,5 | Warrior Plains | 81–90 | 41–50 |
| 10,5 | Highpeak Range | 91–100 | 41–50 |
| 1,6 | Great Divide | 1–10 | 51–60 |
| 2,6 | Redrun Downs | 11–20 | 51–60 |
| 3,6 | Down's Edge | 21–30 | 51–60 |
| 4,6 | Barrens of Mount Crimson | 31–40 | 51–60 |
| 5,6 | Mouth of Hell | 41–50 | 51–60 |
| 6,6 | Devil's Fang | 51–60 | 51–60 |
| 7,6 | Northern Karigar | 61–70 | 51–60 |
| 8,6 | Gorgonzola Highlands | 71–80 | 51–60 |
| 9,6 | Kalibari Lakelands | 81–90 | 51–60 |
| 10,6 | Lowlands of Logal | 91–100 | 51–60 |
| 1,7 | Forest of Elderdale | 1–10 | 61–70 |
| 2,7 | Dale of Mystics | 11–20 | 61–70 |
| 3,7 | High Ridge Peaks | 21–30 | 61–70 |
| 4,7 | Land of the Dragonmen | 31–40 | 61–70 |
| 5,7 | Hills of Baligor | 41–50 | 61–70 |
| 6,7 | Wilderness | 51–60 | 61–70 |
| 7,7 | Land of the Karigar | 61–70 | 61–70 |
| 8,7 | Battleground Valley | 71–80 | 61–70 |
| 9,7 | Riverlands of the Haruchai | 81–90 | 61–70 |
| 10,7 | Great Salt Flats | 91–100 | 61–70 |
| 1,8 | Ravenhead Peaks | 1–10 | 71–80 |
| 2,8 | Northern Plains of Khar | 11–20 | 71–80 |
| 3,8 | Valley of the Blue Lakes | 21–30 | 71–80 |
| 4,8 | Silverdale Forestlands | 31–40 | 71–80 |
| 5,8 | Hills of Marne the Mighty | 41–50 | 71–80 |
| 6,8 | High Rock Mountains | 51–60 | 71–80 |
| 7,8 | Sacred Sea | 61–70 | 71–80 |
| 8,8 | Barrenrock Downs | 71–80 | 71–80 |
| 9,8 | Creeping Desert | 81–90 | 71–80 |
| 10,8 | Wastelands of Khar | 91–100 | 71–80 |
| 1,9 | Western Plains of Khar | 1–10 | 81–90 |
| 2,9 | Plains of Khar | 11–20 | 81–90 |
| 3,9 | Land of the Faruchai | 21–30 | 81–90 |
| 4,9 | Silverdale | 31–40 | 81–90 |
| 5,9 | Sea of Grass | 41–50 | 81–90 |
| 6,9 | Vale of Lake Galgorath | 51–60 | 81–90 |
| 7,9 | Valley of Ulcancan | 61–70 | 81–90 |
| 8,9 | Golden Savannah | 71–80 | 81–90 |
| 9,9 | Razorteeth Mountains | 81–90 | 81–90 |
| 10,9 | Southern Wastelands of Khar | 91–100 | 81–90 |
| 1,10 | Death's Gorge | 1–10 | 91–100 |
| 2,10 | Southern Plains of Khar | 11–20 | 91–100 |
| 3,10 | Valley of the Giants | 21–30 | 91–100 |
| 4,10 | Darkmoor Ridges | 31–40 | 91–100 |
| 5,10 | Eastern Darkmoor | 41–50 | 91–100 |
| 6,10 | Great Barrens | 51–60 | 91–100 |
| 7,10 | Gareck's Desolation | 61–70 | 91–100 |
| 8,10 | Hills of Belcanun the Bold | 71–80 | 91–100 |
| 9,10 | Valley of the Four Winds | 81–90 | 91–100 |
| 10,10 | Black Lagoon | 91–100 | 91–100 |

### Starting regions

The home region of each player tribe, from `medocs/docs/manual/tables/map-areas.md`, renumbered into this frame.
The original marks the four centre regions (5,5), (6,5), (5,6), and (6,6) in black; no tribe starts there.

| Tribe | Race | Region | Region name |
|-------|------|--------|-------------|
| 1 | Humans | 3,1 | Great Plains |
| 2 | Elves | 5,1 | Great Northern Forest |
| 3 | Dwarves | 7,1 | Northern Peaks |
| 4 | Orcs | 2,2 | High Lands of Balgor |
| 5 | Kobolds | 4,2 | Land of the Slayer |
| 6 | Halflings | 6,2 | Land of the Fenrith |
| 7 | Humans | 8,2 | Borderlands |
| 8 | Elves | 1,3 | Oakendale Valley |
| 9 | Dwarves | 3,3 | Ironrock Mountains |
| 10 | Orcs | 5,3 | Hills of Malakai |
| 11 | Kobolds | 7,3 | Sanganoori Wastes |
| 12 | Halflings | 9,3 | Woodlands of Greenholm |
| 13 | Humans | 2,4 | Kalihari Steppes |
| 14 | Elves | 4,4 | Riverrun Forests |
| 15 | Dwarves | 6,4 | Mountains of the Moon |
| 16 | Orcs | 8,4 | Kyocerian Ridge |
| 17 | Kobolds | 10,4 | Howling Valley |
| 18 | Halflings | 1,5 | Great Western Forest |
| 19 | Humans | 3,5 | Grasslands of Angar |
| 20 | Elves | 7,5 | Goldenmist Vale |
| 21 | Dwarves | 9,5 | Warrior Plains |
| 22 | Orcs | 2,6 | Redrun Downs |
| 23 | Kobolds | 4,6 | Barrens of Mount Crimson |
| 24 | Halflings | 8,6 | Gorgonzola Highlands |
| 25 | Humans | 10,6 | Lowlands of Logal |
| 26 | Elves | 1,7 | Forest of Elderdale |
| 27 | Dwarves | 3,7 | High Ridge Peaks |
| 28 | Orcs | 5,7 | Hills of Baligor |
| 29 | Kobolds | 7,7 | Land of the Karigar |
| 30 | Halflings | 9,7 | Riverlands of the Haruchai |
| 31 | Humans | 2,8 | Northern Plains of Khar |
| 32 | Elves | 4,8 | Silverdale Forestlands |
| 33 | Dwarves | 6,8 | High Rock Mountains |
| 34 | Orcs | 8,8 | Barrenrock Downs |
| 35 | Kobolds | 10,8 | Wastelands of Khar |
| 36 | Halflings | 3,9 | Land of the Faruchai |
| 37 | Humans | 5,9 | Sea of Grass |
| 38 | Elves | 7,9 | Valley of Ulcancan |
| 39 | Dwarves | 9,9 | Razorteeth Mountains |
| 40 | Orcs | 4,10 | Darkmoor Ridges |
| 41 | Kobolds | 6,10 | Great Barrens |
| 42 | Halflings | 8,10 | Hills of Belcanun the Bold |

## Terrain

Every hex has exactly one terrain type.

| Terrain        | Notes                                              |
|----------------|----------------------------------------------------|
| Plains         | Common terrain                                     |
| Forest         | Common terrain                                     |
| Mountains      | Common terrain                                     |
| Hills          | Common terrain                                     |
| Forested Hills | Common terrain                                     |
| Wastelands     | Common terrain                                     |
| Lake           | Water                                              |
| Sea            | Water                                              |
| Flooded        | Water                                              |
| Frozen Lake    | A lake frozen over during the Chaos Winter         |
| Frozen Sea     | A sea frozen over during the Chaos Winter          |
| Frozen Flooded | A flooded hex frozen over during the Chaos Winter  |

The original game numbers the six common terrain types in orders such as Global Upgrade:
1 Plains, 2 Forest, 3 Mountains, 4 Hills, 5 Forested Hills, 6 Wastelands (`medocs/docs/manual/orders/domestic.md`).

Movement cost by terrain and race is in [movement](movement.md) and [races](races.md).

## Features

A feature sits on a hex in addition to its terrain.
Features are not terrain types, and every hex with a feature still has a terrain type.

| Feature    | Notes                                                   |
|------------|---------------------------------------------------------|
| Volcano    | Lethal heat; see [movement](movement.md). Usually on Wastelands |
| Portal     | 13 exist; see [portals](portals.md)                     |
| Ruin       | An ancient ruin that can be explored                    |
| Settlement | A town, city, fort, shrine, gem mine, or wizard's tower |

In the Worldographer export, a volcano hex uses the Badlands terrain tile.
"Badlands" is only the Worldographer tile name; the game terrain is Wastelands.
(Badlands is also the name of region 2,3.)

## Converting original locations

The original documents give locations as a region `x,y` plus a hex `x,y` within it.
Both count from 1, so columns carry over directly.
Both count from the **bottom-left**, rows increasing upward (`medocs/docs/manual/campaign-world.md`).
This frame counts rows downward with north at the top, so rows are reversed.

For an original region `RX,RY` and hex `HX,HY`:

| Quantity      | Formula                              |
|---------------|--------------------------------------|
| Global column | `(RX - 1) * 10 + HX`                 |
| Global row    | `(10 - RY) * 10 + (11 - HY)`         |
| Region        | `RX, 11 - RY`                        |

Example: hex 9/5 in Mouth of Hell (original region 5,5) is global `49,56` in region `5,6`.

## Open questions

- No original data gives the terrain of individual hexes; the terrain map must be designed or generated.
