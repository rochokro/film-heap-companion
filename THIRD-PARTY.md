# Bundled software

The companion contains unmodified official Windows x64 runtime binaries. It never distributes an installed user's Jellyfin server, its database, account configuration or API keys.

* **Node.js 24.21.0**, from https://nodejs.org/dist/v24.21.0/. The upstream distribution checksum is checked before packaging. `runtime/NODE-LICENSE.txt` contains Node.js and its bundled dependency notices. Corresponding source: https://nodejs.org/dist/v24.21.0/node-v24.21.0.tar.xz.
* **Jellyfin FFmpeg 8.1.3-1**, the official portable Windows clang GPL release from https://github.com/jellyfin/jellyfin-ffmpeg/releases/tag/v8.1.3-1. The upstream asset SHA-256 is checked before packaging. `runtime/FFMPEG-COPYING-GPLv3.txt` contains its GPL v3 license. Source, patches and build recipes: https://github.com/jellyfin/jellyfin-ffmpeg/tree/v8.1.3-1. Upstream FFmpeg source: https://ffmpeg.org/releases/ffmpeg-8.1.3.tar.xz. The GPL distribution is used; no locally modified or nonfree encoder build is substituted.
* Server dependencies are installed from the application's locked production dependency graph. Their license and notice files accompany the modules in `node_modules`.

Node and FFmpeg run as separate processes. Installation stays in the current Windows user's local application-data folder, requires no administrator elevation, and does not install a system service or open firewall ports.

The app's Windows launcher is not yet Authenticode signed. The download page reports this rather than claiming a verified publisher. Do not disable Windows security protections to install it.
