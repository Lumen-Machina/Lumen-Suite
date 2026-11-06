# Lumen-Index

**A chord and scale companion for making music.** Look up any of 588 chords and 56 scales by name, or play a few notes and see every chord and scale that holds them. Put the chords you like on 12 pads and play them from one octave of your keyboard, with strums, arpeggios, smooth voice leading and hints for what usually comes next. Let a progression play them in time with your song, read the chords out of a clip or MIDI file you already have, follow along on a melody or bass track and catch what you played, then drag any of it into your arrangement as MIDI.

Runs in **Bitwig Studio** (CLAP) and in **Logic Pro** (Audio Unit MIDI FX), and as a **standalone app** for MIDI keyboards and hardware synths, on Windows and Mac. Current version: **1.4.1**.

![The Pads page: the progression at bar 5 (Am7), Dm7 and Fmaj7 glowing as the usual next chords, borrowed chords on pads 8 to 12](../docs/images/lumen-index/pads.png)

## What's new in 1.4.1

The first release for wider testing and feedback: a big round of fixes, and Read, chord names and Caught made much better.

- **Read keeps up with real playing.** It reads each change where you play it: three chords in a bar, a change on the "and", played loose and legato. Open guitar shapes (Em7, Bm7, F♯m7), arpeggios with a tune on top or a bass held under them, and changes on one root (Am to Am7) all read as the chords they are. In our tests on generated progressions with a melody on top, it names the right chord about 96% of the time, up from about 40% in 1.4.
- **Chord names a musician would write:** F/G, C7sus2, E7sus4, G13 shells, and nine new chord types, 50 in all.
- **Chords spelt by what they are in your key.** In C major the ♭VI chord is A♭maj7, not G♯maj7, and the name and the numeral always agree. The Index says what an out-of-key chord is: borrowed from the parallel key, a secondary dominant (E7 in C is V7/vi), or the Neapolitan.
- **Caught keeps 8 chords** (it kept 4), with no "in between" chords when you let go one finger at a time.
- **1-beat slots** on the progression: 16 changes over 4 bars. Changing SLOT or BARS while it plays keeps every chord on its beat.
- **Fine adjustment** on Strum and Velocity, as across the Lumen suite: drag with the right mouse button, or hold Ctrl (Mac: Cmd or Option), for 10 times finer moves; the mouse wheel moves one step.
- **Windows app:** plug and unplug MIDI gear while it runs; the menus update by themselves.
- **Steadier everywhere:** no notes left sounding under a busy host, arpeggios back on the beat after a jump, the downbeat chord kept after MIDI Start in the apps, safer loading of damaged projects and pad sets, and a window that does 2 to 5 times less work to draw.

The full list is under **NEW IN 1.4.1** in the manual (`README.txt` in the download). 1.4 brought Read, Undo and Redo 32 steps deep, scales that play as you browse, and clips dragged out at your song's tempo.

## Find chords and scales

The **Index** page is a dictionary of 50 chord types and 56 scales on every root. Type a name into **FIND** (`ebm9`, `sus`, `f#maj7`, `dorian`, `d hirajoshi`, `bebop`), or play a few notes on your keyboard, or click them, and every chord or scale that holds them comes up, best match first. **Contains** shows everything that holds your notes; **Exact** only what matches them exactly. Filters for root, quality and extension (or, for scales, family and number of notes) narrow it down.

Browse by ear: the arrow keys step through the results and each chord or scale plays as you reach it. Set a **Lead-in** pad and every candidate chord plays after it, so you hear each one coming from your chord, not on its own.

Every chord shows its notes, intervals and Roman numeral in your key (or what it borrows from outside it), with your choice of inversion and voicing, and the common scales it's found in. Send it to any pad in one click; a slash chord keeps its bass note at the bottom. Keep the good ones in a **shortlist** of up to 24, play it back in order, and drag it out as a progression.

![The Index page: every chord containing C, E♭, G and B♭, in B♭ major, with Cm7 open](../docs/images/lumen-index/index.png)

Every scale shows its notes and degrees, its modes, and the chords on each degree; click a chord to hear it. Click the scale itself to hear it played upward, every note and then the octave. **Set as key** makes the scale your key, and **Fill pads 1–7** puts its chords on the pads.

![The Scales view: 90 scales holding those notes, C Minor Pentatonic open with its modes and chords on each degree](../docs/images/lumen-index/scales.png)

## Play chords on pads

