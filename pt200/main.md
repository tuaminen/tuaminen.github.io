# Background

I had bought a Roland JX-3P, and I wanted to have the PG-200 programmer for it. Programmers are very expensive though, so I decided to try to build my own.

The PG-200 protocol was documented [here](https://atosynth.blogspot.com/2015/05/free-pg-200.html), but it contained some things that were not clear enough for implementing the protocol. So I had to do some additional protocol reverse-engineering.

The PG-200 hardware serial interface between the synth and the programmer is pretty straightforward, and can be found from JX-3P service manual.


# PT-200

My version consists of Arduino Nano, MIDI interface and bunch of analog and digital inputs. In addition to Arduino's own inputs, I used two SPI multiplexers for additional inputs.


## Version 1

Version 1.0 has finished around 3/2021. This was the first PCB I had designed myself and fabricated in China. 

My PCB design skills were very limited, but hardware itself was working.


#### First PCBs received from China
![](/images/pt200/v1_pcbs.jpg)

#### A bit of building
![](/images/pt200/v1_first_tests.jpg)

#### Working proto
![](/images/pt200/v1_working_proto_b.jpg)

#### Working proto with the wire mess
![](/images/pt200/v1_working_proto_c.jpg)


## Version 2

To avoid the wire mess, I wanted to create v2.0 that would include the controls within the PCB.

#### Board design
![](/images/pt200/v2_top_black.jpg)

#### Complete build with JX-3P
![](/images/pt200/v2_pt200.jpg)

#### Comparison to PG-200. I eventually got an original PG-200 too.
![](/images/pt200/v2_pt200_and_pg200.jpg)


## Version 3 (future)

V3.0 has been in the works for a long time now, because there are things that could be improved:
- use matrix to read IO inputs to save IO pins
- Use SMD components for multiplexers instead of breakout boards
- Manufacture (almost) ready-built boards
- Case 
- Additional features (presets etc.)

Hopefully I can get it finished and release this to the world.

