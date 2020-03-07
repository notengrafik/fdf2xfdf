# fdf2xfdf

Converts exported PDF annotations from FDF to XFDF. Support for forms data is marginal.

## Motivation

Directly working with FDF is not fun. It's much easier with XFDF and existing XML support in your tool of choice.
However, XFDF doesn't seem to receive much love from PDF software such as Foxit Reader, hence the need for a converter.

## Current state

In the current state, this tool supports just what I need to scratch my own itch. It is not very robust and supports only a subset of the existing annotation types and properties. If you need more, feel free to contribute or to contact us.

## How to use

This PostScript program can be run on the command line with [Ghostscript](http://ghostscript.com/).

### Mac/Linux

    gsnd -q fdf2xfdf.ps annots.fdf > annots.xfdf

### Windows

    gswin64c -dNODISPLAY -q fdf2xfdf.ps annots.fdf > annots.xfdf

(Or `gswin32c` for the 32 bit version.) This requires that the GhostScript executables are on the `PATH` environment variable. Alternatively, specifiy the full path to `gswin32c.exe`, e.g.

    "C:\Program Files\gs\gs9.21\bin\gswin64c.exe" -dNODISPLAY -q fdf2xfdf.ps annots.fdf > annots.xfdf

## What about forms?

**fdf2xfdf** is at the moment *not* directed towards forms data, though marginal support is present. See various other tools for alternatives, e.g.:

* https://www.adobe.com/devnet/acrobat/fdftoolkit.html
* https://www.php.net/manual/en/ref.fdf.php

## Why is this written in PostScript?

As PostScript is sort of the older brother of PDF, it shares a lot of DNA with PDF - such as syntax, types and data structures. FDF parsing virtually comes for free with PostScript.
