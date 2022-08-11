# Project: dmx-multiverse

## The goal: upgrade *de-facto* dmx-512 use-case over show industry.

## The profit: extracting more bandwidth from ready-made tonns of hadware (consoles, dongles, cable, fixtures).

## Physycal layer 

Over the world, circuitry uses *MAX 485-like* ICs. 
1) The *slope-limited* 485 ICs are bound to DMX's 250 kbaud, thus allowing to forget many headaches using *ugly cheap almost-broken* cables.
2) Faster 485 ICs are able to drive 2/6/10 Mbaud. Sure, this time cables can't be *almost-broken*, but *ugly cheap* ones still can do good.

## Successor layer

1) Quater megabaud: *Old good DMX-512/RDM using old good splitter and wires.* Damn slow, no parity checks, but still able to drive a kilometer of cable.

2) Megabaud: *bigger frames, more universes* - this aspect better to be flexible, but it's 4 times faster. Definetely. *WS2812 Led Pixels* finely fit this baudrate too.

3) Quad/Octa megabaud - even more universes, full-duplex RS-422 topology (not half-duplex RS-485), sure parity checks, frame checksums, closed-loop topology, etc. As a penalty - it can't be an *ugly and cheap* kilometer cable. As a life-hack, 1/3 kilometer roll of *FTP Cat5/6 cable* fits (A) couple os RS-422 lanes (B) quad RS-485 lanes (C) Whatever else, analog or digital, that fits 100-700 MHz range. 

## Refactors
### Frame checksuming
