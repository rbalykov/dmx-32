# Project: dmx-multiverse

#### The goal: upgrade *de-facto* dmx-512 use-case over show industry.
#### The profit: extracting more bandwidth from ready-made tonns of hadware (consoles, dongles, cable, fixtures).

## DMX-512 flaws
* While DMX hardware can distribute 10 Mbit over the stage (WS2812 LEDs need 1 Mbit, as instance), it takes just 250 Kbit to carry.
* Frame size is limited to 512 slots. Far in 1989, that was enough to drive tungsten-lamp dimmers, but not now-day's multimedia.
* Framerate done ugly - using full frame, it gives 44 fps, unclearly bound to TV's 25/30. Bounding to 50/60 could be done reducing slots count.
* Modem baudrates can't be used, leaving some UART hardware useless as DMX application.

## Physical layer 

Over the world, circuitry uses *MAX 485-like* ICs. 
1) The *slope-limited* 485 ICs are bound to DMX's 250 kbaud, thus allowing to forget many headaches using *ugly cheap almost-broken* cables.
2) Faster 485 ICs are able to drive 2/6/10 Mbaud. Sure, this time cables can't be *almost-broken*, but *ugly cheap* ones still can do good.

## Possible successor layer

1) Quater megabaud: *Old good DMX-512/RDM using old good splitter and wires.* Damn slow, no parity checks, but still able to drive a kilometer of cable.

2) Megabaud: *bigger frames, more universes* - this aspect better to be flexible, but it's 4 times faster. Definetely. *WS2812 Led Pixels* finely fit this baudrate too.

3) Quad/Octa megabaud - even more universes, full-duplex RS-422 topology (not half-duplex RS-485), sure parity checks, frame checksums, closed-loop topology, etc. As a penalty - it can't be an *ugly and cheap* kilometer cable. As a life-hack, 1/3 kilometer roll of *FTP Cat5/6 cable* fits (A) couple os RS-422 lanes (B) quad RS-485 lanes (C) Whatever else, analog or digital, that fits 100-700 MHz range. 

## Refactors
### Baudrate, framing, startcode magic
#### Modem baudrates
#### XLR cable rates
* 250kHz 500k 1MHz 2M 4M 8M 
#### Cat5/6 rates 
* 16M 32M 64M 128M 256M 512M 1G
250kHz uses starcode 0x00, as before

DMX-512 at multiple speed mode uses startcode 0x00 once per 250kHz-timed frame, the rest frames use SC *not equal to 0x00*

### RS-422, closed-loop topology
5-pin cable goes true 5-wired as default, allowing to replace RS-485 half-duplex with RS-422 full-duplex.
Having full-duplex line, system is capable for *closed-loop* topology, giving tight mechanic control over DMX hardware you already have (you still need new 5-pin RS-422 DMX splitter)

### Checksum and parity checks
You know, this story is about kilometer-long cables again.

Checking framing integrity is nice add-on for that story.
