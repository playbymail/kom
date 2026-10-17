# Errata

Discrepancies and errors in the original documents (`medocs/docs/`), and how this project resolves them.

## Portal locations

**Sources:** the portal lists in nine sheets in `medocs/docs/sheets/`.

**Discrepancy:** `the-high-priest-of-medokh.md` places every portal at a different hex from the other eight sheets.
Twelve locations are one higher in both x and y; portal 7 is one higher in x only.
The 1998 Word original has the same values, so the difference is not a conversion error.

| Portal | Region                | Other sheets | High Priest |
|--------|-----------------------|--------------|-------------|
| 1      | Mouth of Hell         | 9/5          | 10/6        |
| 2      | Riverrun Forests      | 6/1          | 7/2         |
| 3      | Reaper's Dale         | 6/1          | 7/2         |
| 4      | Land of the Karigar   | 4/3          | 5/4         |
| 5      | Land of the Dragonmen | 3/5          | 4/6         |
| 6      | Chasm of the Undead   | 2/5          | 3/6         |
| 7      | Forbidden Land        | 2/8          | 3/8         |
| 8      | Great Abyss           | 6/4          | 7/5         |
| 9      | Highpeak Range        | 8/2          | 9/3         |
| 10     | Black Lagoon          | 5/5          | 6/6         |
| 11     | Eastern Darkmoor      | 6/1          | 7/2         |
| 12     | Death's Gorge         | 5/5          | 6/6         |
| 13     | Great Divide          | 1/7          | 2/8         |

**Resolution:** the other sheets' locations are canonical ([portals](reference/portals.md#locations)).
The High Priest list is treated as an offset error, not a separate set of portals:

- Every other sheet agrees on every portal, including the Knight Crusader of Medokh, which serves the same faction as the High Priest.
- The High Priest sheet uses the same portal numbers, region names, Use Portal order, and description of "the thirteen sacred Portals".
- `warlock-lord-of-kragenarg.md` says the opposing priesthood is "also likely to have use of the ancient Portals", so the portals are shared.
- The shift is not applied uniformly (portal 7), which suggests hand editing rather than design.

## Missing portals in the Hanguraz sheet

**Source:** `medocs/docs/sheets/warlock-lord-of-hanguraz.md`.

**Discrepancy:** the portal list omits portals 3 (Reaper's Dale) and 10 (Black Lagoon).
The other Warlock Lord sheets list all thirteen.

**Resolution:** all thirteen portals exist and are usable by every faction that may use portals.

## Region names

**Sources:** `medocs/docs/manual/tables/map-areas.md` and the sheets that name regions.

**Discrepancy:** region names are spelled inconsistently.

| Variants                                                   | Used here                       |
|------------------------------------------------------------|---------------------------------|
| "… of Skar" / "… of Khar"                                   | Khar                            |
| "Golden Savannak"                                          | Golden Savannah                 |
| "Northern Plains of the Farmer" / "… of the Farner"         | Northern Plains of the Farmer   |
| A leading "The" present in some places, absent in others   | Never used                      |

"Khar" applies to every region: Plains of Khar, Northern, Western, and Southern Plains of Khar, Wastelands of Khar, and Southern Wastelands of Khar.

**Resolution:** [world map: regions](reference/world-map.md#regions) uses the spellings above.

## Missing direction in the movement rules

**Source:** `medocs/docs/manual/army-movement.md`.

**Discrepancy:** the text lists the directions an army may move as "North, North-East, South, South-West or North-West", which is five, not six.
South-east is missing.

**Resolution:** the six directions and their numbers are taken from the Siege Town order (`medocs/docs/manual/orders/military.md`), which lists all six:
1 North, 2 North-east, 3 South-east, 4 South, 5 South-west, 6 North-west.
See [world map: adjacency](reference/world-map.md#adjacency).
