# tev

High dynamic range (HDR) image viewer for people who care about colors.

This repo hosts the flatpak version of [tev](https://github.com/tom94/tev),
available at [Flathub](https://flathub.org/en/apps/io.github.tom94.tev).

As a safe, sandboxed flatpak, **tev** comes *without* network and filesystem access by default.
However, **tev** has several features that work best with network and filesystem permissions enabled.

You can use [Flatseal](https://flathub.org/en/apps/com.github.tchx84.Flatseal) to manage the permissions via a GUI, or
use the following command line
```sh
flatpak override --user --share=network --filesystem=host:ro io.github.tom94.tev
```

Enabling these permissions unlocks the following features:

## Network access

**tev** can communicate with other instances running on the same machine. For example,
if **tev** is already running and you open another image, it will show up in the existing
instance instead of opening a new window.

Another use case is remote control: compatible rendering software (like [PBRTv4](https://github.com/mmp/pbrt-v4)) can send rendered images directly to a running instance of **tev**.
There are also SDKs for various programming languages that allow you to send images to **tev** from your own software.
- [C/C++](https://github.com/westlicht/tevclient), [Python](https://github.com/tom94/tevclient), [Rust](

## Read-only filesystem access

- You can open images directly from the command line, e.g. `flatpak run io.github.tom94.tev /path/to/image.exr /folder/with/images/`.
- **tev** can watch files for changes and automatically reload them when they are modified.
- Your cursor theme will be applied in **tev**, even if the theme itself is not a flatpak.

**Note:** even without filesystem access, **tev** can open and save files via drag-and-drop and file dialogs.
