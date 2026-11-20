# PvZ: Advance / LawnTV game assets

Loose game assets (sprites, reanimations, sounds, music, fonts, shaders and the
XML manifests) used by the native port in
[PvZ-AndroidTVDecomp](https://github.com/IsraelDXPP/PvZ-AndroidTVDecomp) and by
the CI system in [PvZ-Advance-CI](https://github.com/IsraelDXPP/PvZ-Advance-CI).
They live in a separate repository only because of their size; the code is not
here.

The layout is the one the game expects inside `assets/files/`:

* `properties/` - `resources.xml`, `levels.xml`, `LawnStrings.txt` and friends
* `images/`, `reanim/`, `addonFiles/` - artwork
* `sounds/`, `music/`, `movies/` - audio and the intro movie
* `data/` - fonts
* `particles/`, `shaders/`, `compiled/` - particle effects, bgfx shader packages
  and the compiled reanimations

CI downloads the branch archive
(`https://github.com/IsraelDXPP/PvZ-Advance-Assets/archive/refs/heads/main.tar.gz`),
strips its top directory and copies the content to the asset directory of each
target.

`.gitattributes` pins `-text` so Git never rewrites line endings inside these
files; the game reads some of them byte for byte.
