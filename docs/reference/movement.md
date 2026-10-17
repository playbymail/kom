# Movement

How armies and Individuals move across the [world map](world-map.md).

Rules below are taken from the original documents unless marked otherwise.
Sources are `medocs/docs/manual/army-movement.md` (the compendium) and `medocs/docs/sheets/army-movement.md` (a later rule sheet).

## Directions

Movement uses the six direction numbers defined in [world map: adjacency](world-map.md#adjacency):
1 North, 2 North-east, 3 South-east, 4 South, 5 South-west, 6 North-west.

## Army movement order

| Field | Content                                                     |
|-------|-------------------------------------------------------------|
| Army  | Army ID                                                     |
| Mode  | Optional: `7` Pursuit, `8` Cautious, `9` Forced             |
| Steps | Up to 12 direction numbers, or for Pursuit a target army ID |

Examples from the original:

| Order                 | Meaning                                    |
|-----------------------|--------------------------------------------|
| `3 1 1 1 1`           | Army 3 moves four hexes north              |
| `3 1 6 6 5 5 4`       | North, north-west ×2, south-west ×2, south |
| `3 8 1 1 1 1`         | Cautious March four hexes north            |
| `3 9 1 1 1 1 1 1 1 1` | Forced March eight hexes north             |
| `3 7 263`             | Pursue army 263                            |

## Movement points

| Property               | Value                                                                |
|------------------------|----------------------------------------------------------------------|
| Points per turn        | About 20 per army, modified by morale                                |
| Carry-over             | None; unused points are lost                                         |
| Cost to enter a hex    | Set by the hex's terrain and the army's race (see [races](races.md)) |
| Insufficient points    | The army stops                                                       |
| Change during the turn | Orders resolved before movement may raise or lower points            |

### March modes

| Code | Mode     | Points        | Scouting         | Detection by others | Fatigue                                      |
|------|----------|---------------|------------------|---------------------|----------------------------------------------|
| —    | Normal   | 100%          | Normal           | Normal              | Normal                                       |
| `8`  | Cautious | 60%, rounded  | Greatly improved | Much harder         | Less than normal                             |
| `9`  | Forced   | 150%, rounded | Reduced          | Easier              | Considerably more; worse on successive turns |
| `7`  | Pursuit  | 150%, rounded | As Forced        | As Forced           | As Forced                                    |

- A Cautious army is more likely to ambush; a Forced army is more likely to be ambushed.
- Pursuit takes no directions. Each movement round the army steps toward the target's current location.
- An army may pursue only an army its own scouts saw last turn, within 4 hexes.
- Pursuing a mutually allied army follows it into the same hex.

### Trackers

A Tracker halves the movement cost of terrain it specialises in, to a minimum of 2 points per hex.
A Master Ranger counts as a Tracker in all six common terrain types.

## Movement rounds

- All armies of all tribes move at the same time, one hex per movement round.
- Rounds continue until every army has run out of points or orders, or is next to an enemy force.
- Routing armies (defeated last turn) move before all other armies.

## Entry restrictions

| Hex contains                              | An army may enter only if                                  |
|-------------------------------------------|------------------------------------------------------------|
| Another tribe's settlement                | The two tribes are mutually Allied                         |
| Another tribe's army                      | Neither tribe is Hostile to the other                      |
| Terrain not listed for the army's race    | Never (until a supplementary rule allows it)               |
| A portal                                  | See [portals](portals.md)                                  |
| A volcano                                 | Never, except under a Key of Power's heat shield           |
| The map edge                              | Never; see [world map: map edge](world-map.md#map-edge)    |

### Overwhelming force

An army about five or more times the size of an adjoining Hostile force (varies with race and strategy) ignores it and keeps moving, even through its hex.
Combat still happens if both end movement in the same or adjoining hexes.

### The "between" rule

A hex is *between* two foreign forces when it adjoins both of them and they do not adjoin each other.
Only armies, basic fortifications, towns, and cities count; garrisons of shrines, gem mines, and wizard's towers do not.

An army will rarely move into a between hex unless its tribe is Allied to the owner of at least one of the two.
A much larger army may risk it, and racial traits affect the decision.
The outcome is not guaranteed either way.

## Water

| Terrain                 | Armies                                                                                                                                   |
|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| Lake, Sea, Flooded      | Cannot enter                                                                                                                             |
| Frozen Flooded          | Unknown; the original documents do not mention it                                                                                        |
| Frozen Lake, Frozen Sea | 5 points per hex for every race; risk of losing regiments or whole armies, based on size and race (`medocs/docs/sheets/chaos-cometh.md`) |

## Scouting

Every moving army reports what its scouts see within 4 hexes (40 leagues).
Scouts may miss things, and the report says when the army itself went unseen.
Detection depends on army sizes and distance, terrain, terrain skill, commanders, Trackers and Master Rangers, march mode, and magic.

## Lines of supply

An army's supply line runs from its nearest controlled town or city, through controlled forts and armies, including mutually allied ones.
If enemy forces cut it, a large army's morale falls steeply after a few turns and desertions follow.
Small armies forage and are barely affected.

## Individuals

| Method                     | Range or rule                                                                                                                         |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| Transfer Individual (`TI`) | Up to 4 hexes, once per turn (`medocs/docs/manual/orders/individuals.md`)                                                             |
| Go To (Kingdom sheet)      | Crosses water, settlements, and armies; cannot enter volcanoes; risk of death each turn (`medocs/docs/sheets/kingdom-advancement.md`) |

## Open questions

- Movement cost for each race and terrain; the original Race Reference Cards are lost.
- Which terrain types each race may enter at all.
- Whether frozen lakes and seas, and their losses, are kept.
- Movement cost and risk for Frozen Flooded hexes.
- How Pursuit picks a step when several directions are equally close.
- Whether the "between" and overwhelming-force decisions are random, and on what inputs.
