# Scholastic Utopia: design

The source of truth for the game. Each section says whether it is **LOCKED** (Mike confirmed it)
or a **DRAFT** (talked through, not yet confirmed). A draft becomes locked only when Mike says so.

## A. The game — LOCKED (28 Oct 2026, Mike)

1. **Its own game and repo**, Scholastic Utopia, separate from Torchfire (the dungeon crawler in
   `pirateslounge420/animated-succotash`). This is the open world split off from "Torchfire 2".
2. **No items.** You wander through the environment. Nothing to collect, carry or equip. (The old
   open world's spear, bow, fishing pole, tools and inventory do not come over.)
3. **The focus is ambient atmosphere:** lighting patterns, the sky, clouds and procedurally
   generated (RNG) landscapes.
4. **The vibe:** Frutiger Aero, and a scholastic, utopian age of exploration (§D).

## B. The clock and sky — LOCKED (28 Oct 2026, Mike; the numbers as built in animated-succotash)

1. **The 144-minute day** (one game hour = 6 real minutes), with **day, dusk, night and dawn** as
   smooth gradients. At the equinox: 60 min day, 18 dusk, 48 night, 18 dawn. Dawn and dusk stay
   18 minutes all year; days lengthen in summer and shorten in winter by latitude.
2. **Sun and moon** both track across the sky and both light the world; a 29.5-day moon cycle,
   full moons visibly brighter.
3. **Four seasons over a 365-day year** (axial tilt 23.5°), with gradual changes between them;
   the southern hemisphere runs half a year behind. A year is 36.5 real days.
4. **Clouds** drift, build and change across the sky over time; fog rolls in and shifts.
5. Data: `data/sky/day_cycle.json` and `data/seasons.json`, copied unchanged from animated-succotash.

## C. The planet — LOCKED (28 Oct 2026, Mike)

1. **A new random planet every game**, about the size of the old 1/100-Earth world (~400 km
   around). Inspired by Earth in size, **not** in its continent shapes.
2. **Earth-like physics decides everything else:** climate, biomes and weather emerge the way they
   do on Earth: latitude bands, height, distance from water, mountains blocking rain (wet windward,
   dry leeward), wind from pressure systems.
3. **Generation runs as ordered passes**, each reading only the passes before it: height (from the
   seed) → water (seas, rivers traced downhill) → temperature → moisture → biome → plants.
   Nothing is hand-placed.
4. **Biomes blend** with smooth gradients, never hard borders.
5. **The biome roster stays as built:** 53 templates (below). Climate ranges are in `data/biomes/`.

### C.1 The 53 biomes

- **Polar/cold** (4): Ice sheet / polar desert; Tundra; Alpine tundra; Forest-tundra / krummholz.
- **Forest** (4): Taiga / coniferous forest; Temperate deciduous / mixed forest; Temperate rainforest; Montane / cloud forest.
- **Grass & scrub** (6): Tallgrass prairie; Shortgrass prairie; Steppe; Sagebrush shrubland; Mediterranean scrub; Thorn scrub.
- **High-altitude** (4): Paramo; Puna; Alpine meadow; Montane grassland and shrubland (central Mexico).
- **Desert** (2): Cold desert; Hot desert.
- **Tropical** (4): Tropical rainforest; Jungle; Tropical dry forest; Savanna.
- **Wetlands** (7): Swamp / bayou; Floodplain forest; Freshwater marsh; Wet meadow; Salt marsh; Bog; Fen.
- **Coastal** (7): Beach; Dunes; Rocky shore; Maritime forest; Mangrove; Estuary / delta; Lagoon.
- **Freshwater** (2): Fresh water (river, lake); Oasis.
- **Ocean** (5): Shelf sea; Coral reef; Kelp forest; Open / deep ocean; Sea ice.
- **Special** (5): Volcanic field; Badlands; Canyon; Salt flat; Hot spring.
- **Glaciers** (1): Glacier.
- **Caves** (1): Karst / caves (no climate block yet).
- **Mountain** (1): Tepui summit.

## D. The vibe: Frutiger Aero meets the age of exploration — DIRECTION LOCKED (28 Oct 2026, Mike); details DRAFT

**Locked:** the world should feel Frutiger Aero and scholastic-utopian age of exploration.

**Draft (Claude's reading, not yet confirmed):**
1. **Frutiger Aero in the world:** bright aqua skies, tall glossy cumulus, clear water you can see
   the bottom of, dew and droplets catching the light, soft lens flare and bloom, lush saturated
   greens, bubbles and mist at waterfalls. Clean, fresh and alive.
2. **Age of exploration in the feel:** you are a naturalist on an expedition (Humboldt, Darwin,
   botanical plates, brass instruments, maps filling in) in a world that is beautiful, not hostile.
   Wandering is curiosity and discovery, not survival.
3. **Tone:** bright and wondrous. Night is serene rather than scary: starfields, glowing plants,
   fireflies, moonlight on water. The old open world's dark, dangerous tone stays with Torchfire.

## E. Plants — DIRECTION LOCKED (28 Oct 2026, Mike); the roster is a DRAFT

**Locked:** a simplified plant roster of our own, **inspired by Earth's plants but unique to this
game**, not mapped to real species.

**Draft roster (Claude's proposal):** about 24 plant families. Each family comes in a few sizes
and forms by climate, so one family spans many biomes. Most do something with the light, the time
of day, the wind or the season, so the plants help show the 144-minute day. [Brackets: the Earth
plants it is inspired by.]

**Trees**
1. **Spirepine** [pine, redwood, monkey puzzle]: twisted dwarfs at treeline to giant spires. Cold to temperate.
2. **Silverbark** [oak, magnolia]: pale trunks; leaves go copper, then crimson, then bare. Temperate.
3. **Fanleaf** [ginkgo]: ancient-looking; turns pure gold in autumn and drops it all in a few days.
4. **Bogcypress** [cypress]: knee-roots standing out of water. Swamps and floodplains.
5. **Bottletree** [baobab]: swollen water-storing trunk. Dry tropics.
6. **Parasol tree** [acacia]: flat-topped and thorny. Savanna and thorn scrub.
7. **Titanfig** [strangler fig]: huge buttress roots. Rainforest.
8. **Wind-palm** [palms]: leaning trunks. Coasts, oases, tropics.
9. **Tidegrove** [mangrove]: stilt roots in salt water.
10. **Glowfruit** [citrus]: glossy leaves; the fruit catches the low sun at dusk. Warm climates.

**Shrubs and big leaves**
11. **Fireblossom** [rhododendron]: blazes with flowers in spring. Mountain slopes and cloud forest.
12. **Scaletrunk** [cycad]: prehistoric-looking. Hot, dry to tropical.
13. **Silversage** [sagebrush, rosemary]: silver-grey and aromatic. Dry scrub.
14. **Elephant ear** [aroids, alocasia, philodendron]: giant leaves that tilt to follow the light through the day. Tropics.
15. **Bannerleaf** [banana]: huge leaves that shred into ribbons in the wind. Tropics.
16. **Torch cactus**: tall columns that flower only at night. Deserts.
17. **Skyweed** [cannabis]: wild populations that vary by region.

**Ground, water and hangers-on**
18. **Whisperwheat** [wild grasses]: ripples in waves under the wind; changes colour with the seasons.
19. **Curlfern** [ferns]: unrolls at dawn, curls shut at dusk. Anywhere damp.
20. **Moss and lichen**: carpets, beards and crusts. Everywhere cool or damp.
21. **Airvine** [bromeliads, Spanish moss]: hangs and grows on other plants. Cloud forest and swamp.
22. **Trapleaf** [pitcher plants, flytraps]: bogs and fens.
23. **Dusk and dawn flowers** [moonflower, datura, morning glory]: some open at dawn and close at dusk, others the reverse.
24. **Glowcaps** [fungi]: mushrooms that softly light up at night. Forest floors and caves.

Each biome file has an empty `plant_families` list to fill once the roster is locked.

## F. Ideas raised, not decided

1. **Field journal:** when you get close to a new plant or animal, it sketches itself into a
   journal as a botanical-style plate with its name. A record, not an item.

## Open (for Mike)

1. Does the dark, dangerous tone (night dread, werewolves) go entirely, or does some mystery stay at night?
2. The field journal: yes or no?
3. Do animals roam as ambient life? If so, invented like the plants?
4. Lock the plant family roster (names, cuts, additions) and the vibe details in §D.
5. Basic ideas for each biome: its look, light, weather and which plant families grow there.
6. Which code to bring over from animated-succotash (sky, clouds, calendar, world generation, plant
   shapes) and in what order.
