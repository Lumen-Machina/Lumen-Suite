# Lumen-Index

**A chord and scale companion for making music.** Find any chord or scale by name or by the notes you play, put chords on 12 pads, play them with strums and arpeggios, let a progression play them in time, and drag the results straight into your song.

Runs in **Bitwig Studio** and **Logic Pro**, and as a **standalone app** for MIDI keyboards and hardware synths, on Windows and Mac. Current version: **1.1**.

![The Index page: chords containing C, E♭, G and B♭, in B♭ major](../docs/images/lumen-index/index.png)

## Find chords and scales

Every common chord and scale, searchable by name (`Ebm9`, `sus`, `maj7#11`, `dorian`, `d hirajoshi`) or by the notes you play or click, with the best match first. Browse with the arrow keys and each chord plays as you go. Keep the good ones in a shortlist and play it back as a progression.

Every chord shows its notes, intervals, Roman numeral in your key and the scales it belongs to. Every scale shows its modes and the chords that fit each degree.

![The Scales view: C minor pentatonic, its modes and the chords on each degree](../docs/images/lumen-index/scales.png)

## Play chords on pads

Twelve pads on one octave of your keyboard. Any chord on any pad, each with its own inversion, voicing (close, open, drop-2, spread) and octave. Fill pads 1 to 7 from your key in one click, as triads, 7ths or 9ths.

Each pad has its own **strum**, **velocity** curve, **arpeggio** (up, down, up/down, random or chord; 1/4 to 1/32 with triplets; one to three octaves) and **humanize**. Save all twelve pads as a named **pad set** and load it in any project.

## Play a progression

The progression strip under the pads plays them in order, in time with your song: up to 16 slots, looping over 4, 8 or 16 bars. Click a slot, then click pads, and they fill in order. It follows loops and jumps in your song and changes chords exactly on the beat. Press a pad yourself and it takes over until you let go.

![The Pads page: the progression playing Dm7 in bar 2, pad 5 set to arpeggiate](../docs/images/lumen-index/pads.png)

## Get it into your song

Drag a pad, a chord, the shortlist, all twelve pads or the whole progression onto your arranger, and it lands as a MIDI clip with the real notes, strums and arpeggios included. The live display names whatever is playing, with its numeral in your key.

## Guide your melody and bass

Put Lumen-Index on a melody or bass track too and link it to your pads track. The guide shows the chord being played, lights its tones, and checks each note you play against the chord and the key. **Snap** can move stray notes to the nearest one in the scale or chord, or mute them.

![The Melody guide following Dm7 from the pads track](../docs/images/lumen-index/melody.png)

## Work with hardware

The standalone app has the same window and engine as the plugin and talks to your MIDI gear directly, no DAW needed: choose MIDI in, MIDI out and a channel. It follows MIDI clock, so arpeggios and the progression lock to your drum machine, sequencer or DAW. On Mac it also has a virtual output, so Logic or any other app can record what it plays.

## Where it runs

| | Windows | Mac (Intel and Apple Silicon) |
|---|---|---|
| **Bitwig Studio** (or any CLAP host) | CLAP | CLAP |
| **Logic Pro, GarageBand, MainStage** | | Audio Unit (MIDI FX slot) |
| **Standalone, for MIDI gear** | App | App |

## Getting it

**[Get Lumen-Index on Gumroad →](https://lumenmachina.gumroad.com/l/lumen-index)**

Pay what you want, including nothing. Windows and Mac downloads, with every future update free in your Gumroad library.

Found a problem or have an idea? [Open an issue](https://github.com/Lumen-Machina/Lumen-Suite/issues/new/choose) and choose Lumen-Index.

---

[← All Lumen plugins](../README.md)
