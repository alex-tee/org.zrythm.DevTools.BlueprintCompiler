# Blueprint-Compiler Flatpak

Flatpak build of Blueprint Compiler by jwestman.

## Maintainer notes:

Intended for Zrythm maintainers or experienced users.

Build:

Prerequisites:
Assuming you have Flathub installed, along with `flatpak` and `flatpak-builder`.
```
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

1. Clone the repo
```
git clone --recurse-submodules https://github.com/flathub/org.zrythm.DevTools.BlueprintCompiler
cd flathub
```

2. Build the Flatpak
```
flatpak-builder --repo=zrythm --force-clean --install-deps-from=flathub --ccache --user build-dir org.zrythm.DevTools.BlueprintCompiler.json
```

3. Add the local repo and install the Flatpak
```
flatpak remote-add --user zrythm zrythm --no-gpg-verify
flatpak install --user zrythm org.zrythm.DevTools.BlueprintCompiler
```
4. Run the Flatpak build
```
flatpak run org.zrythm.DevTools.BlueprintCompiler
```

Optionally after steps 1-3 you can build and install [a bundle](https://docs.flatpak.org/en/latest/single-file-bundles.html) with:
```
flatpak build-bundle zrythm zrythm.flatpak org.zrythm.DevTools.BlueprintCompiler
flatpak install zrythm.flatpak
```
