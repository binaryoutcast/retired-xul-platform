# Retired XUL Platform (RXP)

This repository holds the code for a lightly modified incarnation of the [Unified XUL Platform](https://repo.palemoon.org/MoonchildProductions/UXP) adapted for retired BinOC XUL Apps. The modifications to the platform herein also open it to alt configurations and improve the quality of life aesthetically and functionally where possible.

## Why?

Reference, example, shuffleboard, accessing an old profile, tinkering on things like the Borealis Navigator which is not only the most popular BinOC Project despite being vaporware (since it has never been released) but also somehow has a tangibly existing downstream ecosystem, which seems impossible. Also, people seemed to like Interlink too.

Well now YOU can build 'em and give them a future in part or in full for yourself or others, sans branding, of course, if you distribute. Though, I may be persuaded by passion, commitment, and good old fasioned American dollars to part with my beloved brands. Inquire if you care unless you don't.

## Should I be using it?

Maybe, it depends. Perhaps you should check out https://thereisonlyxul.org/ before making that decision. There are quite a number of UXP applications there already.

## Isn't this all old and insecure?

Only as old and insecure as the Unified XUL Platform, and that IS properly security patched. If those patches are in this tree when you build? It's likely secure enough but this is why it depends ;)

## But I want old stuff on even older stuff like XP?

That isn't a question. Still, you best get to it. I'd totally consider a non-blocking branch for a legit effort but I'd only be doing overseeing and occasional testing, when I get around to it. So if you bust the tree, you have to fix it. Same goes for other os as well. Other than Windows and Linux that is.

## How do I build it cause you aren't doing exactly what *they* do?

### Dependancies

- Same as the Unified XUL Platform, see Windows and Linux build instructions on [DPMO](https://developer.palemoon.org/build/).
- Proper build instructions along with a modified windows build toolchain will follow soonish. Linux should have no difficulties.

### mozconfig

Now you have the same power I did when I was producing these applications and testing other UXP projects. The Binary Outcast Super Mozilla Configuration File! Just set a few simple variables or tell it to go away and use your own full configuration. The choice is yours! The complicated bits are in `./aura/config/binoc.inc.mozconfig` if you are interested.

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

## Tired of XUL already?

 See https://github.com/binaryoutcast/markIII-dev for the FUTURE!
