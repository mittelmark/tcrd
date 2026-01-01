# tcrd

[![license](https://img.shields.io/badge/license-BSD-lightgray.svg)](https://opensource.org/license/bsd)
[![Release](https://img.shields.io/github/v/release/mittelmark/tcrd.svg?label=current+release)](https://github.com/mittelmark/tcrd/releases)
![Downloads](https://img.shields.io/github/downloads/mittelmark/tcrd/total)
![Commits](https://img.shields.io/github/commits-since/mittelmark/tcrd/latest)
[![Docu Package](https://img.shields.io/badge/Docu-Package-blue)](http://htmlpreview.github.io/?https://github.com/mittelmark/tcrd/blob/master/tcrd/tcrd.html)

Writing chord sheets from lyrics and chord diagrams using Tcl.

## Description

The package  _tcrd_ allow  you to write chord  sheets from lyrics with  embedded
chords and create svg graphics from short text descriptions like _0003_ for an
Ukulele C chord diagram or _xx0231_ for a Guitar Dm chord.

## Synopsis

```
package require tcrd
package require tsvg
tcrd transpose A 1 ;# - Bb
tcrd svgchord C 0003 -outfile uke-c.svg ;# Uke Chord
puts [tcrd chords {[Dm]Are you going to [C]Scarborough [Dm]Fair?}]
```

## Example

```{.tcl}
package require tcrd
tcrd svgchords C  x32010 -outfile guitar-c.svg -width 150
tcrd svgchords Dm xx0231 -outfile guitar-dm.svg -width 150
tcrd svgchords Em 022000 -outfile guitar-em.svg -width 150
tcrd svgchords F  x03211 -outfile guitar-f.svg -width 150
tcrd svgchords G  320003 -outfile guitar-g.svg -width 150
tcrd svgchords Am x02210 -outfile guitar-am.svg -width 150
```

![](assets/guitar-c.svg) ![](assets/guitar-dm.svg) ![](assets/guitar-em.svg) ![](assets/guitar-f.svg)
![](assets/guitar-g.svg) ![](assets/guitar-am.svg)

And here how we can create a chord sheet:

```{.tcl}
puts [tcrd chords {
[Dm]Are you going to [C]Scarborough [Dm]Fair? 
[F]Parsley, [Dm]sage, rose [F]mary [G]and [Dm]thyme 
Remember [F]me to one who [C]lives there 
[Dm]He once [C]was a true love of [Dm]mine
}]
```

Output:

```
Dm               C           Dm     
Are you going to Scarborough Fair?  
F        Dm         F    G   Dm     
Parsley, sage, rose mary and thyme  
         F             C            
Remember me to one who lives there  
Dm      C                  Dm   
He once was a true love of mine 
```

## Changes

- __2026-01-01 - v0.0.1__ - initial release as Tcl package

## SEE ALSO

- [tsvg](https://github.com/mittelmark/tsvg) - writing svg files with Tcl
- [mndoc](https://github.com/mittelmark/mndoc) - converting Markdown output of
  tmdoc to HTML
- [tmdoc](https://github.com/mittelmark/tmdoc) - literate programming with Tcl
  using the _tcrd_ package to display music chord sheets and chord diagrams

## AUTHOR

@ 2025 - Detlef  Groth,  University  of  Potsdam,  Germany  - dgroth(at)uni(minus)potsdam(dot)de

## LICENSE

```
BSD 3-Clause License

Copyright (c) 2020-2025, Detlef Groth, University of Potsdam, Germany

All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

1. Redistributions of source code must retain the above copyright notice, this
   list of conditions and the following disclaimer.

2. Redistributions in binary form must reproduce the above copyright notice,
   this list of conditions and the following disclaimer in the documentation
   and/or other materials provided with the distribution.

3. Neither the name of the copyright holder nor the names of its
   contributors may be used to endorse or promote products derived from
   this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
```
