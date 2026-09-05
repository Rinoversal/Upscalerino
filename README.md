# Upscalerino

**Puts NVIDIA DLSS 5 Neural Rendering into PC games - including games that never shipped
with DLSS - and takes it back out cleanly.**

Point it at a game. It works out which engine it is, which graphics API it really uses,
whether it has DLSS of its own, and which of its pipelines can carry a neural pass into it.
Then it installs that pipeline in the right order with the right settings, and records every
file it touched so one button puts the game back exactly as it was.

It does not invent any of the rendering technology. It is the part that knows *which*
pieces a given game needs, *where* they go, and *how to undo it*. See [CREDITS.md](CREDITS.md)
and [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md) for whose work it deploys.

- **Discord:** https://discord.gg/YXdXz6967N - help, shared looks, bug reports
- **Releases:** https://github.com/Rinoversal/Upscalerino/releases

---

## What it does

**Detects, rather than asks.** Engine and engine age, graphics API, bitness, whether the
game's *own* code calls DLSS (not just whether a DLSS file is lying around), FSR and XeSS
support, ReShade already present and which version, anti-cheat, Microsoft Store packaging,
and where the game keeps its settings so the render resolution can be changed for you.

**Finds your games wherever they are.** Steam libraries on every drive (from Steam's own
list), Epic, GOG and Ubisoft installs (from their own records), EA, Origin, Rockstar,
Amazon and Xbox folders, any drive's "Games" folder, and anything you add by hand - a
folder, a whole library, or a single exe. Nothing has to be on C:.

**Picks a pipeline and explains the choice.** Ride the game's own DLSS, feed a synthetic
one, translate an ancient API forward first, or hook Vulkan through a layer. Rejected lanes
come with the reason. Every pipeline lists what it needs - which ReShade build, which
add-ons, which effects - before you press anything.

**Refuses to stack.** One neural consumer per game folder. Switching pipelines unloads the
old one first and checks the new one can run before touching anything.

**Installs 20-year-old games in stages.** A 32-bit DX8/DX9 game gets its wrapper, then the
overlay, then the neural pass - one game launch each - so a game that will not start tells
you which layer broke it.

**Reverts byte-for-byte.** Every deploy writes a manifest. Every file it overwrites is kept
as `.original` or in a backup folder, and Revert puts it back. A deploy that dies half-way
still writes its manifest, so a failed install is undoable too.

**Shares looks.** The model, strength and pass count you dialled in for a game export as a
small text block - no binaries, no paths from your machine - ready to paste on Discord.
Someone else pastes it into the same game and gets your look, whichever neural add-on they
have installed.

**Warns, never blocks.** Anti-cheat, live-service games, Store packages, a ReShade version
other than the tested one: you get a clear warning and then it is your call.

## Pipelines

<!-- PIPELINES:BEGIN -->
24 pipelines. **4 tested** in play, **5 set up** on a real game and waiting to be confirmed, **15 untested** - built and selectable, but nobody has run them yet. Untested means exactly that, not broken; it is where bug reports are most welcome.

