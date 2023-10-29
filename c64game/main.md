
# Background

I was interested in creating a game Commodore 64, and wanted to see if it could be done in C with sufficient performance.

After coding some various test code with sprites and graphics, I decided to build a Bomberman-inspired game.

Now after 5+ years, the project is still in unfinished state. It not abandoned though. Next key thing is to finalise
overall game story concept, on which the game graphics and themes can be built around.

In general, writing a game for Commodore 64 is not easy. It requires a lot of optimization, and many of the
modern good coding practises must be ignored. In many ways the coding is more difficult than my daily work in
the "normal" IT software world.

# Technical details

I used a Docker-based build system to generate the D64 disk image.

The CC65 compiler doesn't produce very optimized code for 6502 processor, so I had use assembler here and there.

- FastLoader, sprite muxing and music player was made by [Covert Bitops](!http://covertbitops.c64.org/)

- [Exomizer](!https://bitbucket.org/magli143/exomizer/wiki/Home) packing system was used

- Graphics were done with [CharPad and SpritePad](!https://subchristsoftware.itch.io/c64-pro-editions)

- Music was made with [GoatTracker](!https://sourceforge.net/p/goattracker2/code/HEAD/tree/goattrk2/trunk/)

# Some screenshots

#### Intro
![](/images/c64game/logo.png)

#### Progress map
![](/images/c64game/map.png)

#### In-game
![](/images/c64game/game1.png)

![](/images/c64game/game2.png)

![](/images/c64game/game3.png)


{% include footer.md  %}

