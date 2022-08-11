# dmx-multiverse

Standard proposal

The goal: upgrade *de-facto* picture over the industry to extract more bandwidth from ready-made tonns of hadware.

Basic circuitry uses *MAX_485-like* ICs. 
The *time-slope-limited* versions of them are bound to DMX's 250 kbaud, thus allowing to forget many headaches using *ugly cheap almost-broken* cables.
Faster ICs are able to drive up to 10 Mbaud, 40 times faster tnan DMX does. Sure, this time cables can't be *almost-broken*, but *ugly cheap* ones still can do good.

So possible future protocol jam could look like this:
1) Quater megabaud: *Old good DMX-512/RDM using old good splitter and wires.* Damn slow, no parity checks, but still able to drive a kilometer of cable.
2) Megabaud: *bigger frames, more universes* - this aspect better to be flexible, but it's 4 times faster. Definetely. *WS2812 Led Pixels* finely fit this baudrate too.
3) Quad/Octa megabaud - even more universes, full-duplex RS-422 topology (not half-duplex RS-485), sure parity checks, frame checksums, closed-loop topology, etc. As a penalty - it can't be an *ugly and cheap* kilometer cable, but fine Cat5/6 seems to be a good idea.

Feel free to edit/pull request tis document.
