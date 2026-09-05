# Credits

Upscalerino installs other people's work. It does not invent any of the rendering
technology it deploys — it figures out which components a game needs, puts them in
the right place with the right settings, and records what it touched so it can undo
it. Everything below is someone else's craft, and the app is useless without it.

Thank you, all of you.

## The neural rendering stack

**NVIDIA** — DLSS, DLSS-D, DLSS-G, Streamline, and the NGX neural rendering runtime
(`nvngx_dlssnr.dll`). The whole reason this app exists.

**clshortfuse and the RenoDX contributors** — RenoDX, and the DLSS / DLSS 5 add-ons
built on it (`renodx-dlss.addon64`, `renodx-dlss5.addon64`, `renodx-dlssfix.addon64`).
The ShortFuse lane is the one that works most reliably across the most games, and it
is the first thing this app ever successfully deployed.

**jlrouzies-fr** — DLSS5-Feeder. The reason games with no DLSS of their own can be fed
a neural pass at all: the 32-bit add-on, the 64-bit host process, the Vulkan layer and
`DLSS5_Feed.fx` between them cover the cases nothing else reaches.

**Alexander** — Deep Fried Chicken. The lane that rescued Persona 5 Royal when nothing
else would hook it.

**cdozdil**, and **Dagherbou** for the DLSS-NR fork — OptiScaler. The universal
upscaler-swap layer, and the fallback when a game's own API refuses every other route.

**Alex** — Alex's Toolkit, and the multipass work that pairs with the DLSS 5 Tool.

## Injection, wrappers and translation

**crosire** — ReShade. Every single pipeline in this app rides on it. The add-on API is
what makes any of this possible from outside a game's own code.

**Dege** — dgVoodoo2. The reason 20-year-old DX8 and DX9 games can be brought forward
far enough to be worth upscaling at all.

**The DXVK project** — D3D9/10/11 over Vulkan, and the 64-bit ladder that rides it.

**The bridge authors** — `dlss5-bridge`, `dlss5-vk-bridge`, `dlss5-opengl-bridge` and
the D3D12 mip-chain fix, which between them close the gaps the main lanes leave open.

## Shaders and image quality

**Pascal Gilcher (Marty McFly) — Marty's Mods** — LAUNCHPAD, iMMERSE, MXAO and qUINT.
The motion-vector and depth groundwork the feeder lanes depend on, and most of the
lighting quality on top.

**umar-afzaal** — LumeniteFX. Ambient occlusion and bounce light that the neural pass
fundamentally cannot produce on its own, because it never sees the scene geometry.

**The VORT and CShade authors** — additional shader packs, alternative AO and GI
approaches, and RCAS/CAS sharpening that gets detail back after upscaling.

**AMD** — FidelityFX and the CAS/RCAS sharpening algorithms.
**Intel** — XeSS.
**Microsoft** — DirectX headers, and the Detours library several of these tools use.

## Knowledge, not code

A great deal of what this app knows — which hook point a given engine needs, which
combinations fight each other, which log lines are harmless and which mean a real
failure — came from people writing up what they found, in readmes, changelogs, forum
threads and issue trackers, with nothing to gain from it. That collected knowledge is
most of the value here. The code is just what remembers it.

## Also

**SteamGridDB** and its contributors, for the cover art.

---

If your work is here and you would rather it were not bundled, linked, or credited this
way — say so and it will be changed or removed. Nothing here is meant to take anything
from anyone.

## Every component, as the app lists it

Generated from the app's own component list by `build/gen_docs.py`, so this table and
the app can never disagree about who made what.

<!-- COMPONENTS:BEGIN -->
| Component | Author | Where it comes from |
|---|---|---|
| ReShade 6.8.0 (add-on build) | crosire | [ReShade (get the Addon build)](https://reshade.me) |
| NVIDIA DLSS runtime | NVIDIA | [NVIDIA DLSS SDK](https://github.com/NVIDIA/DLSS) |
| DLSS Neural Rendering runtime | NVIDIA | No public download page - it comes from your own NVIDIA driver. Community builds for RTX 20/30/40 are posted in the RenoDX Discord, #dlss5 channel: https://discord.com/invite/renodx |
| RenoDX DLSS add-on (ShortFuse build) | clshortfuse | [RenoDX Discord, #dlss5](https://discord.com/invite/renodx) |
| RenoDX DLSS add-on - pass-bar build | clshortfuse | [RenoDX Discord, #dlss5](https://discord.com/invite/renodx) |
| RenoDX ShortFuse (v2 build) | clshortfuse | [RenoDX Discord, #dlss5](https://discord.com/invite/renodx) |
| DLSS 5 Tool add-on | RenoDX contributors | [RenoDX Discord, #dlss5](https://discord.com/invite/renodx); [RenoDX source](https://github.com/clshortfuse/renodx) |
| RenoDX DLSS Fix add-on | clshortfuse | [RenoDX Discord, #dlss5](https://discord.com/invite/renodx) |
| DLSS5-Feeder 0.12.1-beta.2 (0.12.0 kept as fallback) | Jean-Laurent ROUZIES (jlrouzies-fr) | [DLSS5-Feeder releases](https://github.com/jlrouzies-fr/DLSS5-Feeder/releases) |
| Deep Fried Chicken | Alexander | [Linked from the DLSS5-Feeder README](https://github.com/jlrouzies-fr/DLSS5-Feeder) |
| OptiScaler | cdozdil / optiscaler org | [OptiScaler releases](https://github.com/optiscaler/OptiScaler/releases) |
| OptiScaler DLSS-NR fork | Dagherbou | [OptiScaler DLSS-NR releases](https://github.com/Dagherbou/OptiScaler_DLSSNR/releases) |
| DLSS5-ReShade-AIO | kibblerz | [DLSS5-Reshade-AIO releases](https://github.com/kibblerz/DLSS5-Reshade-AIO/releases) |
| Alex's Toolkit | Alex | [RenoDX Discord (where Alex's Toolkit and similar variants are posted)](https://discord.com/invite/renodx) |
| dgVoodoo 2.87.4 | Dege | [dgVoodoo2](https://www.dege.freeweb.hu/dgVoodoo2/) |
| DXVK | Philip Rebohle, Joshua Ashton and contributors | [DXVK releases](https://github.com/doitsujin/dxvk/releases) |
| NVIDIA Streamline | NVIDIA | [NVIDIA Streamline releases](https://github.com/NVIDIA-RTX/Streamline/releases) |
| DLSS 5 bridges | NIGos, Alan Z, Noel | [dlss5-bridge](https://github.com/NIGos/dlss5-bridge); [dlss5-vk-bridge](https://github.com/NIGos/dlss5-vk-bridge); [dlss5-opengl-bridge](https://github.com/NIGos/dlss5-opengl-bridge); [dlss5-d3d12-fix](https://github.com/NIGos/dlss5-d3d12-fix) |
| ReShade shader packs | various | [Marty's Mods (iMMERSE, qUINT)](https://github.com/martymcmodding); [LumeniteFX](https://github.com/LumeniteFX/LumeniteFX); [CShade](https://github.com/papadanku/CShade); [ZenteonFX](https://github.com/Zenteon/ZenteonFX) |
| 7-Zip command line | Igor Pavlov | [7-Zip](https://www.7-zip.org) |
<!-- COMPONENTS:END -->
