# Green Crystal — interactive demo

A self-contained, single-file prototype for the Mergedom **Green Crystal** feature (order-only merge booster, tracked as `booster='greenstone'`).

Open `index.html` in any browser. No build, no dependencies. Works offline.

## What it shows

Drag the green crystals around the board and drop them on things.

| You drop a crystal on | What happens |
|---|---|
| An order item below max tier (Soap, Tools, Cleaning, Cookies, Toys) | Upgrades it one tier, plays the flash, consumes the crystal |
| An order item at max tier (Soap Lv5, Cookies Lv5) | Blocks — toast "This item is already at max tier", crystal not consumed |
| A producer, chest, coins, energy, or the blue gem | Refuses — toast "Green Crystal only works on regular items", crystal not consumed |
| An empty cell | Moves there, no event |
| Two matching order items (e.g. the two Soap Lv1) | Normal merge still works, untouched by the crystal |

## What to try

- **First-use tutorial** — the first time you pick up a crystal, the one-time coachmark fires. Tap to dismiss. Use **Replay** in the side panel to see it again.
- **Kill switch** — flip `GreenCrystal.IsWorking` off and the crystal goes inert.
- **MaxTargetTier** — set the optional cap to `5` or `7`, then drop a crystal on a higher item to see it block on the cap instead of upgrading.
- **booster_used event log** — every drop onto a real item logs a row exactly as the analytics spec defines it (`booster`, `used_on`, `family`, `outcome`, `consumed`). The counters demonstrate the parity caveat: real usage is `outcome='success'`, never a raw row count.

## Notes

Prototype, not final art. A green recolor of the blue gem stands in for the Green Crystal per the PRD's easy-path art option. Order families and tier ceilings come from `mergedom_items.md` (the balancing spreadsheet).

PRD lives in the prd-workspace: `green-crystal.md` and `green-crystal-notion.md`.