Twelve pads sit on the twelve keys of one octave of your keyboard: C1 to B1 by default (Bitwig's note names, where middle C is C3), and you can move them anywhere from C-1 to C7. Every other key passes straight through to your instrument, so you can play pads with one hand and a melody with the other.

Any chord goes on any pad, each with its own root, chord type, inversion, voicing (**Close**, **Open**, **Drop-2**, **Spread**) and octave. Pick your key and scale in the header, and:

- **Fill 1–7** puts your key's chords on the first seven pads as triads, 7ths or 9ths.
- **Borrowed** puts chords from the parallel key on pads 8–12: in C major with 7ths, Fm7, A♭maj7, B♭7, E♭maj7 and Gm7, the colours behind a lot of bittersweet and shoegaze progressions. They're spelt properly (A♭, not G♯) and dimmed less than other out-of-key chords.
- **Smooth** makes each chord lead into the next with as little movement as possible, choosing the inversion and octave nearest the chord before, never more than a sixth from where you set the pad.
- **Hints** light up where to go next: after each pad, the usual next chords glow bright red, other common ones get a dim red edge, and one surprising-but-good option gets a pale glow.

![Editing pad 2: Dm7 in an open voicing, with root, chord, inversion, voicing and octave](../docs/images/lumen-index/pad-editor.png)

Each pad also has its own way of playing:

- **Strum** up to 250 ms, up, down or random.
- **Velocity** that follows your playing (soft, linear or hard curve) or stays fixed.
- **Arpeggio**: up, down, up/down, random, or the whole chord retriggered; 1/4 to 1/32 with triplets; one to three octaves; gate from 25 to 100%. It follows the song's tempo and lands on its grid.
- **Humanize**: timing (up to 35 ms) and velocity (up to 30%), on chords, strums and arpeggios alike.

Copy a voicing or a set of play settings to every pad at once. Save all twelve pads, with every setting and the progression, as a named **pad set** and load it in any project. **Undo** and **Redo** go back and forth through your last 32 changes to the pads, the progression and the key, from the buttons in **Pad sets** or with **Ctrl+Z** (**Cmd+Z** on a Mac).

## Play a progression

The progression strip under the pads plays them in order, in time with your song: up to 16 slots of one beat, half a bar, one bar or two bars, looping over 4, 8 or 16 bars. Click a slot, then click pads, and they fill the slots in order. Use the same pad in two slots in a row to hold a chord; right-click a slot for a rest.

It runs while the transport runs, lined up with the bars of your song, so it follows loops and jumps and changes chords exactly on the beat. Arpeggios, strums and Smooth carry on in the strip. Press a pad yourself and it takes over until you let go.

## Read the chords of a clip

Got a chord part already? Open **Read** on the Pads page and either:

- **play it:** press Read, then play the clip on the same track; reading starts with its first note and stops when the song loops back or stops (up to 64 bars); or
- **drop a MIDI file** on the window, or open one. Drums (on channel 10) are left out.

Lumen-Index reads each chord change where you play it, even several in a bar or one on the "and", and copes with block chords, open guitar shapes, arpeggios (with a tune on top or a bass held under them), slash chords, and a melody played over the chords. It finds the key too (major or natural minor). Click any chord to hear it, then put them on the pads in the order they come, at the inversion and octave they were played, with or without the progression in time, and change your key to match if you like. Undo puts back the pads, the progression and the key.

(Bitwig and Logic don't hand a clip dragged from their arranger to a plugin window, which is why Read listens to the clip as it plays, alongside the file drop.)

![Read: 9 chords over 8 bars read from a dropped MIDI file, in A minor, ready to put on the pads](../docs/images/lumen-index/read.png)

## Guide your melody and bass

Put Lumen-Index on a melody or bass track too, set it to **Melody guide** or **Bass guide**, and link it to your pads track with the same link number. The guide shows the chord being played and lights its tones (the bass guide points you to the root and the 5th), and checks each note you play: chord tone, scale note, or outside the key (outlined red on its keyboard while you hold it, even with Snap off). Linked tracks share the key, so changing it on one changes it on all of them.

**Snap** can move stray notes up, down or to the nearest note in the scale or chord, or mute them.

**Caught** keeps the last eight chords, each with the notes you played over it, how long it lasted and a little piano roll: chord tones bright, other notes in the key grey, notes outside it red. When the changes come fast you can see what just went by and what you played over it. Click a card to hear its chord. Drag a card out for the line you played over that chord, drag the whole line, or drag the chords at their real lengths.

![The Melody guide: the last eight chords caught, with the notes played over each](../docs/images/lumen-index/melody.png)

## Get it into your song

Drag a pad, a chord, the shortlist, all twelve pads, the whole progression or a caught line onto your arranger, and it lands as a MIDI clip with the real notes, strums, arpeggios and humanize written in, timed at your song's tempo. The live display in the header names whatever is playing, with its numeral in your key.

## Work with hardware

The standalone app has the same window and engine as the plugin and talks to your MIDI gear directly, no DAW needed: choose a MIDI input, a MIDI output and a channel. It follows MIDI clock, so arpeggios lock to the tempo of your drum machine, sequencer or DAW, and after Start the progression and Read run on it too. Clock and Start/Stop pass on to your gear. On Mac it also has a virtual output, so Logic or any other app can record what it plays, and gear you replug while it runs comes back by itself.

## Where it runs

| | Windows | Mac (Intel and Apple Silicon) |
|---|---|---|
| **Bitwig Studio** (or any CLAP host) | CLAP | CLAP |
| **Logic Pro** (MainStage should work too) | | Audio Unit (MIDI FX slot) |
| **Standalone, for MIDI gear** | App | App |

In Bitwig it goes first on an instrument track, as a note effect; in Logic, in the MIDI FX slot above the instrument. Your pads, progression, key and settings are saved with the project, and every parameter can be automated.

Ableton Live, FL Studio and other DAWs without CLAP or a MIDI FX slot can use it today through the standalone app: its MIDI out into a virtual MIDI port, recorded in the DAW, or chords dragged from the app straight in. A VST3 version is next on the [roadmap](../ROADMAP.md), with Lumen-Index first. GarageBand has no MIDI FX slot, so it can't load Lumen-Index.

## Getting it

**[Get Lumen-Index on Gumroad →](https://lumenmachina.gumroad.com/l/lumen-index)**

Pay what you want. Windows and Mac downloads; new versions appear in your Gumroad library.

- [User guide](lumen-index-guide.md): how to use every part, step by step.
- Manual: every control, in one plain-text file, `README.txt` in the download. The Mac download also has `README-mac.txt`, with the install steps for Mac.

Found a problem or have an idea? [Open an issue](https://github.com/Lumen-Machina/Lumen-Suite/issues/new/choose) and choose Lumen-Index. If something went wrong, press **Save log** in the plugin's footer right after and attach the file it puts on your Desktop.

---

[← All Lumen plugins](../README.md)
