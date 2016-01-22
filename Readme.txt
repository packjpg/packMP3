packMP3 v1.0g (01/22/2016)
~~~~~~~~~~~~~~~~~~~~~~~~~~

packMP3 is a compression program specially designed for further 
compression of MPEG-1 Audio Layer III audio files without causing any 
further loss. Typically it reduces the file size of a MP3 file by 16% 
based on tests with 6000 randomly selected files. 


LGPL v3 license and special permissions
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

All programs in this package are free software; you can redistribute 
them and/or modify them under the terms of the GNU Lesser General Public 
License as published by the Free Software Foundation; either version 3 
of the License, or (at your option) any later version. 

The package is distributed in the hope that it will be useful, but 
WITHOUT ANY WARRANTY; without even the implied warranty of 
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU Lesser 
General Public License for more details at 
http://www.gnu.org/copyleft/lgpl.html. 

If the LGPL v3 license is not compatible with your software project you 
might contact me and ask for a special permission to use the packMP3 
library under different conditions. In any case, usage of the packMP3 
algorithm under the LGPL v3 or above is highly advised and special 
permissions will only be given where necessary on a case by case basis. 
This offer is aimed mainly at closed source freeware developers seeking 
to add PMP support to their software projects. 

Copyright 2010...2014 by Ratisbon University and Matthias Stirner. 


Usage of packMP3
~~~~~~~~~~~~~~~~

MP3 files are compressed and PMP files are decompressed using this
command:

 "packMP3 [file(s)]"

packMP3 recognizes file types on its own and decides whether to compress
(MP3) or decompress (PMP). For unrecognized file types no action is
taken. Files are recognized by content, not by extension.

packMP3 supports wildcards like "*.*" and drag and drop of multiple 
files. Filenames for output files are created automatically. In default
mode, files are never overwritten. If a filename is already in use,
packMP3 creates a new filename by adding underscores.

If "-" is used as a filename input from stdin is assumed and output is 
written to stdout. This can be useful for example if the lame encoder is 
to be used as a preprocessor. 

Usage examples:

 "packMP3 *.pmp"
 "packMP3 luca.mp3"
 "packMP3 song??.pmp"
 "packMP3 - < sail.pjg > sail.jpg"


Command line switches
~~~~~~~~~~~~~~~~~~~~~

 -ver  verify files after processing
 -v?   level of verbosity; 0,1 or 2 is allowed (default 0)
 -np   no pause after processing files
 -o    overwrite existing files
 -p    proceed on warnings

By default, compression is cancelled on warnings. If warnings are 
skipped by using "-p", most files with warnings can also be compressed, 
but MP3 files reconstructed from PMP files might not be bitwise 
identical with the original MP3 files. There won't be any loss to audio 
data or quality however.

There is no known case in which a file compressed by packMP3 (without 
the "-p" option, see above) couldn't be reconstructed to exactly the 
state it was before. If you want an additional layer of safety you can 
also use the verify option "-ver". In this mode, files are compressed, 
then decompressed and the decompressed file compared to the original 
file. If this test doesn't pass there will be an error message and the 
compressed file won't be written to the drive. 

Please note that the "-ver" option should never be used in conjunction 
with the "-p" option. As stated above, the "-p" option might lead to 
reconstructed MP3 files not being bitwise identical to the original MP3 
files. In turn, the verification process may fail on various files 
although nothing actually went wrong. 

Usage examples:

 "packMP3 -v1 -o luca.pmp"
 "packMP3 -ver luca.mp3"
 "packMP3 -p *.mp3"


Known Limitations 
~~~~~~~~~~~~~~~~~ 

packMP3 is a compression program specially for MP3 files, so it doesn't 
compress other file types.

Please note that MP3 may stand for three different audio file types: 
MPEG-1 Audio Layer III, MPEG-2 Audio Layer III and MPEG-2.5 Audio Layer 
III. Only the first type is supported by packMP3. The file types may not 
be distinguished by their extension (which would be '.mp3' for each of 
them) but by their sample rates when playing in audio player software. 
Only MPEG-1 Audio Layer III supports sample rates of 32kHz and above. 

packMP3 has low error tolerance. MP3 files might not work with packMP3 
even if they work perfectly with audio player software. The command line 
switch "-p" can be used to increase error tolerance and compatibility. 

If you try to drag and drop to many files at once, there might be a 
windowed error message about missing privileges. In that case you can 
try it again with less files or consider using the command prompt. 
packMP3 has been tested to work perfectly with thousands of files from 
the command line. This issue also happens with drag and drop in other 
applications, so it might not be a limitation of packMP3 but a 
limitation of MS Windows. 

Compressed PMP files are not compatible between different packMP3 
versions. You will get an error message if you try to decompress PMP 
files with a different version than the one used for compression. You 
may download older versions of packMP3 from: 
http://www.placeholder.com/packMP3/binaries/old/ 


History
~~~~~~~

v1.0 (01/09/12) (non public)
 - first released version
 - only for testing purposes
 
v1.0c (04/13/12) (public)
 - some minor bugfixes
 - changed the library interface a little
 - first public version!
 
v1.0d (09/28/13) (public)
 - packMP3 is now open source under the terms of the GPL v3

v1.0e (01/15/14) (public)
 - various source code optimizations (using cppcheck)
 
v1.0f (11/21/14) (public)
 - packMP3 licensing changed to LGPL v3
 - some minor bugfixes
 
v1.0g (01/22/16) (public)
 - Updated contact info
 - fixed a minor bug

 
Acknowledgements
~~~~~~~~~~~~~~~~

packMP3 is the result of countless hours of research and development. It 
is part of my master thesis for Ratisbon University, which was 
supervised by Prof. Dr. Christian Wolff. Thanks go to him for giving me 
such an interesting topic to work on and for all the helpful advice 
during my time working on the thesis. 

Prof. Dr. Gerhard Seelmann from Hochschule Aalen introduced me to the 
field of data compression when I was still studying at HTW Aalen 
University. Without him, neither packJPG nor packMP3 would have been 
possible. 

Thanks goes to Stephan Busch of SqueezeChart.com fame for spending many, 
many hours beta-testing packMP3. He's the one to thank for packMP3 
running smoothly and not causing you any trouble. 

packMP3 logo and icon are designed by Michael Kaufmann.


Contact
~~~~~~~

The official home of packMP3:
 http://packjpg.encode.ru
 
For questions and bug reports:
 packjpg (at) matthiasstirner.com


____________________________________
packMP3 by Matthias Stirner, 01/2016
