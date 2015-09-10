# mediamock

Mediamock provides mocking of folders and (image) files.

Current use case: Magento's media folder, containing all images, pdf, etc
for an online shop, can have a pretty nice total byte size, up to several
GB or even TB. Copying these files to your development environment takes
a long time and consumes lots of precious disk space.

## Mediamock has two run modes:

1. First analyze and store the folder structure on the server.
2. Download the stored structure onto your development machine
and recreate the folder and files.

### Run mode: Analyze

THe program will recursively walk through the folders and stores
each file including path, image width & height and modification 
date in a simple CSV file.

The analyze mode will be triggered as soon as the program detects a 
local folder.

### Run mode: Mock

The mock mode will read the CSV file and creates all the folders and
files including correct creation and modification date.
For images it creates an empty image with the width and height.
The image may contain nothing or a watermark or random generated structure
or Chuck Norris jokes or cats.

The mock mode will be triggered as soon as the program detects an 
URL or local path with a .csv suffix.

The mocked images should be as small as possible. All other non-image
files are of size 0kb.

## Future TODOs

Run as gRPC server and allow clients to trigger the analyze steop
once connected to the server.

## Install

Download binaries or `go get -u github.com/SchumacherFM/mediamock` or
`go install github.com/SchumacherFM/mediamock`.

## License

Copyright (c) 2015 Cyrill (at) Schumacher dot fm. All rights reserved.

[Cyrill Schumacher](https://github.com/SchumacherFM) - [My pgp public key](http://www.schumacher.fm/cyrill.asc)
