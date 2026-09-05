# Upscalerino

**Puts NVIDIA DLSS 5 Neural Rendering into PC games, including games that never had DLSS,
and takes it back out cleanly.**

Pick a game, pick a pipeline, press Set up. The app works out the engine, the graphics
API and whether the game has DLSS, installs the right parts in the right order, and one
button puts everything back exactly as it was.

- **Download:** https://github.com/Rinoversal/Upscalerino/releases/latest
- **Discord:** https://discord.gg/YXdXz6967N
- **Details:** [TECHNICAL.md](TECHNICAL.md) has every pipeline, what each needs, and how it all works

## Getting started

1. Run the Setup exe (installs to your own folder, no administrator needed) or unzip the
   portable zip anywhere. Windows shows an "unknown publisher" warning the first time;
   that is what an unsigned app looks like. More info, Run anyway.
2. The components come with it. The one thing to add yourself is the neural engine for
   your card: NVIDIA's signed build for RTX 50, or the sf-v2 build for RTX 20/30/40.
   Drop the file on the app window. Onboarding says where each comes from.
3. Open a game, choose a pipeline, Set up, play. Revert undoes it.

## What you need

- Windows 10 / 11, 64-bit, an NVIDIA RTX card, a recent NVIDIA driver.
- ReShade 6.8.0 Addon build is included and is the version the add-ons are built for.

## Status

24 pipelines. 7 are confirmed in play, 3 are set up on a real game and waiting to be
confirmed, the rest are built and selectable but nobody has run them yet. Untested means
exactly that, not broken. The full table is in [TECHNICAL.md](TECHNICAL.md).

## Updates

The app checks for a newer release when it starts (a preference you can turn off) and
never installs without you pressing the buttons. Your library, pipelines, settings, key,
components and engines are never touched by an update.

## Credits and licences

The rendering technology is other people's work. [CREDITS.md](CREDITS.md) says whose, and
[THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md) has every component's author, terms and
source. The app itself is BSD-2-Clause, see [LICENSE](LICENSE).

Upscalerino 2026 - Made by Carterino
