# fdf2xfdf

Convert PDF annotation exports from FDF to XFDF

Directly working with FDF is not fun. It's much easier with XFDF and existing XML support in your tool of choice.
However, XFDF doesn't seem to receive much love from PDF software such as Foxit Reader, hence the need for a converter.

In the current state, this tool supports just what I need to scratch my itch. It is not very robust and supports only a subset of the existing annotation types and properties. If you need more, feel free to contribute or to contact us.

## How to use

As FDF syntax is virtually a subset of PostScript syntax and PostScript is a programming language, it seemed natural to write this tool in PostScript where we get parsing for free. It can be run with Ghostscript:

    gsnd -q fdf2xfdf.ps my_annotations.fdf > my_annotations.xfdf

## What about forms

**fdf2xfdf** is at the moment not directed towards forms data - forms are already well supported by various tools.