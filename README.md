# Retired XUL Platform (RXP)

![image](https://github.com/binaryoutcast/retired-xul-platform/assets/3889475/d2f2e2ea-dac6-4b32-82c5-fd716a826b75)

This repository holds the code for a lightly modified incarnation of the [Unified XUL Platform](https://repo.palemoon.org/MoonchildProductions/UXP) adapted for retired BinOC XUL Apps. The modifications to the platform herein also open it to alt configurations and improve the quality of life aesthetically and functionally where possible.

## Why?

Reference, example, shuffleboard, accessing an old profile, tinkering on things like the Borealis Navigator which is not only the most popular BinOC Project despite being vaporware (since it has never been released) but also somehow has a tangibly existing downstream ecosystem, which seems impossible. Also, people seemed to like Interlink too.

## Should I be using it?

Maybe, it depends. Perhaps you should check out https://thereisonlyxul.org/ before making that decision. There are quite a number of UXP applications there already.

But if none of those meet your requirements then try your hand at building your self your own DIY release of this incomplete xul software.

## Isn't this all old and insecure?

Only as old and insecure as the Unified XUL Platform, and that IS properly security patched. If those patches are in this tree when you build? It's likely secure enough but this is another reason why it depends ;)

## How do I build it cause you aren't doing exactly what *they* do?

### Dependancies

- Same as the Unified XUL Platform, see Windows and Linux build instructions on [DPMO](https://developer.palemoon.org/build/).
- https://github.com/binaryoutcast/retired-xul-platform/releases/tag/AURABUILD_5.1.0a2 (download the attached 7zip archive) for builds on Windows instead of MozillaBuild 3.4.

### mozconfig

Now you have the same power I did when I was producing these applications and testing other UXP projects. Next is the Binary Outcast Super Mozilla Configuration File! Just set a few simple variables or tell it to go away and use your own full configuration. The choice is yours! The complicated bits are in `./aura/config/binoc.inc.mozconfig` if you are interested.

```
# Application to build
_APP=navigator

# Branding to use (if not specified in the logic of this mozconfig it will be app/branding/branddir
_BRANDING=release

# Enable the updater
_UPDATER=

# Enable Debugging (There are remaining asserts that may insta-crash)
_DEBUG=

# Number of processes to spawn when compiling. BinOC normally has number of cores (or threads) minus two
_CORES=10

# 64-bit target
_X64=1

# GTK Version (2 or 3)
_GTK=2

# This is the prefix of where you want object directories stored. BinOC uses ../.obj
_OBJDIR_PREFIX=../.obj

# This enables extended optimization flags used by BinOC Internally.
_BINOC_OPTZ=

# =====================================================================================================================

. ./aura/config/binoc.inc.mozconfig
```

`./mach build`

`./mach package` on Linux or `./mach installer` on Windows

Additionally, one can do `./mach install` even on windows with the never-broken gre-packaging I created out of the much larger and overly complex out of date mozilla packaging.

![image](https://github.com/binaryoutcast/retired-xul-platform/assets/3889475/422e3e8a-6b43-4aea-ae24-6b5ecfc957f8)

## Tired of XUL already?

 See https://github.com/binaryoutcast/markIII-dev for the FUTURE!
