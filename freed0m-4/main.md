# FREED0M-4 Background

-After Sandst0rm-1 monosynth, I had an idea to build a new polyphonic synth with stereo sound.

To simplify the design, I decided to remove all computer-controlled parameters, so patch/preset support had to be forgotten.




 came to life
-No patch memory (no need to sample & generate all user controls)


The name was inspired by the war in Ukraine. I also wanted to use blue-yellow colors for the hardware.

# Features

- Analog signal path

- 4 voices:
	- VCO: triangle/pulse/saw, pulse PWM
    - 5 octaves
    - 3 octave offsets
    - Auto-tuning
    - Suboctave oscillator

- MIDI input
    - Velocity support
    - Pitch-wheel support
    - Aftertouch support
    - Modwheel support

- VCF:
    - 24dB Low-pass filter
    - Self-oscillating
    - Key follow
    - Bass boost compensation on lower frequencies

- Noise generator

- 2 x  envelopes:
    - VCA envelope (ADSR), modulates VCO / VCA
    - VCF envelope (ADSR), modulates VCF

- 3 x LFOs:
    - LFO1 analog: triangle/pulse/saw, PWM
    - Modulates VCO / VCF

    - LFO2 digital: triangle/pulse/saw/random/noise/…
    - Modulates VCO PWM

    - LFO3 digital: triangle/pulse/saw/random/noise/…
    - Modulates VCO / VCF / VCA / panning


- Stereo panning
    - stereo panning effects per voice
    - Various stereo modes

- Power:
    - 24V DC (ca. 300mA?), ca. 7W
    - Internal voltages:  +15V, -15V, +5V, -5V (, +3.3V)



## Voice boards

![](/images/freed0m4/voice.png)

There are 4 identical voice boards.

VCO Oscillator is based on CEM3340 from 1980 (clone by Alfa AS3340).

There are two ADSR envelopes (for VCA and VCF) CEM3310 from 1980 (clone by Alfa AS3310)

-Filter is CEM3320 from 1980 (clone by Alfa AS3320)

The voices are somewhat based on Sequential Pro-1 design.

VCF filter Bass boost is also similar to Prophet5/Pro-1

Suboscillator is based on 4040 binary counter. It counts oscillator’s pulse waves and counters binary values (suboctaves) are then summed together.


## Controls board

![](/images/freed0m4/controls.png)

This is a simple board for all the user controls and sending them to the Main board and Analog Input board.


## CPU board

![](/images/freed0m4/cpu.png)

The CPU board contains Arduino NANO (2k RAM, 1x EEPROM) as the main processor. The main idea was to keep this as a hardware project, not a software project. So I like to
use a minimal CPU for this.

CPU also contains several IO chips to generate various control signals for the synth:
- LTC1660 8x 10bit DAC (via SPI)
- TLC5628 8x 8bit DAC (via SPI)
- MCP23S17 16x IO (via SPI)
  
CPU is also connected to MIDI input interface (thru 6N137 optocoupler to Arduino Nano serial port), which is used to receive the notes.




This is a simple board for all the user controls and sending them to the Main board and Analog Input board.



