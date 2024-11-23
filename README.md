# Radio 86RK Video Output
The РАДИО-86РК was a Soviet-era homebrew/DIY computer based on their clone of the Intel 8080, the КР580ВМ80А.  [Sergey Kiselev](https://github.com/skiselev) has [made a very nice modern recreation](https://github.com/skiselev/radio-86rk) that, importantly, outputs a "composite" video signal.<br>

Well, the machine outputs a B&W-only video signal but you know what I mean.<br>

![86RK video signal](86RK_video_signal.jpg)

The Intel 8275 generates a horizontal (HRTC) and vertical (VRTC) retrace signals which are combined with the character bitstream to produce the video output.  The image above shows on scanline with text.<br>

The 86RK was serially produced by various factories in the Soviet Union resulting in machines such as the АЛЬФА-БК, ПАРТНЕР-01.01 and УМПК-Р.  These machines all output an RF-modulated video signal which is not convenient these days. <br>

To simplify conversion of these machines' video output I thought it might be worth implementing Sergey's video output stage as a discrete module that could be installed in these older machines.<br>

## Status: UNTESTED
- 23-Nov-2024: initial design

## Versions
I've made two versions: one with an RCA phono jack for testing and a second with a pin header for installation into a machine.

### [RCA Jack](/RCA_output/)
Selected the "same sky" part RCJ-014 as the phono jack.<br>
![RCA Jack version](86RK_Video_RCA.jog)

### [PIN Header](/Pin_header_output/)
![Pin header version](86RK_Video_Pin.jog)


