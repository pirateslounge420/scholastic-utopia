# Working on Scholastic Utopia

- Mike is not a coder. He describes the game in plain English; explain to him in plain English what changed and what he will see.
- `docs/DESIGN.md` is the source of truth. Build only what is marked LOCKED; never treat a DRAFT as decided.
- Record a design decision in DESIGN.md only once Mike confirms it, not during brainstorming.
- Mike does not move files around in the repo himself: commit and push changes directly.
- Tunable numbers live in `data/` as JSON, not in code.
- Code worth reusing (sky, clouds, calendar, world generation, plant shapes) is in `pirateslounge420/animated-succotash`, run there with `GAME=torchfire2`.
