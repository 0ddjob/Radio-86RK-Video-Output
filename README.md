# Radio 86RK Video Output
The РАДИО-86РК was a Soviet-era homebrew/DIY computer based on their clone of the Intel 8080, the КР580ВМ80А.<br>
[Sergey Kiselev](https://github.com/skiselev) has [made a very nice modern recreation](https://github.com/skiselev/radio-86rk) that, importantly, outputs a "composite" video signal.<br>

Yes yes, "composite" means colour/luma+chroma but the machine outputs a luma/B&W-only video signal ... but you know what I mean ... the yellow RCA jack.<br>

![86RK video signal](/Images/86RK_video_signal.jpg)

The Intel 8275 (Soviet: КР580ВГ75) generates horizontal (HRTC) and vertical (VRTC) retrace signals which are combined with the character bitstream (character ROM to shift register) to produce the video output.  The image above shows one scanline with text - the negative-going pulses are HRTC & VRTC, the positive-going are character bits.<br>

The schematic below is a simplified version of Sergey's schematic highlighting how the video signal is generated.<br>

Sergey's implemention additionaly includes the reverse video (RVV) signal but this isn't implemented in all versions of the 86RK, so I'm ignoring (for now).<br>

![86RK video output stage](/Images/86RK_video_output.png)

The 86RK was serially produced by various factories in the Soviet Union resulting in machines such as the АЛЬФА-БК, ПАРТНЕР-01.01 and УМПК-Р.  These machines all output an RF-modulated video signal which is not convenient these days. <br>

To simplify conversion of these machines' video output I thought it might be worth implementing Sergey's video output stage as a discrete module that could be installed in these older machines.<br>

## Status: PARTIALLY TESTED
- 23-Nov-2024: initial design
- 25-Nov-2024: test PCBs ordered from PCBWAY
- 17-Dec-2024: [initial testing](https://youtu.be/Y1xS1cXXh0Q) on УМПК-Р but this machine has an underlying fault (DRAM?) so need to fix that first

## Initial Build
This is my dodgy "hand-made" version I whipped together when trying to get video out of a УМПК-Р, which convinced me that a proper module might be better for future use.<br>

![Brett's dodgy handmade version](/Images/86RK_video_dodgy_stripboard_version.jpg)

## Versions
I've made two versions: one with an RCA phono jack for testing/troubleshooting a machine without modifying too much and a second with a pin header for installation into a machine.

### [RCA Jack](/RCA_output/)
Selected the "same sky" part RCJ-014 as the phono jack.  Kicad library & datasheet are incuded.<br>

![RCA Jack version](/Images/86RK_Video_RCA.jpg)

### [PIN Header](/Pin_header_output/)
![Pin header version](/Images/86RK_Video_Pin.jpg)

## Bill of materials
- 2 x 1kΩ resistor
- 1 x 1.5kΩ resistor
- 1 x 75Ω resistor
- 1 x 150Ω resistor
- 1 x 2N3904 transistor
- 1 x 47µF electrolytic capacitor (pitch 2.5mm)
- 1 x 22nF ceramic capacitor (pitch 2.5mm)
- 1 x M3 bolt/nut/washer/spacer (if required)

For RCA phono jack version:
- 1 x RCJ-014 (or similar) RCA phono jack
- 1 x 4-pin header (pitch 2.54mm)

For pin header version:
- 1 x 5-pin header (pitch 2.54mm)
