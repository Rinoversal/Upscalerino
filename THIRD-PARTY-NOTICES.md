# Third-party notices

Upscalerino installs other people's software into games. It ships none of it. Every item below is the work of the people named, kept under their own terms, and supplied by the person using the app - the app files it, checks it against a known hash where one exists, places it, and takes it out again on Revert.

If your work is here and you would rather it were not deployed, linked, or credited this way, say so and it will be changed or removed.

## ReShade 6.8.0 (add-on build)

- **By:** crosire
- **Licence / terms:** BSD-3-Clause (ReShade). Binaries are not re-shared: get them from reshade.me.
- **Files the app places:** `ReShade64.dll`, `ReShade32.dll`
- **Where to get it:**
  - [ReShade (get the Addon build)](https://reshade.me)
- **Build the app is tested with:** `ReShade64.dll`, 5,592,064 bytes, sha256 `0cee63f9c9f13f3ac909c5b4903f4dbb4b719a7ab3b4f13b0deaf83c814b94f7`

## NVIDIA DLSS runtime

- **By:** NVIDIA
- **Licence / terms:** NVIDIA DLSS SDK licence. Redistributable only inside an application; you supply the file.
- **Files the app places:** `nvngx_dlss.dll`
- **Where to get it:**
  - [NVIDIA DLSS SDK](https://github.com/NVIDIA/DLSS)
- **Build the app is tested with:** `nvngx_dlss.dll`, 58,956,400 bytes, sha256 `c85f971ce023c9f3492fc7455f0b01a24ba18ea39636407a846902c4360b0b7e`

## DLSS Neural Rendering runtime

- **By:** NVIDIA
- **Licence / terms:** NVIDIA driver component. Not published in any SDK; comes from your own driver.
- **Files the app places:** `nvngx_dlssnr.dll`
- **Where to get it:** No public download page - it comes from your own NVIDIA driver. Community builds for RTX 20/30/40 are posted in the RenoDX Discord, #dlss5 channel: https://discord.com/invite/renodx
- **Build the app is tested with:** `nvngx_dlssnr.dll`, 165,840,496 bytes, sha256 `984bee0f775c277d5829b8fd6775d53a7b0f75396c852b3aaf06a18375f81014`

## RenoDX DLSS add-on (ShortFuse build)

- **By:** clshortfuse
- **Licence / terms:** RenoDX add-on, distributed by its author through the RenoDX Discord.
- **Files the app places:** `renodx-dlss.addon64`
- **Where to get it:**
  - [RenoDX Discord, #dlss5](https://discord.com/invite/renodx)
- **Build the app is tested with:** `renodx-dlss.addon64`, 2,578,432 bytes, sha256 `27c73c0df1cbd4576c5b47d2809be06be3bea0a90ac55093fa7e334bb4742a15`

## RenoDX DLSS add-on - pass-bar build

- **By:** clshortfuse
- **Licence / terms:** RenoDX add-on, distributed by its author through the RenoDX Discord.
- **Files the app places:** `renodx-dlss.addon64`
- **Where to get it:**
  - [RenoDX Discord, #dlss5](https://discord.com/invite/renodx)
- **Build the app is tested with:** `renodx-dlss.addon64`, 2,499,584 bytes, sha256 `85eae478f1e733e85b247c32469c2b2cc1a1c0dd2ab4afd7dac240e619201cee`

## RenoDX ShortFuse (v2 build)

- **By:** clshortfuse
- **Licence / terms:** RenoDX add-on, distributed by its author through the RenoDX Discord.
- **Files the app places:** `renodx-dlss.addon64`
- **Where to get it:**
  - [RenoDX Discord, #dlss5](https://discord.com/invite/renodx)
- **Build the app is tested with:** `renodx-dlss.addon64`, 2,520,576 bytes, sha256 `fba3271626587f8b1f49c4fb40bbe23fd969282da6fe48be2da9b17beb708ee6`

## DLSS 5 Tool add-on

- **By:** RenoDX contributors
- **Licence / terms:** RenoDX add-on, distributed by its author through the RenoDX Discord.
- **Files the app places:** `renodx-dlss5.addon64`
- **Where to get it:**
  - [RenoDX Discord, #dlss5](https://discord.com/invite/renodx)
  - [RenoDX source](https://github.com/clshortfuse/renodx)
- **Build the app is tested with:** `renodx-dlss5.addon64`, 1,732,608 bytes, sha256 `d5adf82eb44b065f4c590ac91fe824bab07afea0eb9f994bde936710c8593952`

## RenoDX DLSS Fix add-on

- **By:** clshortfuse
- **Licence / terms:** RenoDX add-on, distributed by its author through the RenoDX Discord.
- **Files the app places:** `renodx-dlssfix.addon64`, `DLSS Fix.addon64`
- **Where to get it:**
  - [RenoDX Discord, #dlss5](https://discord.com/invite/renodx)
- **Build the app is tested with:** `DLSS Fix.addon64`, 1,712,640 bytes, sha256 `6c550b3258e9ec570ce3544f26754aaeed0fbf027a8a7167fce4fd7120d790b9`

## DLSS5-Feeder 0.12.1-beta.2 (0.12.0 kept as fallback)

- **By:** Jean-Laurent ROUZIES (jlrouzies-fr)
- **Licence / terms:** MIT.
- **Files the app places:** `dlss5-feed.addon64`, `dlss5-feed.addon32`, `dlss5-feed-host64.exe`, `DLSS5_Feed.fx`
- **Where to get it:**
  - [DLSS5-Feeder releases](https://github.com/jlrouzies-fr/DLSS5-Feeder/releases)
- **Build the app is tested with:** `dlss5-feed.addon64`, 236,032 bytes, sha256 `61d91549fb18778ad8e60fd61d5cb6b6be5bdc6b639fbf535eb349630197c159`

## Deep Fried Chicken

- **By:** Alexander
- **Licence / terms:** Author's own terms; bundling by anyone else is forbidden.
- **Files the app places:** `deep-fried-chicken.addon64`, `deep-fried-chicken-nvngx.dll`, `deep-fried-chicken.cfg`
- **Where to get it:**
  - [Linked from the DLSS5-Feeder README](https://github.com/jlrouzies-fr/DLSS5-Feeder)
- **Build the app is tested with:** `deep-fried-chicken.addon64`, 726,016 bytes, sha256 `96e7a582019372c66b25201db898bf17bc3a4d285d32ff13782dd856ed9f74d7`

## OptiScaler

- **By:** cdozdil / optiscaler org
- **Licence / terms:** GPL-3.0.
- **Files the app places:** `OptiScaler.dll`, `OptiScaler.ini`
- **Where to get it:**
  - [OptiScaler releases](https://github.com/optiscaler/OptiScaler/releases)
- **Build the app is tested with:** `OptiScaler.dll`, 25,379,632 bytes, sha256 `fbfb6676b829dad7e020fb830586a16aa0ec6add78016db48ef12e2ae1803231`

## OptiScaler DLSS-NR fork

- **By:** Dagherbou
- **Licence / terms:** GPL-3.0.
- **Files the app places:** `OptiScaler.dll`
- **Where to get it:**
  - [OptiScaler DLSS-NR releases](https://github.com/Dagherbou/OptiScaler_DLSSNR/releases)
- **Build the app is tested with:** `OptiScaler.dll`, 25,712,640 bytes, sha256 `365fd117fdcceedc9a75311243c0a3ef06d54252420547947d5782595aa35294`

## DLSS5-ReShade-AIO

- **By:** kibblerz
- **Licence / terms:** Open release on GitHub; see the project page for its terms.
- **Files the app places:** `standalone-dlssnr.addon64`, `DLSS5_AIO_Feed.fx`
- **Where to get it:**
  - [DLSS5-Reshade-AIO releases](https://github.com/kibblerz/DLSS5-Reshade-AIO/releases)
- **Build the app is tested with:** `standalone-dlssnr.addon64`, 138,752 bytes, sha256 `2fd358882d2cd30ca6eb68821fa5d9c58269ea5856f66ca6cdfa108fbfa8d105`

## Alex's Toolkit

- **By:** Alex
- **Licence / terms:** No published licence.
- **Files the app places:** `alexs-toolkit.addon64`
- **Where to get it:**
  - [RenoDX Discord (where Alex's Toolkit and similar variants are posted)](https://discord.com/invite/renodx)
- **Build the app is tested with:** `alexs-toolkit.addon64`, 275,456 bytes, sha256 `04c134ac31e515e21f6c35cbaeb4cabe8eb3411916997995ad9174b6e84c6a1b`

## dgVoodoo 2.87.4

- **By:** Dege
- **Licence / terms:** Freeware; the author's terms cover redistribution with other software.
- **Files the app places:** `D3D8.dll`, `D3D9.dll`, `DDraw.dll`, `dgVoodooCpl.exe`
- **Where to get it:**
  - [dgVoodoo2](https://www.dege.freeweb.hu/dgVoodoo2/)
- **Build the app is tested with:** `D3D8.dll`, 2,012,672 bytes, sha256 `8e6bd4fa76f47c48e7ceb1ceefb03808f5b739e4c837273a10b61c1c616ab3dc`

## DXVK

- **By:** Philip Rebohle, Joshua Ashton and contributors
- **Licence / terms:** zlib.
- **Files the app places:** `d3d9.dll`, `d3d11.dll`, `dxgi.dll`
- **Where to get it:**
  - [DXVK releases](https://github.com/doitsujin/dxvk/releases)
- **Build the app is tested with:** `d3d9.dll`, 7,860,238 bytes, sha256 `337f45c215afee723d6b73e46e545f665940b2543fd029b37060959dbcfb75b1`

## NVIDIA Streamline

- **By:** NVIDIA
- **Licence / terms:** NVIDIA Streamline licence.
- **Files the app places:** `sl.interposer.dll`, `sl.common.dll`, `sl.dlss.dll`
- **Where to get it:**
  - [NVIDIA Streamline releases](https://github.com/NVIDIA-RTX/Streamline/releases)
- **Build the app is tested with:** `sl.interposer.dll`, 651,392 bytes, sha256 `27b2190057994c0b287c2c5716953bf1586f6499ac12fbbb2092b9aaf8396570`

## DLSS 5 bridges

- **By:** NIGos, Alan Z, Noel
- **Licence / terms:** MIT.
- **Files the app places:** `dlss5-bridge.addon64`, `dlss5-vk-bridge.dll`, `dlss5-opengl-bridge.addon64`, `dlss5-d3d12-fix.addon64`
- **Where to get it:**
  - [dlss5-bridge](https://github.com/NIGos/dlss5-bridge)
  - [dlss5-vk-bridge](https://github.com/NIGos/dlss5-vk-bridge)
  - [dlss5-opengl-bridge](https://github.com/NIGos/dlss5-opengl-bridge)
  - [dlss5-d3d12-fix](https://github.com/NIGos/dlss5-d3d12-fix)
- **Build the app is tested with:** `dlss5-bridge.addon64`, 465,408 bytes, sha256 `f0828689adab004c23e433bf4c6cf5f890641136582abb2856de8d83443ea9e5`

## ReShade shader packs

- **By:** various
- **Licence / terms:** Marty's Mods shaders are proprietary and must not be redistributed; other packs keep their own licences.
- **Files the app places:** `MartysMods_LAUNCHPAD.fx`, `lumenite_Kernel.fx`, `vort_*.fx`, `c*.fx`
- **Where to get it:**
  - [Marty's Mods (iMMERSE, qUINT)](https://github.com/martymcmodding)
  - [LumeniteFX](https://github.com/LumeniteFX/LumeniteFX)
  - [CShade](https://github.com/papadanku/CShade)
  - [ZenteonFX](https://github.com/Zenteon/ZenteonFX)
- **Build the app is tested with:** `MartysMods_LAUNCHPAD.fx`, 64,226 bytes, sha256 `fbe62772ad6782f5c8126f73470ae586f5395455719ad90b1287e8bb57b7b033`

## 7-Zip command line

- **By:** Igor Pavlov
- **Licence / terms:** 7-Zip: GNU LGPL, with the unRAR restriction.
- **Files the app places:** `7z.exe`
- **Where to get it:**
  - [7-Zip](https://www.7-zip.org)

## Also

- **AMD** - FidelityFX and the CAS / RCAS sharpening algorithms.
- **Intel** - XeSS.
- **Microsoft** - DirectX headers and the Detours library several of these tools use.
- **SteamGridDB** and its contributors - cover art, through your own free API key.
- **Python**, **Nuitka**, **Inno Setup** - what the program itself is built with.
