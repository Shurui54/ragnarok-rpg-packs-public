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

DragonMine Z assets belong to their creators; see `CREDITS.txt` in the starter pack.
