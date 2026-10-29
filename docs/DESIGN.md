# Scholastic Utopia: design

Decisions are recorded here only once Mike confirms them. Brainstorms stay in chat until then.

## A. The game — LOCKED (28 Oct 2026, Mike)

1. **Its own game and repo**, named Scholastic Utopia, separate from Torchfire (the crawler).
2. **No items.** You wander through the environment. Nothing to collect, carry or equip.
3. **The focus is ambient atmosphere:** lighting, sky, clouds and procedurally generated landscapes.
4. **The clock:** the 144-minute day, with day, dusk, night and dawn as smooth gradients, the sun
   and moon both lighting the world, and the seasons. Reused from the Torchfire 2 sky and calendar
   code in `animated-succotash`.
5. **Clouds** drift and change across the sky.
6. **The vibe:** Frutiger Aero, and a scholastic, utopian age of exploration.

## B. The planet — LOCKED (28 Oct 2026, Mike)

1. **A new random planet every game**, about the size of the old 1/100-Earth world (~400 km around).
   Not Earth's continents.
2. **Earth-like physics decides everything else:** climate, biomes and weather emerge the way they
   do on Earth (latitude, height, distance from water, mountains blocking rain). Generation runs as
   ordered passes: height, water, temperature, moisture, biome, plants.
3. **The biome roster stays as built:** the 53 biome templates from `animated-succotash/data/biomes`.

## C. Plants — DIRECTION LOCKED, roster still a draft (28 Oct 2026, Mike)

1. **A simplified plant roster of our own**, inspired by Earth's plants but unique to this game,
   not mapped to real species.
2. **Draft (not yet locked):** about 24 plant families, each with a few sizes and forms by climate,
   so one family spans many biomes. Most do something with the light, time of day, wind or season.

## Open (for Mike)

1. Does the old open world's dark, dangerous tone (night dread, werewolves) go entirely, or does
   some mystery stay at night?
2. A field journal that sketches each new plant or animal as a botanical plate: yes or no?
3. Do animals roam as ambient life?
4. Lock the plant family roster (names, cuts, additions).
5. Which code to bring over from `animated-succotash` (sky, clouds, calendar, world generation,
   plant shapes) and in what order.
