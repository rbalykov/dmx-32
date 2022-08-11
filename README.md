# dmx-multiverse

Project goal: upgrade *de-facto* dmx-512 use-case over show industry.
Project profit: extracting more bandwidth from ready-made tonns of hadware (consoles, dongles, cable, fixtures).

Physycal layer circuitry uses *MAX 485-like* ICs. 

1) The *slope-limited* 485 ICs are bound to DMX's 250 kbaud, thus allowing to forget many headaches using *ugly cheap almost-broken* cables.
2) Faster 485 ICs are able to drive 2/6/10 Mbaud. Sure, this time cables can't be *almost-broken*, but *ugly cheap* ones still can do good.

Successor hardware use-cases could look like:

1) Quater megabaud: *Old good DMX-512/RDM using old good splitter and wires.* Damn slow, no parity checks, but still able to drive a kilometer of cable.

2) Megabaud: *bigger frames, more universes* - this aspect better to be flexible, but it's 4 times faster. Definetely. *WS2812 Led Pixels* finely fit this baudrate too.

3) Quad/Octa megabaud - even more universes, full-duplex RS-422 topology (not half-duplex RS-485), sure parity checks, frame checksums, closed-loop topology, etc. As a penalty - it can't be an *ugly and cheap* kilometer cable, but fine Cat5/6 seems to be a good idea.
