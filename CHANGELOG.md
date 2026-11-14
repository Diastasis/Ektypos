# Ektypos 3.3.2

14 November 2026. Fixed file names for GitHub hosting. No changes to printing or to the program's features.

## 3.3.2
- **Fixed file names.** The program is now `index.html`, the manifest is `manifest.webmanifest` and the offline helper is `sw.js`. The hosted address no longer contains a version number, so it stays the same for every release, and installed apps update in place.
- **Assets folder.** The app icons moved to `assets/icons/` and the logos and icon sources to `assets/brand/`. The manifest and the offline helper point to the new paths. The page itself is unchanged, because its own icon is embedded.
- **Updates reach installed copies.** The offline helper now downloads fresh files when it updates, so GitHub's own caching can't give an installed app an old version. Each release changes the cache name in `sw.js`.
- The manifest has a fixed app id and starts the app at the folder address.
- **Source code button** keeps the version in the name of the copy it downloads (`ektypos-v3.3.2.html`).
- A README with the logo and a repository layout is included.
- **Protocol document** (`docs/PROTOCOL.md`) now covers all seven Fichero models in the Fichero app: D11s, A4 6181, 4437 and 5622 (all tested on real hardware), and the 4575, 3561 and 5655 label printers (from the app's code, not yet supported by Ektypos). It replaces the A4-only notes and adds the model list, command table, all print sequences and a guide for adding a printer.

## 3.3.1 (earlier release)

14 November 2026. Name correction and new icon. No changes to printing.

## 3.3.1
- **The project is called Ektypos**, with the tagline **"Print it. No typos."** 
- **New icon.** The favicon, home-screen icons and maskable icon use the new Ektypos icon (brand set). The icon also appears next to the name in the header and in the About dialog.
- The About dialog shows the tagline.
- **Fonts** renamed again: Ektypos Book, Ektypos Sans, Ektypos Serif and Ektypos Mono. The letter shapes are unchanged.
- **Saved designs keep working.** Designs saved with 3.3.0 that use the Ektypose font names, and older designs that use the Lora and Liberation names, switch to the new names automatically.
- **Notices:** a new section, 2.5 in THIRD-PARTY-NOTICES.md, covers the icon and logo. They are the project's own artwork under AGPL-3.0-or-later. The logo lettering is set in Poppins (SIL OFL 1.1), which does not restrict artwork made with it. The section also asks people not to pass off modified versions as the official Ektypos. The About dialog has a matching credit line.
- **Exports:** designs export as `name.ektypos.json` with the format label `ektypos`.
- **Offline cache:** the service worker also clears offline copies left by older versions.

## 3.3.0

13 November 2026. Licensing release, prepared for publication. No changes to printing.

## Name and license
- The program is now called **Ektypos**. The new name is used in the page title, app name, header, About dialog, test page, messages and install prompt.
- Ektypos is licensed under the **GNU Affero General Public License, version 3 or later**, Copyright (C) 2026 The Ektypos authors. The license notice is at the top of the HTML file.
- "Fichero" now appears only where it names compatible printers. The About dialog says that Ektypos is not affiliated with the maker or sellers of Fichero printers.

## About dialog
- It now shows the copyright, the license and the no-warranty statement.
- New **Source code** button. It downloads an unmodified copy of this page, which is the complete source code. Once the repository is public, set `SOURCE_URL` in the file and the button opens the repository instead. The AGPL requires this when the tool is offered to others over a network.
- New **Licenses** button. It shows the full third-party notices and the full AGPL-3.0 text. Both are embedded in the file, so every saved copy carries them.
- The credits are corrected and complete: qrcode-terminal (Apache 2.0) and zxing-cpp (Apache 2.0, PDF417 table) are added, and icon changes are stated. The 0xMH/fichero-printer credit now says "protocol documentation consulted", because no code was taken from it.
- The embedded GUST Font License is version 1.0 (2009), the current text. The licence of TeX Gyre Adventor is confirmed in its readme.

## Fonts
- **New: Sans (Arial metrics)**, based on Liberation Sans. Earlier versions listed Liberation Sans but did not include it, so labels used whatever sans-serif font the device had. Labels using it now look the same on every device.
- Fonts with reserved names are renamed, as their license requires for modified copies:

| Before | Now | Shown as |
|---|---|---|
| Lora | Ektypos Book | Book serif |
| Liberation Serif | Ektypos Serif | Serif (Times metrics) |
| Liberation Mono | Ektypos Mono | Mono (Courier metrics) |
| Liberation Sans (not embedded) | Ektypos Sans | Sans (Arial metrics) |

- The letter shapes are unchanged. Saved designs, templates and imported files that use the old font names switch to the new names automatically when they open.

## Icons
- Brand and logo icons are removed: 242 from Material Design Icons, 4 Font Awesome logos, and 4 GitHub marks from Octicons (logo-github, mark-github, logo-gist, copilot). 9,793 library icons and the 80 built-in icons remain.
- A design that uses a removed icon can no longer show it.
- The app icon (favicon, home-screen icon) is the new Ektypos icon.

## Files
- File names now start with `ektypos-v3.3.0` (now `ektypos-v3.3.1`): the HTML file, the web manifest, the service worker and the icons.
- Exported designs are saved as `name.ektypos.json` with the format label `ektypos`. Older `.fichero.json` exports still import.
- The internal storage keys are unchanged, so saved designs, templates and settings stay in place.
- The file is about 95 KB larger (2.44 MB), mostly because of the embedded license texts and the Sans font.

## Tested
In Chromium:
- All four renamed fonts load.
- The font picker shows the new names, and old font names are mapped to the new ones.
- The brand icons are gone and the other icons still load.
- The About and Licenses dialogs work.
- There are no script errors.