| Pipeline | Status | Stability | Needs |
|---|---|---|---|
| ShortFuse direct-NR | Tested - works with the applications this engine is for | stable | ReShade 6.8.0 Addon build, NVIDIA DLSS runtime, DLSS Neural Rendering runtime, RenoDX DLSS add-on (ShortFuse build), effect: MXAO, effect: RCAS |
| ShortFuse direct-NR (pass-bar build) | Tested - works with the applications this engine is for | experimental | ReShade 6.8.0 Addon build, NVIDIA DLSS runtime, DLSS Neural Rendering runtime, RenoDX DLSS add-on - pass-bar build, effect: MXAO, effect: RCAS |
| Standalone AIO (NR + DLSS SR + FG) | Tested - works with the applications this engine is for | experimental | ReShade 6.8.0 Addon build, NVIDIA DLSS runtime, DLSS Neural Rendering runtime, DLSS5-ReShade-AIO, effect: RCAS |
| Vulkan feeder (64-bit) | Tested - works with the applications this engine is for | experimental | ReShade 6.8.0 Addon build, NVIDIA DLSS runtime, DLSS Neural Rendering runtime, DLSS 5 Tool add-on, DLSS5-Feeder 0.12.1-beta.2 (0.12.0 kept as fallback), effect: RCAS |
| 32-bit dgVoodoo ladder 1/3 | Set up on a real game, not yet confirmed in play | experimental | dgVoodoo 2.87.4 |
| 32-bit dgVoodoo ladder 2/3 | Set up on a real game, not yet confirmed in play | experimental | ReShade 6.8.0 Addon build, dgVoodoo 2.87.4, effect: RCAS |
| Chicken on native DLSS | Set up on a real game, not yet confirmed in play | experimental | ReShade 6.8.0 Addon build, DLSS Neural Rendering runtime, Deep Fried Chicken, effect: MXAO, effect: RCAS |
| DLSS 5 Tool (krnikitin) | Set up on a real game, not yet confirmed in play | experimental | ReShade 6.8.0 Addon build, NVIDIA DLSS runtime, DLSS Neural Rendering runtime, DLSS 5 Tool add-on, effect: MXAO, effect: RCAS |
| Feeder + Chicken | Set up on a real game, not yet confirmed in play | experimental | ReShade 6.8.0 Addon build, NVIDIA DLSS runtime, DLSS Neural Rendering runtime, DLSS5-Feeder 0.12.1-beta.2 (0.12.0 kept as fallback), Deep Fried Chicken, effect: RCAS |
| 32-bit dgVoodoo ladder 3/3 | Built and selectable, nobody has run it yet | experimental | ReShade 6.8.0 Addon build, DLSS Neural Rendering runtime, DLSS5-Feeder 0.12.1-beta.2 (0.12.0 kept as fallback), dgVoodoo 2.87.4 |
| 32-bit ladder 1/3: DXVK | Built and selectable, nobody has run it yet | experimental | DXVK |
| 32-bit ladder 2/3: ReShade Vulkan layer | Built and selectable, nobody has run it yet | experimental | ReShade 6.8.0 Addon build, DXVK, effect: RCAS |
| 32-bit ladder 3/3: feeder 0.12 + host64 | Built and selectable, nobody has run it yet | experimental | ReShade 6.8.0 Addon build, DLSS Neural Rendering runtime, DLSS5-Feeder 0.12.1-beta.2 (0.12.0 kept as fallback), DXVK |
| 64-bit DX9 -> dgVoodoo, rung 1/3 | Built and selectable, nobody has run it yet | experimental | dgVoodoo 2.87.4 |
| 64-bit DX9 -> dgVoodoo, rung 2/3 | Built and selectable, nobody has run it yet | experimental | ReShade 6.8.0 Addon build, dgVoodoo 2.87.4, effect: RCAS |
| 64-bit DX9 -> dgVoodoo, rung 3/3 | Built and selectable, nobody has run it yet | experimental | ReShade 6.8.0 Addon build, DLSS Neural Rendering runtime, DLSS5-Feeder 0.12.1-beta.2 (0.12.0 kept as fallback), Deep Fried Chicken, dgVoodoo 2.87.4, effect: RCAS |
| dgVoodoo DX8 chain | Built and selectable, nobody has run it yet | experimental | dgVoodoo 2.87.4, 7-Zip command line, effect: RCAS |
| DLSS 5 Bridge (DX11/Vulkan mirror) | Built and selectable, nobody has run it yet | experimental | ReShade 6.8.0 Addon build, NVIDIA DLSS runtime, DLSS Neural Rendering runtime, DLSS 5 Tool add-on, DLSS 5 bridges, effect: MXAO, effect: RCAS |
| DLSS 5 Bridge synth (no-DLSS fallback) | Built and selectable, nobody has run it yet | experimental | ReShade 6.8.0 Addon build, NVIDIA DLSS runtime, DLSS Neural Rendering runtime, DLSS 5 Tool add-on, DLSS 5 bridges, effect: MXAO, effect: RCAS |
| OpenGL feeder (32-bit, host64) | Built and selectable, nobody has run it yet | experimental | ReShade 6.8.0 Addon build, DLSS Neural Rendering runtime, DLSS 5 Tool add-on, DLSS5-Feeder 0.12.1-beta.2 (0.12.0 kept as fallback) |
| OpenGL feeder (64-bit) | Built and selectable, nobody has run it yet | experimental | ReShade 6.8.0 Addon build, NVIDIA DLSS runtime, DLSS Neural Rendering runtime, DLSS 5 Tool add-on, DLSS5-Feeder 0.12.1-beta.2 (0.12.0 kept as fallback), effect: RCAS |
| OptiScaler bridge | Built and selectable, nobody has run it yet | experimental | OptiScaler, effect: MXAO, effect: RCAS |
| OptiScaler DLSS-NR (replaces the game's upscaler) | Built and selectable, nobody has run it yet | experimental | DLSS Neural Rendering runtime, OptiScaler DLSS-NR fork, effect: RCAS |
| Vulkan feeder + NIGHTLY ReShade layer | Built and selectable, nobody has run it yet | experimental | ReShade 6.8.0 Addon build, NVIDIA DLSS runtime, DLSS Neural Rendering runtime, DLSS 5 Tool add-on, DLSS5-Feeder 0.12.1-beta.2 (0.12.0 kept as fallback), effect: RCAS |
<!-- PIPELINES:END -->

## What you need

- Windows 10 / 11, 64-bit.
- An NVIDIA RTX card. RTX 50 runs NVIDIA's own signed neural build. RTX 20 / 30 / 40 need
  a community build - the signed one refuses to start on them.
- A recent NVIDIA driver (the neural runtime, `nvngx_dlssnr.dll`, ships with it).
- The files the app is not allowed to bundle. Most of them cannot legally be redistributed
  by anyone but their author, so you supply them: ReShade's Addon build, the neural add-ons,
  NVIDIA's runtimes. The app tells you which ones, where each comes from, and checks each
  one against the build it was tested with. [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md)
  has the full list with links.
- **ReShade 6.8.0, Addon build.** The add-ons are compiled against one ReShade API. Use the
  same build the app was tested with until a release says a newer one is supported; a
  different one is reported, not refused.

## First run

Run the installer (it installs to your own user folder, no administrator needed) or unzip
the portable build anywhere. The first start opens **Onboarding**, which walks through:

1. **The engine your card needs.** Drop `nvngx_dlssnr.dll` into the
   `Drop NVIDIA engine files here` folder (or `engines\`). The app identifies the build by
   its contents - every build is called the same thing - and picks the right one for your
   card. A build it has never seen is kept and you say which cards it is for.
2. **Everything else.** Any component file dropped into that folder, or any of its
   subfolders, is filed automatically - into the right place even if you put it in the
   wrong subfolder. The Components page shows what is still missing and where to get it.
3. **Box art (optional, free).** A [SteamGridDB](https://www.steamgriddb.com/profile/preferences/api)
   key gives non-Steam games real cover art. Stored on your machine, sent nowhere else.

Onboarding is always one click away in the header if you need it again.

## Everyday use

Click a game. The page shows what was detected, the pipelines that can run there with what
each needs, and the tools: **Set up**, **Tuning**, **Lock** (freeze a game's settings so
nothing overwrites them), **Fix launch crash**, **Troubleshoot**, **Revert**.

Click the box art for **Share & Import**: copy your look as text for Discord, or paste
someone else's and apply it.

**Restart as administrator** appears only when a pipeline needs it (the Vulkan lane edits a
machine-wide folder). Everything else runs as a normal user.

## Updates

The app can check GitHub for a newer release when it starts and say so in the header.
That check is a preference you can switch off, and it never downloads anything on its own.
Installing is always three presses: Check, Preview (it shows exactly which files change),
Install - then the app restarts itself to finish.

An update replaces the program only. These are never touched, whatever a release contains:

- your game library, favourites, hidden games and added folders
- every pipeline you have set up (those live inside the game folders)
- locked settings, saved looks, learned profiles
- your SteamGridDB key
- the components you supplied and the engines you dropped in

The previous program is kept in `_backup_before_update` until the next update.

## Privacy

No telemetry, no account, no phone-home. Outbound requests: SteamGridDB for cover art (only
with your key), and GitHub's release list (only if the update check is on). The
diagnostics button writes one local text file and uploads nothing. Shared looks contain no
paths from your machine.

## Known limits

- Untested pipelines are exactly that. They install and revert cleanly on disk; nobody has
  watched them in a game yet. Reports on the Discord are what moves them up the table.
- Microsoft Store / Xbox app packages are detected and warned about: Windows can block or
  silently undo files placed inside them.
- Just Cause 2 has no lane that can run it yet.

## Licence

BSD-2-Clause - see [LICENSE](LICENSE). Every component the app installs belongs to someone
else and keeps its own licence.

Upscalerino 2026 - Made by Carterino
