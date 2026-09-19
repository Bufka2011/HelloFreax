# HelloFreax

Demo package for the Freax (OpenComputers) `apt` package manager.
Installs a `hellofreax` command that prints "Hello, Freax!".

## Layout

- `DEBIAN/control` — package metadata (built with `dpkg-deb -b`)
- `bin/hellofreax.lua` — the program (installs to `/bin/hellofreax.lua`)
- `usr/man/hellofreax` — man page (installs to `/usr/man/hellofreax`)
- `pool/main/hellofreax_1.0_all.fpkg` — the built package archive
- `dists/freax/Release` — repository release file
- `dists/freax/main/binary-all/Packages` — package index

Built with the Freax `lib/fpkg.lua` archive writer, so the `.fpkg`
byte format is exactly what in-game `dpkg` reads. Indexes match what
in-game `apt-ftparchive` generates.

## Use as an apt source

On a Freax machine with an internet card, add to `/etc/apt/sources.list`:

```
deb https://raw.githubusercontent.com/Bufka2011/HelloFreax/main freax main
```

Then:

```
apt update
apt install hellofreax
hellofreax
```
