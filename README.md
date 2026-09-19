# Batcap

A BatMUD client that draws the map, keeps the triggers and remembers the
characters, in one window with nothing to configure on a command line.

It talks to `batmud.bat.org:2022` over TLS, speaks the BatClient protocol the
game already sends, and works whether or not you give it a map.

## Download

Take the package for your machine from
[Releases](../../releases/latest), unzip it, and read the `README.txt` inside —
it is two pages and it is written for somebody who has not seen any of this.

| | |
|---|---|
| **Windows** | `Batcap-<version>-windows.zip` — double-click `Batcap-amd64.exe` |
| **macOS** | `Batcap-<version>-macos.zip` — drag `Batcap.app` to Applications |

Both are unsigned. Windows may quarantine the exe without saying so; macOS
will refuse the app until you right-click it and choose Open. That is what an
unsigned build is, and there is no way around it that does not involve buying
a certificate.

## What is in the package

```
Batcap-<version>-windows/
  Batcap-amd64.exe        the client
  Batcap-arm64.exe        for an ARM machine, and only for one
  batcap/                 copy this into your home directory
    areas/                Arelium and the newbie areas, about 600 rooms
    triggers/rules.json   five example triggers
  README.txt
```

The `batcap` folder is where the client keeps everything: settings, your
characters, the map it draws, the triggers it runs. Copying it in gives you a
map on the first screen and something to read in the trigger editor. You do not
have to — without it the client plays perfectly well, draws no map, and says so
rather than leaving you wondering.

## The map

Two maps, and they are different things.

**The archive** is the world as somebody else already walked it. The package
carries the corner of it a new character sees. The whole archive is about three
hundred areas and is not this client's to hand out: it is exported from the
SuperBat plugin, by you, from your own copy. Export it, then point
*Settings → connection & files* at the folder.

**The map it draws itself** is everywhere the archive does not have. It records
rooms as you walk them, works out which way the doors go, and is yours. That
one needs nothing.

## Your passwords

Ask it to remember a character and the password is sealed with a key in
`batcap/.key`, not readable out of the file it is stored in. Carry both or
neither.

## Help

Everything the client can do is in the client. Press **Help** on the bar, or
type `$help` at the prompt.

    $help          every command there is
    $help $sail    one of them, in full, with examples
