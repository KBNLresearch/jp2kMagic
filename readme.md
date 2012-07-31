## Contents of this repository
This repository contains:

1. Updated *magic* signatures for the *JPEG 2000* family of file formats. This allows *File* to distinguish between the *JP2*, *JPX*, *JPM* and *MJ2* formats. 
2. A small set of sample images that represent each of the above formats.

##*Magic* signatures
The directory [*magic*][magic] contains the following files:

+ [*Magic file with JPEG 2000 signatures*][magicUncompiled] (uncompiled)
+ [*Magic file with updated JPEG 2000 signatures*][magicCompiled] (compiled)

Note that these signatures are intended as a replacement of the existing *JPEG 2000 image data* signature by David Santinoli (on which it is based). They *only* contain the new *JPEG 2000* signatures (i.e. the ones for *JP2*, *JPX*, *JPM* and *MJ2*), and do not include a signature for JPEG 2000 codestreams (this already exists).

### Compiling on your own system
Download the uncompiled file (`jpeg2000Magic`) and compile it using:

`file -C -m jpeg2000Magic`

This should produce a compiled *magic* file called `jpeg2000Magic.mgc` which can be used as input to *File* by using its `-m` switch.

##JPEG 2000 sample images
The directory [*sampleImages*][sampleImages] contains one sample image for each of the *JPEG 2000* file formats:

+ [*balloon.jp2*][sampleJP2] - [JPEG 2000 Part 1][JP2] (JP2) image, created using [Aware JPEG 2000 SDK][Aware] <sup>*</sup>

+ [*balloon.jpf*][sampleJPX] - [JPEG 2000 Part 2][JPX] (JPX) image, created using [Kakadu][Kakadu] 6.4 *

+ [*balloon.jpm*][sampleJPM] - [JPEG 2000 Part 6][JPM] (JPM) image, created using [Luratech JPEG 2000 plugin][Luratech] for [IrfanView][IrfanView] <sup>*</sup>

+ [*Speedway.mj2*][sampleMJ2] - [JPEG 2000 Part 3][MJ2] (MJ2) video (aka "motion JPEG 2000"), created using [OpenJPEG][OpenJPEG] <sup>\#</sup>

## Known issues
*JPX* images that were create in *Photoshop* using *Adobe*'s *JPEG 2000* plugin wil be identified as *JP2*. This is because the plugin inserts a wrong value in the 'brand' field of these files. This is simply a bug in the plugin and not a fault of these signatures.    

----

<sup>*</sup>Created from the following source image: 


[http://commons.wikimedia.org/wiki/File:1783_balloonj.jpg](http://commons.wikimedia.org/wiki/File:1783_balloonj.jpg "http://commons.wikimedia.org/wiki/File:1783_balloonj.jpg")

> 1786 description of the historic Montgolfier Brothers' 1783 balloon flight. Illustration with engineering proportions and description.

Public Domain.

<sup>#</sup>Source: 
[http://www.openjpeg.org/samples/Speedway.mj2](http://www.openjpeg.org/samples/Speedway.mj2 "http://www.openjpeg.org/samples/Speedway.mj2")


[JP2]:http://www.jpeg.org/public/15444-1annexi.pdf
[JPX]:http://www.jpeg.org/public/15444-2annexm.pdf
[JPM]:http://www.jpeg.org/public/fcd15444-6.pdf
[MJ2]:http://www.jpeg.org/public/fcd15444-3.pdf

[Aware]:http://www.aware.com/imaging/jpeg2000sdk.html
[Kakadu]:http://www.kakadusoftware.com/
[Luratech]:https://www.luratech.com/en/products/imaging-solutions/additional-imaging-solutions.html
[IrfanView]:http://www.irfanview.com/
[OpenJPEG]:http://www.openjpeg.org/

[sampleJP2]:./sampleImages/balloon.jp2
[sampleJPX]:./sampleImages/balloon.jpf
[sampleJPM]:./sampleImages/balloon.jpm
[sampleMJ2]:./sampleImages/Speedway.mj2
[sampleImages]:./sampleImages/
[magic]:./magic/

[magicUncompiled]:./magic/jpeg2000Magic
[magicCompiled]:./magic/jpeg2000Magic.mgc