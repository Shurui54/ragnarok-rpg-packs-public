# Ragnarok RPG Toolkit: public packs

This is what the **Ragnarok RPG Toolkit** mod downloads from in game. Players never need to visit it.

- `index.json`: the list the in-game Pack Browser reads.
- `packs/`: whole projects (scripts and docs) that players can try or that servers can use.
- `assets/`: shared art libraries (models, textures, animations, sounds). The DMZ asset pack is split into two zips
  to stay under GitHub's file size limit.

When a project needs an art library it doesn't have (Dragon Block Ragnarok needs `dmzpack`), the game asks the player once,
downloads the parts, checks their SHA-256, and unpacks them into `<minecraft folder>/ragnarok_rpg/assetpacks/`.
Nothing is written outside the Minecraft folder.

## Updating
Rebuild with `tools/publish_packs.py` in the toolkit repo. It writes the zips and `index.json` with the right sizes and
checksums. Bump the asset version when the art changes, and update `assetPacks: ["dmzpack@<version>"]` in the starter's
`00_project.js` so players get the update.

Credits for the DMZ art are in `assets/dmzpack/CREDITS.txt` inside the asset pack.

## Licences

Everything in this repository is open source:

- `addons/dragon_block_ragnarok-*.zip`: GPL-3.0-or-later. Each zip carries its own `LICENSE`, and a `NOTICE.md` with
  credits for DragonMine Z, whose systems it recreates.
- `assets/dmzpack-*`: art and sounds from DragonMine Z (GPL-3.0-or-later), with credits inside the pack. Two sounds are
  CC-BY and are credited there too.
- Anything else here with no licence of its own: GPL-3.0-or-later (see `LICENSE`).

The Ragnarok RPG Toolkit mod itself is closed source and isn't in this repository; it only downloads these files.
