# Lumen-Index 1.4.1 user guide

*This is the guide for Lumen-Index version 1.4.1. See [what's new in 1.4.1](lumen-index.md#whats-new-in-141), or go back to the [Lumen-Index page](lumen-index.md).*

Lumen-Index is a chord and scale companion by [Lumen-Machina](https://lumen-machina.com). This guide covers every control in version 1.4.1, in the plugin and in the standalone apps.

## Contents

1. [What Lumen-Index is](#what-lumen-index-is)
2. [Install](#install)
3. [Questions](#questions)
4. [New in 1.4.1](#new-in-141)
5. [A first 10 minutes](#a-first-10-minutes)
6. [The window](#the-window)
7. [Index page: Chords and Scales](#index-page-chords-and-scales)
8. [Pads page](#pads-page)
9. [Progression](#progression)
10. [Read chords](#read-chords)
11. [Melody guide and Bass guide](#melody-guide-and-bass-guide)
12. [Link](#link)
13. [Getting it into your song](#getting-it-into-your-song)
14. [Standalone apps](#standalone-apps)
15. [Saving and pad set files](#saving-and-pad-set-files)
16. [Troubleshooting and Save log](#troubleshooting-and-save-log)
17. [Reference](#reference)

---

## What Lumen-Index is

Lumen-Index sits in front of an instrument and works with MIDI notes. It makes no sound of its own: it sends notes on to the synth after it. With it you can:

- **Find** any chord or scale by name, or by the notes you play.
- **Play chords on 12 pads** from one octave of your keyboard, with strums, arpeggios and smooth voice leading.
- **Run a progression** of those pads in time with your song.
- **Read the chords** of a clip or a MIDI file and put them on the pads.
- **Guide a melody or bass track**: another copy of Lumen-Index shows the chord the pads track is playing and checks what you play over it.
- **Drag** pads, chords, progressions and the lines you played straight into your song as MIDI clips.

### Formats and where it runs

| | Windows | Mac (Intel and Apple Silicon, macOS 10.13 or later) |
|---|---|---|
| **Bitwig Studio** or any CLAP host | `Lumen-Index.clap` | `Lumen-Index.clap` |
| **Logic Pro** (and other hosts with a MIDI FX slot for Audio Units) | | `Lumen-Index.component` (Audio Unit, goes in the **MIDI FX** slot) |
| **Standalone**, for MIDI keyboards and hardware synths | `Lumen-Index.exe` | `Lumen-Index.app` |

The window and the note engine are the same in every format. The standalone apps add MIDI device menus to the footer (see [Standalone apps](#standalone-apps)).

### A note on note names

Note names follow Bitwig's numbering, where middle C (MIDI note 60) is **C3**. So the default trigger keys, C1–B1, are MIDI notes 36–47. Logic and Ableton Live number octaves the same way. Hosts and keyboards that call middle C **C4** (Reaper, by default) call the same keys C2–B2. If your host numbers octaves differently, go by the note numbers.

---

## Install

Get the Windows or Mac zip from [Gumroad](https://lumenmachina.gumroad.com/l/lumen-index) (pay what you want).

| Download | What's inside |
|---|---|
| Windows zip | `Lumen-Index.clap`, `Lumen-Index.exe`, `README.txt` (the manual), `licences/` |
| Mac zip | `Lumen-Index.clap`, `Lumen-Index.component`, `Lumen-Index.app`, `README-mac.txt`, `README.txt` (the manual), `licences/` |

### Windows

1. Copy `Lumen-Index.clap` to `C:\Program Files\Common Files\CLAP\` (make the folder if it's missing). Windows asks for administrator permission: click **Continue**.
   - No administrator rights? Use your own CLAP folder instead: `%LOCALAPPDATA%\Programs\Common\CLAP\` (paste it into Explorer's address bar; make the folder if it's missing). CLAP hosts look there too; if yours doesn't, add the folder in its plug-in settings.
2. Rescan plug-ins in Bitwig.
3. For the standalone app, put `Lumen-Index.exe` wherever you like and run it. It needs no installing.

### Mac

1. Copy the files you want:
   - **CLAP** (Bitwig): `Lumen-Index.clap` to `~/Library/Audio/Plug-Ins/CLAP/`
   - **Audio Unit** (Logic Pro): `Lumen-Index.component` to `~/Library/Audio/Plug-Ins/Components/`
   - **App**: drag `Lumen-Index.app` into Applications.

   In Finder, use **Go > Go to Folder…** and paste the path. Make the folder if it's missing.
2. Restart Logic or Bitwig.

### If Windows or macOS won't open it

The files aren't signed with a paid developer certificate yet, so the first time, Windows and macOS say they don't know who made them. That's expected, and you only do this once.

**Windows**

- Simplest: before you unpack the zip, right-click it, choose **Properties**, tick **Unblock** and click **OK**.
- `Lumen-Index.exe`: if "Windows protected your PC" appears, click **More info**, then **Run anyway**.
- `Lumen-Index.clap`: if your DAW won't load it, right-click the file, choose **Properties**, tick **Unblock**, click **OK**, and rescan.

**Mac**

- The app: open it once (macOS blocks it), then open **System Settings > Privacy & Security**, scroll down and click **Open Anyway** next to Lumen-Index. (macOS 12 and older: **System Preferences > Security & Privacy > General**.)
- The plugins, or if there's no **Open Anyway**: open Terminal and run, once, the line for each file you installed (`README-mac.txt` in the zip has them too):

  ```
  xattr -dr com.apple.quarantine /Applications/Lumen-Index.app
  xattr -dr com.apple.quarantine ~/Library/Audio/Plug-Ins/Components/Lumen-Index.component
  xattr -dr com.apple.quarantine ~/Library/Audio/Plug-Ins/CLAP/Lumen-Index.clap
  ```
- Then restart Logic or Bitwig. If Logic still doesn't list Lumen-Index, open **Logic Pro > Settings > Plug-in Manager**, find Lumen-Index and click **Reset & Rescan Selection**.

### Updating

Close Bitwig or Logic (and the app) first, then copy the new files over the old ones: Windows can't replace a plugin file that's loaded. Projects, pad sets and app settings carry over. If you have a very old `Lumen Index.clap` (version 0.2.x, with a space in the name), delete it: projects made with it open with this one.

### Uninstalling

Delete the files you installed:

| | Windows | Mac |
|---|---|---|
| CLAP | `C:\Program Files\Common Files\CLAP\Lumen-Index.clap` (or the one in `%LOCALAPPDATA%\Programs\Common\CLAP\`) | `~/Library/Audio/Plug-Ins/CLAP/Lumen-Index.clap` |
| Audio Unit | | `~/Library/Audio/Plug-Ins/Components/Lumen-Index.component` |
| App | `Lumen-Index.exe`, wherever you put it | `Lumen-Index.app` in Applications |

Your own files stay until you delete them too: pad sets and app settings (`%APPDATA%\Lumen-Index\`, or `~/Library/Application Support/Lumen-Index/` on a Mac; deleting the folder loses your pad sets), the Save log on your Desktop, dragged clips in the temporary folder (see [Where files go](#where-files-go)), and on a Mac the app's window position, `~/Library/Preferences/com.lumenmachina.lumen-index.app.plist`.

### Loading it in Bitwig

1. Make an instrument track with the synth you want to play.
2. Add Lumen-Index **first** on the track, before the instrument. It's a note effect, so it passes notes on to the device after it.
3. Open its window.

Every parameter can be automated (see [Parameters the host can automate](#parameters-the-host-can-automate)).

### Loading it in Logic Pro

1. Make a Software Instrument track. For a hardware synth, put Logic's **External Instrument** plug-in (**Utility > External Instrument**) in its instrument slot and choose your MIDI port.
2. Click the **MIDI FX** slot above the instrument and choose **Audio Units > Lumen-Machina > Lumen-Index**.
3. Play C1–B1 to trigger the pads. Everything else passes through.

If it doesn't appear, open **Logic Pro > Settings > Plug-in Manager**, find Lumen-Index and click **Reset & Rescan Selection**.

Other hosts with a MIDI FX slot for Audio Units, such as MainStage, should work the same way; only Logic has been tested. GarageBand has no MIDI FX slot, so it can't load Lumen-Index.

### Other DAWs

- **Other CLAP hosts**, such as Reaper: put Lumen-Index before the instrument, in the same track's chain. Not tested yet.
- **Ableton Live, and DAWs without CLAP or a MIDI FX slot**: use the standalone app between your keyboard and the DAW (see [Questions](#questions)).

---

## Questions

**Can I use it in music I release?**
Yes. You may use Lumen-Index in your music, and I hope you do. What you make with it (chords, progressions, MIDI clips, recordings) is yours to release and sell, with no credit or fee owed.

**Does it make sound?**
No. Lumen-Index sends MIDI notes to the instrument after it (from the standalone app: to your synth, or to another program). You need a synth after it to hear anything.

**Which formats are there?**
CLAP (Windows and Mac), Audio Unit MIDI effect (Mac), and standalone apps for Windows and Mac. There's no VST3, no AAX and no Linux version.

**Which DAWs does it work in?**
- **Bitwig Studio**: the CLAP. This is where it's tested most.
- **Logic Pro**: the Audio Unit, in the **MIDI FX** slot.
- **Reaper and other CLAP hosts**: the CLAP, before the instrument. Not tested yet.
- **GarageBand** has no MIDI FX slot, so it can't load Lumen-Index.
- **Ableton Live and other DAWs without CLAP or MIDI FX**: run the standalone app. Set its **MIDI IN** to your keyboard and its **MIDI OUT** to a virtual MIDI port, then in the DAW, record a MIDI track from that port.
  - On a Mac the app has its own port: **Lumen-Index (virtual, for other apps)**.
  - On Windows, make a port with a virtual MIDI cable program such as loopMIDI. Windows lets only one program use most MIDI devices at a time: give your keyboard to the app, and switch it off in the DAW's MIDI settings.
  - Without MIDI clock coming in, the app's arpeggios run at 120 bpm and the progression waits (see [MIDI clock](#midi-clock)).
  - You can also drag chords, pads and progressions from the app straight into the DAW.

**Which Windows and macOS versions?**
Windows 10 or 11, 64-bit. macOS 10.13 or later, on Intel and Apple Silicon.

**How much CPU, and does it add latency?**
It adds no latency: in a DAW, notes go out in the same audio block they come in, and it reports none to the host. Strum and humanize delay notes on purpose, only when you set them. The standalone apps pass notes on within about a millisecond. The note engine uses very little CPU. The window is drawn by the plugin itself and uses a little more while it's open; close it when you don't need it.

**My DAW calls these keys C2, not C1.**
Lumen-Index names notes as Bitwig does: middle C (MIDI note 60) is C3, so the pads' keys, C1–B1, are MIDI notes 36–47. Logic and Ableton Live name notes the same way. Hosts that call middle C "C4" (Reaper, by default) call the same keys C2–B2. See [A note on note names](#a-note-on-note-names).

**Does it follow time signatures?**
No: 4/4 only. The progression, Read and the lengths of dragged clips count four beats to the bar.

**What does it cost?**
Pay what you want, on [Gumroad](https://lumenmachina.gumroad.com/l/lumen-index).

**Something went wrong. Where do I report it?**
Press **Save log** in the footer right away (see [Save log](#save-log)) and send the file, with a line on what you did, as an [issue](https://github.com/Lumen-Machina/Lumen-Suite/issues/new/choose). **Panic**, next to it, ends every note at once.

---

## New in 1.4.1

- **Before you update**: close your DAW first. If a project automates **Trigger octave** to its lowest step, its pads now sit on C-1–B-1, as the host's name for that step says (1.4 gave C0–B0): if they went quiet, move the automation up one step. Pads saved with add9, m(add9), add11 or 7alt in 3rd inversion, or 7alt in 2nd, now play the right inversion.
- **Read follows quick changes**: several chords in a bar, off the beat, played loose and legato. It also reads open guitar shapes, changes on one root (C to Cmaj7), arpeggios with a tune on top or a bass under them, and a vamp's key from its home chord (see [Read chords](#read-chords)).
- **Chord names as a musician writes them** (F/G, C7sus2, G13), nine new chord types (50 in all), and every chord spelt by what it is in your key, its numeral to match (see [How chords and notes are spelt](#how-chords-and-notes-are-spelt)). The Index says what an out-of-key chord is.
- **Caught keeps 8 chords**, and no chords "in between" when you let go one finger at a time (see [Caught](#caught)).
- **The progression has 1-beat slots**, and changing **SLOT** or **BARS** keeps every chord on its beats (see [Slots and length](#slots-and-length)).
- **The Windows app follows your MIDI gear**: plug and unplug it while the app runs.
- **Fine adjustment** on the **STRUM** and **VELOCITY** sliders (see [Play tab](#play-tab)).
- **Many fixes**: no notes left sounding, safer loading of damaged projects and pad sets, safer with hosts that misbehave, and the window does 2 to 5 times less work to draw.

Every change and fix is in the [changelog](../CHANGELOG.md).

---

## A first 10 minutes

This walkthrough uses Bitwig. You'll need a MIDI keyboard, or you can click the pads with the mouse.

**1. Load it and set the key**

1. Put Lumen-Index first on an instrument track (in Logic, in the MIDI FX slot) and open its window.
2. Click **KEY** in the header. Pick a root, then a scale, for example **A** and **Natural Minor**. Click outside the menu to close it.

**2. Fill the pads**

1. Click **Pads** in the header if it isn't already showing.
2. Pick **7ths** (the default), then click **Fill 1–7**. Pads 1–7 now hold the seven chords of your key.
3. Click **Borrowed**. Pads 8–12 get chords from the parallel key (the major or minor key on the same root), which add colour.
4. Changed your mind? **Pad sets ▾** has **Undo** and **Redo** for changes to the pads, the progression and the key.

**3. Play the pads**

1. Play C1 to B1 on your keyboard, black keys included: each key plays one pad. Or click and hold a pad.
2. Turn on **Smooth**. Each chord now picks the inversion closest to the one before it, so the notes move as little as possible.
3. **Hints** is on by default. After a pad plays, the pads that usually come next glow: bright red for the usual next chords, a dim red edge for other common ones, a pale glow for a twist that works.
4. Watch the **LIVE** display in the header: it names each chord and where it sits in your key.

**4. Build a progression**

A new instance already has four slots set to pads 1, 6, 4 and 5 (I, vi, IV, V). To make your own:

1. Under the pads, click the first slot of **PROGRESSION**. It lights up.
2. Click four pads in the order you want. Each fills the next slot.
3. Press **Esc** to stop filling.
4. Click **On**, then press play in Bitwig. The progression plays while the transport runs, in time with the song.

**5. Add a guide track**

1. Make a second instrument track (a lead or bass sound) and add Lumen-Index first on it.
2. In its window, on the **Pads** page, set the role switch at the top to **Melody guide** (or **Bass guide**).
3. Both instances start on link 1, so the guide already follows the pads track. The header's **LINK** chip shows the number.
4. Play along while the progression runs. The guide shows the current chord, lights its tones on the keyboard, and labels each note you play as a chord tone, a scale note or outside the key.

**6. Look at Caught**

On the guide track, the **CAUGHT** row keeps the last eight chords, each with the notes you played over it. Click a card to hear its chord.

**7. Drag into the arranger**

1. Drag a **Caught** card onto the arranger: you get a clip of the line you played over that chord.
2. On the pads track, drag **Drag strip** onto the arranger: you get the whole progression as a clip, with strums and arpeggios included.
3. Drag any single pad out for one bar of its chord.

**8. Read chords from a clip**

1. On the pads track, click **Read ▾**.
2. Drop a MIDI file on the window (or click **Open file…**), or press **● Read** and play a clip on the same track.
3. When the result shows, click **Pads + progression**.
4. Turn the progression **On** (Read doesn't do this for you) and press play.

That's the core of it. The rest of this guide covers each part in full.

---

## The window

The window is the same in the plugin and both apps. It's a fixed size (1200 × 720) and can't be resized; the host or the operating system scales it.

### Header

- **Page tabs: Index and Pads.** **Index** is the chord and scale dictionary. **Pads** holds the pads, the progression, Read and, in a guide role, the guide.
- **LIVE**: names whatever this instance is sending out, or, if nothing is going out, the keys you're holding. A scale the Index plays (▶ Play, clicking a scale) isn't named: it plays one note at a time and LIVE leaves it out. The dot next to it lights red while something sounds.
  - Two or more notes that make a known chord: the chord name (root in red), then its Roman numeral and whether it's in your key, for example "ii7 in C Major". The numeral shows where the chord sits in the key: ii7 is the minor 7th built on the 2nd degree.
  - One note: its name and its degree, for example "degree 6 of C Major", or "outside C Major" for a note that isn't in the key.
  - Three or more notes that make no known chord: up to 6 note names.
  - Nothing sounding: "–".
- **KEY**: shows the current key, for example "KEY C Major". Click to open the [KEY menu](#key-menu).
- **LINK**: shows "LINK Off" or "LINK 1" to "LINK 4", with a red dot when on. Click for the next value (Off → 1 → 2 → 3 → 4 → Off); right-click for the one before. On a Mac, Control-click counts as a right-click. The footer says what it means, for example "Link 2: tracks on Link 2 share the key and the chord." or "Link off: this track shares nothing with the others." See [Link](#link).

### KEY menu

- **KEY ROOT**: the 12 roots, each spelt as the key on it is written with the scale you have: with Major, D♭ E♭ F♯/G♭ A♭ B♭; with Natural Minor, C♯ E♭/D♯ F♯ G♯ B♭. A key is spelt with the key signature that has fewer sharps or flats (a mode by the key it's a mode of, so E♭ Dorian, not D♯ Dorian), so it is never a key nobody writes in (A♯ Major is B♭ Major, G♭ minor is F♯ minor).
- **♭ Flats / ♯ Sharps**: only for the keys that can be written either way, with the same number of sharps or flats: F♯ or G♭ Major, D♯ or E♭ minor, and the modes and scales that share those key signatures (G♯ or A♭ Mixolydian, D♯ or E♭ harmonic minor...). Everything else is spelt the same whichever you pick. Default: Flats.
- **SCALE**: the 16 common scales: Major, Dorian, Phrygian, Lydian, Mixolydian, Natural Minor, Harmonic Minor, Phrygian Dominant, Melodic Minor, Major Pentatonic, Minor Pentatonic, Blues, Major Blues, Whole Tone, Diminished (whole-half), Diminished (half-whole). The last rows are below the fold: a bar on the right shows there's more, and the mouse wheel scrolls. The menu opens with your scale in view.
- **All scales**: opens the Index in Scales mode with your key's scale picked, where any of the 56 scales can be made the key with **Set as key**.

The default key is C Major with flats. The key decides how notes are spelt (see [How chords and notes are spelt](#how-chords-and-notes-are-spelt)), the Roman numerals, which pads are dimmed as out of key, what **Fill 1–7** and **Borrowed** put on the pads, the Hints, and what Snap treats as the scale. Linked instances share the key.

A key change made in this menu can be undone (see [Undo and Redo](#undo-and-redo)).

### How chords and notes are spelt

A chord is named the way its Roman numeral reads in your key, so the name and the numeral always agree:

- A chord on a note of the scale uses the scale's own letter (in D minor, B♭; in G♯ harmonic minor, F𝄪, shown F♯♯).
- A chord on a note outside the scale uses the major scale's letter where there is one: F♯ in D minor (D major's 3rd), so the D chord is D F♯ A and C♯°7 is vii°7. Secondary dominants keep their raised notes: E7 in C is E G♯ B D.
- On the five notes in between, a chord takes the flat of the degree above, ♭II ♭III ♭V ♭VI ♭VII: in C, D♭7, E♭maj7, A♭maj7, B♭6. A diminished chord there is a leading-tone chord to the degree above and takes a sharp, as does a minor chord on the tritone: F♯°7 (♯iv°7, leading to G), G♯°7 (♯v°7), C♯°7, D♯°7, F♯m7♭5 (♯ivø7), F♯m (♯iv).
- A single note outside the key is spelt the same way: in C, D♭ E♭ F♯ A♭ B♭.
- In the Index, a chord you typed or picked with its own spelling (`a#maj7`, or the ROOT filter's ♯) keeps it, and its numeral follows (♯VImaj7 in C). Sent to a pad or the shortlist, it keeps that spelling; any other chord is spelt again from the key if you change key.

The Scales view spells a scale, its modes and its chords from the scale's own notes. Flats / Sharps in the KEY menu only picks between F♯ and G♭ major, D♯ and E♭ minor, and the scales that share those key signatures.

### Footer

- **Status text**: what just happened, for example "Sent Cmaj7 (Root, Close) to pad 3." A message shows for about 6 to 15 seconds, depending on how long it is (a warning, such as "Could not write the log file.", about 4 seconds more). Then the page's hint comes back. A new message, even the same one again, starts its time again.
  - While you hold a pad (or press on anything you can drag out), and while you drag a clip out, the message stays until you let go or drop; then its time starts again.
  - While Read is waiting or reading, the footer shows "Reading: play the clip on this track." instead of the page's hint.
  - While you fill progression slots, it shows the filling hint instead of any message.
  - "Type a name for the set first." stays while the set's name field is still empty.
  - Switching pages (or Chords and Scales) clears a message about the page you left, so the new page's hint shows. A warning stays for its time.
  - With the pointer over **Lead-in**, **Follow MIDI**, **Play as I browse**, **Slash**, **Smooth**, **Hints**, **Triads / 7ths / 9ths**, **Fill 1–7**, **Borrowed**, **SLOT**, **BARS** or **LINK**, and no message showing, the footer says what it does, and whether a switch is on, for example "Smooth is off: pads play as voiced. Click to switch it on."

  The hints:
  - Index: "← → ↑ ↓ browse · Space replays · Enter adds to the shortlist"
  - Pads: "Hold a pad to play it · drag it into the arranger for a clip"
  - While filling progression slots: "Click pads to fill the progression in order · Esc stops"
  - Guides: "Same link number here and on the pads track"; with no chord from the pads track yet, "No chord yet: put Lumen-Index on another track, set it to Pads, Link 1"
- **Link and voices**: "Link 1 · 2 instances · voices 3", or "Link off · voices 0". The instance count is the instances on your link number, this one included (an instance of 1.4 or older isn't counted).
- **Panic**: stops every sound Lumen-Index is making and sends "all notes off". Use it for stuck notes. A progression that's playing stays quiet until its next slot (or until you stop and start the song), and letting go of a key you held through it sends nothing more. Status: "Panic: every voice ended."
- **Save log**: writes a diagnostic file to your Desktop. See [Save log](#save-log).
- The version, **v1.4.1**.
- In the standalone apps only: **MIDI IN**, **MIDI OUT** and **CH** (see [Standalone apps](#standalone-apps)).

### Mouse and keyboard in general

- The mouse wheel or trackpad scrolls the results, the detail panel, the KEY menu's scale list, the Pad sets list and the pad editor's chord grid. You can also drag the results scrollbar. Over the **STRUM** or **VELOCITY** slider, the wheel moves the slider a step instead (see [Play tab](#play-tab)).
- **Fine adjustment** (since 1.4.1, as across the Lumen suite): drag a slider with the **right** mouse button, or hold **Ctrl** (Mac: **Cmd** or **Option**) and drag with the left, and it moves 10 times more finely, from where it was. A right-click on a slider never opens a menu and doesn't move the value. Shift is never used: Bitwig doesn't pass it to plug-in windows.
- A double-click works like a single click.
- A switch that's on (**● Follow MIDI**, **/ Slash**, **● Play as I browse**, **Smooth**, **Hints**) is lit, with a red bar along its foot; off, it has none. Clicking one says in the footer which way it went.
- **Esc** closes an open menu, or stops filling progression slots. Clicking outside a menu also closes it.
- **Ctrl+Z** undoes and **Ctrl+Shift+Z** or **Ctrl+Y** redoes (on a Mac, **Cmd+Z**, **Cmd+Shift+Z**, **Cmd+Y**), when the Lumen-Index window has the keyboard and you're not typing in FIND or a set name. See [Undo and Redo](#undo-and-redo).
- On a Mac, keys the window doesn't use, and any key with Command other than Undo and Redo, go on to the host, so its transport shortcuts still work.

---

## Index page: Chords and Scales

![The Index page in B♭ major with C, E♭, G and B♭ selected; Cm7 picked with its notes, intervals, inversion and voicing choices and the keys it belongs to](../docs/images/lumen-index/index.png)

*The Index in B♭ major with C, E♭, G and B♭ selected. Cm7 is picked, showing its notes, intervals, inversion and voicing, and the keys it's found in (B♭ Major first, then C, F and G minor).*

The Index is a dictionary of 588 chords (50 chord types, 49 names, on 12 roots) and 672 scales (56 scales on 12 roots). Switch between them with **Chords / Scales** at the top of the left column. Switching clears the FIND text.

The page has three columns: what you're looking for on the left, the results in the middle, and the details of the selected result on the right.

### FIND

Click the **FIND** field and type a chord or scale name. Press Enter, Esc or Tab to leave the field. Typing a name clears any selected notes.

**Chords**: type a root and a chord symbol, or just the symbol.

| You type | You get |
|---|---|
| `ebm9` | E♭ minor 9th |
| `sus` | every sus chord on every root |
| `maj7` | major 7th chords on all 12 roots first, then maj7♯11 and +maj7 |
| `bbmaj7` | B♭ major 7th |
| `am7` | A minor 7th |
| `dim`, `add9`, `aug`, `alt` | those chords, and the chords whose names start with them, on every root (`dim` also brings up m7♭5 and °7). These words are read as chord names, not as a root |
| `half`, `quartal` | words from the long names work too (half-diminished, quartal) |
| `c` | every chord on C (a single letter is always a root) |

Roots work in lowercase or capitals. Use `b` for flat and `#` for sharp. The chord that matches what you typed exactly comes first; chords whose names start with it follow.

> **Bitwig may keep Shift from plug-in windows,** so type in lowercase: `ebm9`, `f#maj7`. If `#` won't type (it needs Shift on most keyboards), pick the root with the **ROOT** filter (for example **F** and **♯**) and type just the rest (`maj7`) in FIND.

**Scales**: type a scale name, a family, or a root and a name.

| You type | You get |
|---|---|
| `dorian` | Dorian on your key's root |
| `d hirajoshi` | Hirajoshi on D |
| `bebop` | the bebop scales |
| `pentatonic`, `blues` | scales in that family |

Other names work as search words too, among them Ionian, Aeolian, Hijaz, Freygish, Jazz Minor, Super-Locrian, Octatonic, Sakura, Byzantine and Gypsy Minor.

### Filters

- **ROOT**: **–** (any) or a letter C to B, plus **♭ ♮ ♯** to make it flat, natural or sharp.
- Chords only:
  - **QUALITY**: – Maj Min Dom Aug Dim Sus 5 (5 is the power chord).
  - **EXTENSION**: – None 6th 7th 9th 11th 13th.
- Scales only:
  - **FAMILY**: All, Major, Minor, Modal, Pentatonic, Blues, Bebop, Jazz, Symmetric, World.
  - **NOTES**: – 5 6 7 8+ (how many notes the scale has).

### Finding a chord by its notes

The **PLAY OR CLICK NOTES** keyboard covers two octaves, C2 to C4.

- **Click** keys to turn them on or off. A key you turn on plays briefly. Selected keys show their names.
- **Play** notes on your MIDI keyboard. With **● Follow MIDI** on (the default), each new note you play replaces the selection with all the keys you're holding, in any octave, and clears FIND. This only happens while the Index page is showing. Click it to switch to **○ Follow MIDI** (off).

Below the keyboard, a line shows your selection, for example "Notes: C E G   bass C", or "No notes selected: showing everything that matches the filters."

- **Contains / Exact**: **Contains** lists every chord or scale that holds all your notes. **Exact** lists only the ones made of exactly those notes (plus "no 5" matches, below).
- **/ Slash** (Chords, on by default): when your lowest note isn't the chord's root, the result is named as a slash chord. A slash chord is a chord over a different bass note: C/E is C major with E in the bass. This applies to exact and "no 5" matches.
- **Clear**: clears the notes, every filter and FIND. It leaves Contains/Exact, Follow MIDI and Slash as they are.

### Results

The middle column shows "N chords found · best match first" (the "best match first" part appears when notes are selected). Each tile shows the name (root in red), its degrees, a mini keyboard, and a tag:

| Tag | Meaning |
|---|---|
| **exact** | made of exactly the notes you selected |
| **no 5** | exact apart from a missing 5th (only for chords of 4 or more notes, with at least 3 notes selected); players often leave the 5th out |
| **+N** | the chord has N notes you didn't select |

Results are ordered by: name match, then how well they match your notes, then whether your bass note is the root, then how common the chord is, then fewest notes, then by root, counting up from your key's root (in C: C, D♭, D… B).

With no notes selected, Chords lists every chord the filters allow. Scales, with no notes and no root, lists the scales on your key's root; with a root, that root; with notes, every root and scale that contains them.

If nothing matches, the results say what to try, for what is set:

- a name typed in FIND that is no chord: "No chord called that. Try a name like Cm7, F/A or G7♭9." (Scales: "No scale called that. Try a name like Dorian or Blues.")
- notes with **Contains**: "No chord holds all these notes. Take one off, or Clear."; with **Exact**: "No chord is made of exactly these notes. Try Contains."
- a filter set: "Nothing matches. Clear a filter, or Clear for everything." (with **Exact**: "Nothing matches. Try Contains, or clear a filter.")

- **Click a tile** to select it and hear it: a chord plays as a chord, a scale note by note (see [Scales view](#scales-view)).
- **Drag a chord tile** into your DAW for a one-bar clip (see [Getting it into your song](#getting-it-into-your-song)).

### Browsing with the keys

When FIND isn't taking your typing:

| Key | Does |
|---|---|
| ← / → | previous / next result |
| ↑ / ↓ | up / down one row (2 results) |
| PgUp / PgDn | 12 results back / on |
| Space | replay the selected chord or scale |
| Enter | add the chord to the shortlist, or take it out if it's already there (Chords only) |

**● Play as I browse** (on by default) plays each result as you move to it with the arrow keys or PgUp / PgDn: a chord as a chord, a scale note by note. It's shown in both Chords and Scales, and it's one setting for both.

### Lead-in

**Lead-in** (Chords, with − / + buttons) plays one of your pads before each candidate, so you hear every chord coming from the chord before it. The values are None, then "Pad 1 · Cmaj7" through "Pad 12".

With a lead-in, each audition plays the pad, a short gap, then the candidate, and the footer says so: "Played pad 2 (Dm7), then G7: the Lead-in plays a pad first." Without one, the candidate plays on its own. Changing it says what it does: "Lead-in: pad 2 (Dm7) plays before each chord you try, so you hear it coming from Dm7." or "Lead-in off: each chord you try plays on its own." The lead-in is for chords only: scales always play on their own.

### Chord details

The right column shows the selected chord:

- The name, large, with its long name and other ways of writing it, for example "C major 7th · also CΔ7, CM7, CΔ".
- A Roman-numeral pill and "in C Major", or, for a chord with notes outside the key, what it is: "borrowed from C minor" (from the parallel key, or a parallel mode: B♭maj7 in C is "borrowed from C Mixolydian"), "V7/vi, secondary dominant" (E7 in C), "vii°7/V, leading-tone chord" (F♯°7 in C), "the Neapolitan" (D♭ in C), "from A harmonic minor" (E7 in A minor), or "out of key: E♭ B♭ D♭" with the notes that aren't in the key.
- A keyboard with the notes labelled by degree.
- **NOTES**, **INTERVALS** and **VOICED** (with octave numbers, for example "C3 E3 G3"; the octave goes with the letter, so MIDI 72 spelt B♯ is "B♯3", the same key as C4).
- **INVERSION**: **Root / 1st / 2nd / 3rd**. An inversion puts a different chord note at the bottom: 1st inversion has the 3rd lowest, 2nd the 5th. At most four buttons are shown, even for 5- and 6-note chords. For a slash chord (C/E), the inversion that puts its bass at the bottom is lit to begin with.
- **VOICING**: **Close / Open / Drop-2 / Spread** (explained under [Chord tab](#chord-tab)). Changing the inversion or voicing plays the chord again.
- **▶ Play** plays it. Index chords play around C3, at velocity 0.75, through your instrument.
- **☆ Shortlist / ★ In shortlist** adds it to the shortlist, or takes it out.
- **SEND TO PAD 1–12** puts this chord on that pad: root, spelling, chord type, and the inversion and voicing you picked. The pad keeps its octave and play settings. Status: "Sent Cmaj7 (Root, Close) to pad 3." It can be undone (see [Undo and Redo](#undo-and-redo)). A slash chord (C/E) is played, starred, dragged and sent in the inversion that puts its bass at the bottom, so the pad keeps that bass note; pick another **INVERSION** first if you want a different one.
- **FOUND IN**: up to six keys that have the chord, the most telling first: your key, if the chord is in it, then the major and minor keys it belongs to (where it's the I chord, then the V, the IV...), then harmonic and melodic minor (E7: A Major, F♯ Minor, A Harmonic Minor, A Melodic Minor, B Melodic Minor). Each is spelt the way the key is written. Click one to jump to that scale in Scales mode.

### Shortlist

The **SHORTLIST** (Chords only) keeps up to 24 chords while you explore. Each keeps the inversion and voicing it was added with.

- Add a chord with **☆ Shortlist** or Enter.
- Click a chip to hear it. Click its **×** to remove it.
- A chord kept in an inversion is named with the bass it puts at the bottom: C major in 1st inversion is "C/E", on its chip, in its status ("Played C/E") and in the clip ("C over E").
- **▶ Play in order** (shown with 2 or more chips) plays them one a second, so you can hear them as a progression.
- **Drag as clip** (on the right, where it stays when **▶ Play in order** appears): drag it into your DAW for one bar per chord.
- Drag a single chip out for that chord alone.

The shortlist is saved with the project.

### Scales view

![The Scales view with the same notes, 90 matching scales; C Minor Pentatonic picked, showing its modes and the chords on each degree](../docs/images/lumen-index/scales.png)

*The Scales view with the same four notes: 90 scales contain them. C Minor Pentatonic is picked, showing its modes and the chords on each degree.*

The right column shows the selected scale:

- The root (in red) and name, with "also …" names, the number of notes and its families.
- A keyboard labelled with degrees (the octave shows as "8").
- **NOTES** and **DEGREES**. For Melodic Minor, also **DESCENDING**: the natural minor, read downward, as it's traditionally played going down.
- **▶ Play** plays the scale going up, one note at a time, 150 ms apart, each note ending as the next starts (the octave on top rings a little longer): every note of it, starting from its root in middle C's octave (C3 to B3), then the octave on top. A bebop scale plays all 8 notes and the octave, the chromatic scale all 12 and the octave. Status: "Played D Dorian through the instrument: 7 notes, then the octave."
- You hear a scale the same way when you click its tile, press **Space** (it replays the selected scale), or step to it with the arrow keys while **● Play as I browse** is on.
- **Set as key** makes it your key (spelt as the KEY menu spells it), choosing flats or sharps from the root's spelling. The scale stays picked, so **Fill pads 1–7** next fills from it. Status: "Key set to D Dorian. Shared with linked instances." It can be undone.
- **Fill pads 1–7** fills pads 1–7 from this scale at the size chosen on the Pads page (Triads, 7ths or 9ths). Status: "Pads 1–7 filled from Dorian." A scale with fewer than 7 notes fills that many pads and leaves the rest as they are: "Pads 1–5 filled from Major Pentatonic (it has 5 chords); pads 6–7 unchanged." If the pads already hold those chords: "Pads 1–7 already hold the chords of Dorian: nothing changed." Like **Fill 1–7** on the Pads page, it can be undone (see [Undo and Redo](#undo-and-redo)).
- **MODES OF …** (for scales in the Major, Harmonic minor, Melodic minor and Major pentatonic families): each mode, shown on the root that shares this scale's notes. A mode is the same set of notes started from a different degree: D Dorian has the notes of C Major. Click one to go to it.
- A scale on a black key is spelt the way that key is written (A♭ Major Pentatonic, not G♯), and its modes and chords use the same spelling as its notes (A♭ Major Pentatonic's modes start on B♭, C, E♭ and F).
- **CHORDS ON EACH DEGREE** (7-note scales): a triad and a 7th on each degree, built by stacking thirds. For other scales, **CHORDS THAT FIT EACH DEGREE**: the most common triad and 4-note chord that fit. Each shows its numeral. Click one to hear it.

---

## Pads page

![The Pads page in C major, 12 seventh-chord pads including borrowed ones, Smooth and Hints on; the 8-bar progression at bar 5 (Am7) with Dm7 and Fmaj7 glowing as usual next chords; pad 5 (G7) open on its Play tab, arpeggio Up 1/8 2 octaves](../docs/images/lumen-index/pads.png)

*The Pads page in C major with Smooth and Hints on. The 8-bar progression is at bar 5 (Am7), and Dm7 and Fmaj7 glow as usual next chords. Pad 5 (G7) is open on its Play tab, with an arpeggio set to Up, 1/8, 2 octaves.*

### Role

The switch at the top of the Pads page sets what this instance does: **Pads** (the default), **Melody guide** or **Bass guide**. This section covers Pads. For the guides, see [Melody guide and Bass guide](#melody-guide-and-bass-guide).

### The KEYS C1–C5 keyboard

The vertical keyboard on the left runs from C1 to C5. It lights the keys being sent out, the keys you're pressing, the scale notes, and the tones of the last chord (its root marked "R" in red). The trigger keys are marked "pad 1" to "pad 12" when they fall inside C1–C5. Click a key to hear that note.

### Trigger keys

The 12 keys of one octave, black keys included, play pads 1–12. **Trigger keys** sets which octave, from "C-1–B-1" to "C7–B7". The default is **C1–B1**.

Every key outside the trigger octave passes through to your instrument as normal, with Snap applied if Snap is on (see [Snap](#snap)).

The trigger octave only decides which keys play the pads. The octave each pad sounds in is set per pad in the editor.

### The 12 pads

The pads sit in a 4 × 3 grid. Each card shows:

- the pad number and its trigger key (always spelt with sharps, for example "C♯1");
- the chord name and its numeral;
- only the settings that aren't the default ("1st", "Open", "arp", "strum", "hum" and so on);
- a mini keyboard of its notes.

Pads with notes outside the key are dimmed, but still play. Borrowed chords are dimmed less. The selected pad has a red edge, and a pad flashes when it plays.

- **Click and hold** a pad to play it (at velocity 0.8) and open it in the editor on the right.
- **Drag** a pad (move more than a few pixels while holding) to drag it out as a clip. The pad stops playing when the drag starts.
- **Play it from your keyboard**: velocity follows the pad's Velocity setting. A pad played from a key goes out on the MIDI channel the key came in on, unless **Output channel** is set (see [Parameters](#parameters-the-host-can-automate)). A note that's already sounding isn't started twice.

A new instance starts with these pads:

| Pad | Chord | Notes |
|---|---|---|
| 1–7 | Cmaj7, Dm7, Em7, Fmaj7, G7, Am7, Bm7♭5 | the 7th chords of C major, octave 3 (pad 1 = C3 E3 G3 B3) |
| 8 | Cadd9 | Open voicing, 60 ms strum |
| 9 | Fmaj7♯11 | Spread voicing, 120 ms strum |
| 10 | G9sus4 | |
| 11 | A♭maj7 | Drop-2 voicing, 30 ms strum |
| 12 | B♭6 | |

Pads 11 and 12 hold the ♭VI and ♭VII chords, spelt as what they are in the key: A♭maj7 and B♭6, as **Borrowed** spells them.

### Fill 1–7, Triads / 7ths / 9ths

1. Choose a size: **Triads**, **7ths** (the default) or **9ths**. This changes nothing on the pads by itself; it's the size the next **Fill 1–7** or **Borrowed** uses. Status: "Next Fill 1–7 and Borrowed use triads. Click one to put them on the pads."
2. Click **Fill 1–7**. Pads 1–7 get the chords of your key at that size. For 7-note scales they're built by stacking thirds.

- Where a degree has no 9th chord, it uses the 7th (or the triad).
- Scales with fewer than 7 notes fill only that many pads, and the status says so: "Pads 1–5 filled from the key (Major Pentatonic has 5 chords); pads 6–12 kept. Pad sets ▾ has Undo."
- Each filled pad is reset to root position and spelt from the key. It keeps its voicing, octave and play settings.
- Pads 8–12 are kept.
- It can be undone: status "Pads 1–7 filled from the key. Pads 8–12 kept. Pad sets ▾ has Undo."
- If the pads already hold the key's chords at that size, nothing changes and no undo step is made: "Pads 1–7 already hold the key's chords: nothing changed."

### Borrowed

A borrowed chord comes from the parallel key: the key on the same root with the other quality (C minor if you're in C major, A major if you're in A minor), or from another mode on the same root. Borrowed chords give a lot of bittersweet and shoegaze progressions their colour.

**Borrowed** fills pads 8–12 with up to five chords that aren't already in your key, at the size chosen for Fill:

| Your key | Chords, in this order |
|---|---|
| Major-type | iv, ♭VI, ♭VII, ♭III, v, then ♭II, ii°: from the parallel minor (♭II is the Neapolitan, from Phrygian) |
| Minor-type | V, IV, I, ii, ♭II, then iii, vi: from the parallel major, but V7 from harmonic minor, the 7th and 9th on IV (D7 in A minor) from melodic minor, and ♭II, the Neapolitan, from Phrygian |

- Triads give triads; 7ths give m7, maj7 or 7 (and ii° becomes m7♭5); 9ths give m9, maj9 or 9 (ii° stays m7♭5).
- The chords are spelt properly (A♭, not G♯, in C). In C major with 7ths you get Fm7, A♭maj7, B♭7, E♭maj7 and Gm7.
- The status says where each comes from, for example in C major with 7ths "Pads 8–12 borrowed: iv7 ♭VImaj7 ♭VII7 ♭IIImaj7 v7 from C minor. Pad sets ▾ has Undo.", in A minor "Pads 8–12 borrowed: V7 from A harmonic minor, IV7 from A melodic minor, Imaj7 ii7 from A major, ♭IImaj7 from A Phrygian. …". It can be undone.
- A key that isn't a 7-note scale (Whole Tone, a pentatonic, Blues…) has no parallel major or minor: it borrows from the natural minor on its root if it has a major 3rd, otherwise from the major. If the pads already hold those chords, the status says nothing changed.
- If there's nothing to borrow: "This key has no borrowed chords that aren't already in it."

### Smooth

Voice leading means moving each note of one chord to a nearby note of the next, the way a keyboard player's hands move, instead of jumping the whole shape. **Smooth** (off by default) does this for you.

With Smooth on, each pad you play, from a key, a click or the progression, picks the inversion and octave (the pad's own, one up or one down) whose notes move least from the chord played just before. C to F, for example, keeps the C and moves E and G up a step.

- It prefers to stay within a fourth of the pad's own register, and the middle of the chord never moves more than a major sixth (9 semitones) from it.
- The first chord plays as voiced.
- "Just before" means the last pad this instance played, whatever played it.
- It also applies inside **Drag all pads** and **Drag strip**.

Smooth is saved with the project.

### Hints

**Hints** (on by default) lights up, after a pad plays, the pads that usually come next:

| Glow | Meaning |
|---|---|
| **Bright red** | the usual next chords (all of them) |
| **Dim red edge** | common choices (at most 2) |
| **Pale glow** | a twist that works, such as a borrowed chord or a deceptive move (at most 1) |

Pads holding the same chord as the one just played are skipped. Major and minor keys have their own tables. For a chord the tables don't cover, the hint goes by how the root moves: down a fifth is strong; up a step, or down a third, is good.

Hints need a pad to have been played first. The setting is saved with the project.

### The pad editor

![Pad 2 (Dm7, Open voicing) held, its Chord tab showing root, chord type, inversion, voicing, octave and notes out (D3 A3 C4 F4); G7 glowing as the usual next chord](../docs/images/lumen-index/pad-editor.png)

*Pad 2 (Dm7, Open voicing) held. The Chord tab shows its root, chord type, inversion, voicing, octave and the notes it sends out (D3 A3 C4 F4). G7 glows as the usual next chord.*

The right column edits the selected pad. Its header shows "PAD n", its trigger key, the chord name, a numeral pill, and "in C Major" or "out of key". It has two tabs, **Chord** and **Play**; the open tab is saved with the project.

Every change in the pad editor can be undone (see [Undo and Redo](#undo-and-redo)). Quick changes to one control, such as dragging **STRUM** or clicking **+** several times, count as one step.

#### Chord tab

Every change plays the pad briefly, with its strum.

- **ROOT**: 12 buttons, each spelt as the pad's chord would be named on it in the key (for a major 7th in C: D♭, E♭, A♭, B♭; for a °7: C♯, D♯, F♯, G♯). Choosing a root resets the spelling to the key's.
- **CHORD**: a scrolling grid of all 50 chord types, by symbol ("maj" for major; "quartal" for 7sus4 without its 5th).
- **INVERSION**: **Root / 1st / 2nd / 3rd**.
- **VOICING**: how the notes are spread out. Voicings apply to chords of 3 or more notes.

  | Voicing | What it does |
  |---|---|
  | **Close** | the notes stacked as tightly as they come |
  | **Open** | the second note up an octave |
  | **Drop-2** | the second note from the top down an octave: a wider shape common in jazz piano and guitar |
  | **Spread** | the lowest note down an octave and, with 4 or more notes, the third note up an octave |

- **OCTAVE**: 0 to 6, default 3. Octave 3 puts the root at C3 (middle C).
- **NOTES OUT**: the notes the pad will play.

#### Play tab

- **STRUM**: from 0 ("off") to 250 ms, with a direction: **Up** (lowest note first), **Down** (highest first) or **Rand**. The strum time is spread evenly from the first note to the last. Strum is dimmed while an arpeggio is on.
- **VELOCITY**:
  - **Follow** (default) follows how hard you play, through a curve: **Soft** (light playing comes out louder), **Linear** (default, as played) or **Hard** (you have to play harder for loud notes).
  - **Fixed** plays every note at one velocity, from 1 to 127 (default 100).
- **Using the two sliders** (STRUM, and VELOCITY when Fixed):
  - Click or drag with the left button: the value jumps to the mouse.
  - **Fine adjustment** (since 1.4.1): drag with the right button, or with **Ctrl** held (Mac: **Cmd** or **Option**). The value doesn't jump; it moves from where it was, 10 times more finely (about 22 pixels for 5 ms of strum, about 9 pixels for 1 of velocity). A right-click alone changes nothing.
  - **Mouse wheel** over a slider: one step each notch, 5 ms of strum or 1 of velocity (up for more).
  - A whole drag, or a run of wheel steps, is one undo step.
- **ARPEGGIO**: plays the chord one note at a time while the pad is held.

  | Mode | Plays |
  |---|---|
  | **Off** | the chord (default) |
  | **Up** | low to high |
  | **Down** | high to low |
  | **Up/Dn** | up then down, without repeating the top and bottom notes |
  | **Rand** | random order, never the same note twice in a row |
  | **Chord** | the whole chord, unstrummed, on every step |

  - Rate: **1/4**, **1/8**, **1/8T**, **1/16** (default), **1/16T**, **1/32** (T is triplet).
  - **OCTAVES**: 1 (default), 2 or 3. The notes repeat up over that many octaves (at most 24 notes). In Chord mode this reads "OCTAVES (NOT USED)".
  - **GATE**: 25%, 50%, 75% (default) or 100%: how much of each step the note lasts.
  - It runs at the song tempo (120 bpm if the host gives none). While the transport runs, it locks to the song's grid: the first step plays when you press, and the next lands on the next grid line (or the one after, if the next is less than half a step away). When the song jumps (you click the playhead, it loops, or you start it while holding the pad), the next step goes back on the grid the same way.
- **HUMANIZE TIMING**: **Off**, **5 ms**, **10 ms**, **20 ms** or **35 ms**. Each note, or arpeggio step, comes up to that much late, at random.
- **HUMANIZE VELOCITY**: **Off**, **5%**, **10%**, **20%** or **30%**. Each note's velocity varies by up to that much, up or down.

Humanize works on chords, strums and arpeggios.

#### Buttons under the editor

- **▶ Play** plays the selected pad while you hold the mouse.
- On the Chord tab, **Copy voicing to all pads** copies only the voicing to the other 11 pads. It doesn't copy the root, chord, inversion or octave. Status: "Voicing copied to all pads."
- On the Play tab, **Copy play settings to all pads** copies the whole Play tab to the other 11 pads: strum and its direction, velocity mode, value and curve, arpeggio mode, rate, octaves and gate, and both humanize settings. Status: "Strum, velocity, arpeggio and humanize copied to all pads."

Both copy buttons can be undone.

### Pad sets, Undo and Redo

A pad set saves all 12 pads, with every Chord and Play setting, plus the progression (its slots, slot length and loop length). It doesn't save the progression's On/Off, Smooth, Hints, the key or the shortlist. Pad sets are shared by every project on the computer.

Click **Pad sets ▾** to open **PAD SETS**. When a set is loaded, the button shows its name instead.

**To save a set**

1. Type a name in the field ("Name this set"). If a set is loaded, its name is already there.
2. Click **Save**, or press Enter. If the name exists, the button reads **Replace** and overwrites it.

Names can use plain letters, digits, spaces and `- _ . ( ) ' # & + ,`, up to 39 characters. The field takes only those, so the name saved is the one shown: another character isn't typed, and the footer says "A set's name can have letters, digits, spaces and - _ . ( ) ' # & + , only."; at 39 characters the field stops taking more and says "That's the longest a set's name can be (39 characters)." (Spaces and dots at the end are left off when it's saved.) Status: "Saved pad set "lo-fi keys"." With no name: "Type a name for the set first."

**To load a set**, click its name in the list (sorted A–Z; the loaded set has a red dot). Status: "Loaded pad set "X". Pad sets ▾ has Undo." Loading a set from 1.0.5–1.0.7, which had no progression, keeps your current progression.

**To delete a set**, click its **×**, then **Delete** to confirm.

In the name field, Enter saves, Esc closes the menu and Tab leaves the field.

#### Undo and Redo

**Undo** and **Redo** sit at the bottom of the **PAD SETS** menu. They take back what you change in the pads, the progression and the key, up to 32 steps.

- **Undo** names what it will take back, for example **Undo Fill 1–7**, **Undo Send to pad 3**, **Undo pad 2 voicing** or **Undo load of "lo-fi keys"**. On the right, the menu shows how many steps there are to undo ("3 steps"). Click it to go back one step; the menu stays open, so you can click again. Status: "Undid Fill 1–7."
- **Redo** appears on the right once you've undone something, named the same way. It puts back what you undid, one step at a time, until you make a new change: a new change clears Redo. Status: "Redid Fill 1–7." Neither button moves when the other appears or runs out, so clicking Undo again after the last step never redoes.
- With nothing to undo or redo, the menu shows "Click a set to load it. Sets are shared by every project." instead.

**From the keyboard**: **Ctrl+Z** undoes, **Ctrl+Shift+Z** or **Ctrl+Y** redoes (on a Mac, **Cmd+Z**, **Cmd+Shift+Z** or **Cmd+Y**). They work when the Lumen-Index window has the keyboard (click in it first) and you're not typing in FIND or a set name. Whether a host such as Bitwig passes these keys on to a plug-in window depends on the host; the **Undo** and **Redo** buttons in **Pad sets ▾** always work.

**What a step puts back**: all 12 pads, with every Chord and Play setting; the progression (its slots, slot length and loop length; its **On / Off** is left as it is now); and the key (root, scale, and flats or sharps). Linked instances follow the key back. Undoing the load of a pad set also puts back the name the **Pad sets** button showed before.

**What makes a step**:

- **Fill 1–7** and **Borrowed** on the Pads page
- **Fill pads 1–7**, **Set as key** and **Send to pad** on the Index
- Read's **Pads only** and **Pads + progression** (with **Set to <key>** on, the key too)
- loading a pad set
- any change in the KEY menu
- filling and clearing progression slots, and changing **SLOT** or **BARS**
- **Copy voicing to all pads** and **Copy play settings to all pads**
- every control in the pad editor

A click that changes nothing makes no step. Quick repeated changes to one control on one pad count as one step: dragging **STRUM** or **VELOCITY**, or clicking **+** on **OCTAVE** several times, as long as each change comes within 1.5 seconds of the one before. Clicking through roots or scales in the KEY menu, and filling progression slots one after another, work the same way. After an Undo or a Redo, the next change is a step of its own.

**Not undo steps**: saving or deleting a pad set file, the progression's **On / Off**, the role, **Snap** and **Snap to**, the link number, **Output channel** (**CH** in the apps), **Trigger keys**, **Smooth**, **Hints**, the Triads / 7ths / 9ths choice, and anything on the Index other than the buttons above (filters, notes, the shortlist).

**How long it lasts**: the history is kept by the plugin, not by its window, so closing and reopening the plugin window doesn't lose it. It isn't saved with the project, and it starts empty when a project loads (in the standalone apps, when the app starts). After 32 steps, the oldest goes.

### Drag all pads

Drag **Drag all pads** onto the arranger for a 12-bar clip, one bar per pad, with their arpeggios, strums and humanize, and with Smooth across them if it's on. The clip is named "Lumen-Index pads", or after the loaded pad set.

---

## Progression

The **PROGRESSION** strip under the pads plays your pads in order, in time with the song.

### Slots and length

- **SLOT**: **1/4** (a beat), **1/2**, **1** (default) or **2** bars per slot.
- **BARS**: a loop of **4** (default), **8** or **16** bars.
- The number of slots is the loop length divided by the slot length, up to 16. So beat slots allow a 4-bar loop and half-bar slots at most 8 bars. Choosing a longer loop switches the slots to the shortest length that fits it (8 bars with beat slots: half-bar slots; 16 bars: 1-bar slots), and choosing a shorter slot shortens the loop to fit (beat slots: 4 bars). The footer says when it had to: "Beat slots loop 4 bars at most: BARS set to 4." or "8 bars needs half-bar slots: SLOT set to 1/2."
- Changing **SLOT** or **BARS** keeps every chord on the beats it played:
  - Shorter slots: each chord fills the slots covering its beats (a 1-bar Cmaj7 becomes two half-bar slots holding Cmaj7, so it sounds the same). "SLOT 1/2: every chord keeps its beats."
  - Longer slots: each slot takes the chord playing at its start; a change inside a slot is gone, and the footer counts them: "SLOT 2: each slot plays the chord at its start; 2 changes inside a slot gone (Undo)."
  - A longer loop keeps the old one as it was and adds empty slots (rests) after it: "Loop of 8 bars: bars 5–8 empty, click a slot to fill them." A shorter loop cuts the end: "Loop of 4 bars: bars 5–8 cut."
  - Each change is one undo step.

Each slot shows its bar number, the chord, and "pad n" (with "· arp" if the pad arpeggiates; narrow slots show just the pad number).

A new instance starts with slots 1–4 set to pads 1, 6, 4 and 5 (I vi IV V: Cmaj7, Am7, Fmaj7, G7).

### Filling it

1. Click a slot. It lights up.
2. Click pads. Each pad goes into the lit slot and the light moves to the next one. While you fill, the footer shows "Click pads to fill the progression in order · Esc stops".
3. To stop, click the lit slot again or press Esc. Clicking anything other than a pad, a slot or Off/On also stops filling. After the last slot, clicking a pad just plays it.

- **Holds**: the same pad in two slots in a row holds the chord. The second slot shows "—".
- **Rests**: right-click a slot to clear it (Control-click on a Mac). An empty slot shows "+" and is silent. Status: "Slot 4 cleared (silence)."
- Filling and clearing slots, and changing **SLOT** or **BARS**, can be undone (see [Undo and Redo](#undo-and-redo)). Switching the progression **On** or **Off** isn't an undo step.

### On / Off and timing

Click **On** to switch it on (default **Off**). Status: "Progression on: it plays while the transport runs."

- It plays only while the host's transport runs (in the apps, while MIDI clock runs after Start), and only in the Pads role. When it's on but stopped, the strip says "waiting for play" (apps: "waiting for clock"). While playing it says "bar x / y", and the playing slot is red with a progress line.
- It's locked to the song's bar 1, not to when you pressed On. The slot comes from the song position, so it follows loops and jumps in the song: jump to bar 3 of a 4-bar loop and you hear slot 3.
- Chord changes land exactly on the beat. 4/4 is assumed.
- Pads keep their arpeggio, strum, humanize and Smooth. Strip chords play at velocity 0.8 through the pad's velocity curve (or at the pad's Fixed velocity), on the Output channel (or channel 1).
- **Pad takeover**: press a pad yourself (a key or a click) and it replaces the strip's chord until you let go; then the strip comes back.

The progression, including On/Off, is saved with the project. Pad sets save it without On/Off.

### Drag strip

Drag **Drag strip** onto the arranger for the whole progression as one clip, the length of the loop. Held chords are written as one long chord, rests as silence, and slot lengths are kept. Smooth is applied if it's on. A strip of only rests is named "Lumen-Index progression".

---

## Read chords

![The Read panel after dropping "Verse sketch.mid": 9 chords over 8 bars (Am F C G/B Am F, Dm and E for 2 beats each, Am), "Set to A Natural Minor" switched on, Read again / Pads only / Pads + progression](../docs/images/lumen-index/read.png)

*The Read panel after dropping "Verse sketch.mid": 9 chords over 8 bars (Am, F, C, G/B, Am, F, Dm and E for 2 beats each, Am), with "Set to A Natural Minor" on.*

New in 1.4. Read finds the chords and the key of a clip or a MIDI file and puts them on the pads and the progression.

Click **Read ▾** on the Pads page (Pads role) to open **READ CHORDS**. While Read is waiting the button shows "● Waiting"; while reading, "● Reading".

### Read a clip as it plays

1. Click **● Read**. The menu shows "Waiting for the song · Play the clip on this track. Reading starts with its first note." and **Cancel**. Until reading ends, the footer comes back to "Reading: play the clip on this track." whenever no newer message is showing.
2. Play the clip **on the same track** as this Lumen-Index, so its notes come into it.
3. Reading starts at the first note while the transport plays. The menu shows the bar and the note count, with **Done** and **Cancel**.
4. It stops by itself when the song loops back, the transport stops, or after 64 bars. Or press **Done**. Notes still held then end where the song stopped or looped; if that was less than a beat after a bar line, they end on the bar line (a last chord held until you stop doesn't get an extra bar).

When it ends, the footer says "Read N chords over N bars. Click one to hear it, then put them on the pads." If it found nothing: "Read heard no chords. Press Read again, then play the clip on this track." **Cancel** gives "Reading cancelled."

- The trigger keys aren't read: they play pads instead. If your clip uses that octave, move **Trigger keys** out of its way first.
- Live reading reads every MIDI channel.
- Read needs the host's transport position. It has been tested in Bitwig. In the standalone apps, Read runs while MIDI clock runs after Start.

### Read from a MIDI file

- **Drop a MIDI file** on the window, from Explorer or Finder, a DAW export or a MIDI pack. A drop works on any page; the window switches to Pads with the Read menu open. While a file is over the window, it shows "Drop to read its chords".
- Or click **Open file…** and choose one.

If several files are dropped, only the first is read.

You can't drag a clip from the arranger into the window: Bitwig and Logic keep arranger clip drags inside themselves. Export the clip as MIDI and drop the file, or use Read as it plays.

**What files work**

- Standard MIDI files (type 0 or 1), up to 16 MB, up to 4096 notes.
- Drums (MIDI channel 10) are left out, unless the file has nothing else.
- A file with more than 4096 notes (since 1.4.1): the drums are left out first, so a long drum track doesn't crowd out the chords; if there are still too many, the earliest 4096 in time are read, whichever track they're on. (Before, the first 4096 in the file's order were read.)
- The file's tempo is ignored; it's read in beats.
- A damaged or cut-off file gives whatever could be read.

**Errors**

- "notes.txt isn't a MIDI file, so there are no chords to read in it. Drop a .mid file." (with the file's name)
- "Couldn't read <name>: it's empty, too big, or another program has it open."

### What it reads well, and its limits

- It reads block chords, arpeggios, slash chords, and a melody over chords. Short notes count for less, 7ths and 9ths count only when they're held like the rest of the chord, and the chord's root must be present.
- **Changes are read where you play them** (since 1.4.1), not bar by bar: three chords in a bar, or a change on the "and" of a beat, read as played. Each change is placed on the nearest place a hand would mean: the bar line if within a third of a beat, else the beat, the 8th or the 16th.
  - A change costs a little, more off the beat and more where no chord is struck at once (an arpeggio or a melody), so a melody or passing notes over a chord don't split it.
  - Played loose and legato is fine: notes a little early or late count as one start, and the end of a chord held into the next isn't counted with the next.
  - It tells chords that share notes apart by what a listener hears: notes that never sound together (F then G is not G11/F), a bass that moves (C then C/E), and a root that stops (E♭m7 then G♭).
  - Neighbouring chords in a bar with the same root and triad are merged, and a gap of less than a bar extends the chord before it.
- Bars are 4 beats. Counting starts at the bar line at or before the first note (a first note slightly early still starts its bar).
- **A clip that doesn't start on the bar**: a clip that starts up to 1 beat after a bar line and lasts whole bars is measured from its first note. This covers a clip dropped a sixteenth late on Bitwig's grid; it still reads with the right length. Any other clip that starts up to a beat late is also measured from its first note when its changes then land nearer the bar lines and beats.
- Only the 41 chord types of 1.4 are recognised (not the 9 that 1.4.1 added).
- At most 64 bars, and at most 256 chords and rests.
- **The key it finds** is always a major or natural minor key. It's worked out from the notes, how much of the time the chords fit the key, and whether the first or last chord is the home chord.

### The result

The heading shows "N chords · N bars", with the source on the right: the file name, or "the clip". Below it, the chords in order, each with its length ("1 bar", "1½ bars", "2 beats", "½ beat" and so on); rests show as "rest". After four rows it shows "+N more".

- **Click a chord** to hear it.
- **KEY · Set to <key>**: a switch that also changes your key to the one found. It's on when the found key differs from yours. If it's the same, it shows "your key already".
- **Pads only**: puts the chords on the pads.
  - Each different chord goes on once, on pads 1, 2, 3… in the order they first come.
  - With more than 12 different chords, the 12 heard longest go on, still in order.
  - Each pad gets the root, the chord type, the inversion that puts a slash bass at the bottom, and the octave nearest where it was played.
  - Pads keep their voicing and play settings. Pads beyond the count are kept.
- **Pads + progression** (red): the same, and it also writes the progression.
  - Slot length: 2 bars if every chord starts on a 2-bar line, 1 bar if every chord starts on a bar line, half a bar if every chord starts on a half bar, otherwise a beat (chords played by hand count within a third of a beat).
  - Loop: the clip's length rounded up to 4, 8 or 16 bars (half-bar slots: at most 8; beat slots: 4).
  - The slot length is judged on the bars the progression will hold, not on the bars cut off after them: a 56-bar clip whose first 16 bars change once a bar gets 1-bar slots over 16 bars, whatever comes later.
  - A clip longer than 4 bars with changes quicker than half a bar (in the bars it holds) gets half-bar slots: each slot gets the chord heard longest in it. **Pads only** keeps every chord.
  - Each slot gets the chord heard longest in it. Chords that didn't make it onto the pads become rests.
  - A clip shorter than the loop repeats to fill it. A clip longer than 16 bars is cut to its first 16.
  - **It doesn't switch the progression On.** Click **On** yourself, then press play.
- **Read again** clears the result and takes the menu back to the start: press **● Read**, or drop or open a file.

After either button the menu closes and the Pads page shows. Status, for example: "Pads 1–4 and the progression from My verse, in A Natural Minor. Pad sets ▾ has Undo."

**Undo** (in **Pad sets ▾**, or Ctrl+Z) puts back the pads, the progression and, if **Set to <key>** changed it, the key (see [Undo and Redo](#undo-and-redo)).

If nothing was found, the panel says "No chords in it", with "Its notes never sound as a chord or an arpeggio." or "It has no notes.", and **Read again**.

---

## Melody guide and Bass guide

![A Melody guide following the pads track on Link 1, live chord Am7/E with its chord tones, the last notes played, and eight Caught cards (Dm7/F, G7, Cmaj7/G, Am7/G, Fmaj7, G7/F, Em7, Am7/E) each with the notes played over it](../docs/images/lumen-index/melody.png)

*A Melody guide following the pads track on Link 1. The live chord is Am7/E, with its chord tones, the last notes played, and eight Caught cards (Dm7/F, G7, Cmaj7/G, Am7/G, Fmaj7, G7/F, Em7, Am7/E), each with the notes played over it.*

A guide is a second Lumen-Index on another track, for example a lead or bass synth. It shows the chord your pads track is playing and checks what you play against it.

### Setting one up

1. Put Lumen-Index first on the melody or bass track.
2. On its **Pads** page, set the role to **Melody guide** or **Bass guide**.
3. Give it the same link number as the pads track (both start on 1). Use the **LINK** chip in the header, or **FOLLOW CHORDS FROM** in the right column: **Off**, **Link 1**, **2**, **3**, **4**. They're the same setting.

The footer hint reminds you: "Same link number here and on the pads track".

### What the guide shows

- **The linked chord**: "LINK 1 · FROM THE PADS TRACK", the chord name, large, with its numeral ("V7 in C Major"), and a tile for each chord tone. The root tile is red and labelled "root"; the others show their degree. The **Bass guide** dims every tile except the root and the 5th, the safe notes for a bass line.
- With no chord yet: "No chord from the pads track yet", and under it how to get one: "Put Lumen-Index on another track, set it to Pads, Link 1." (with this track's link number). With the link off: "Link is off".
- **LAST NOTES ON THIS TRACK**: the last 4 notes you played here, each labelled "chord tone · 3 of G7", "scale note · 6 of C Major" or "outside C Major", in colour.
- **The keyboard on the left** lights the chord's tones: "root" and "chord tones" in the Melody guide, or "root (play this)" and "5th" in the Bass guide. Scale notes are shaded. A key you press that's outside the key is outlined red ("outside the key") for as long as you hold it, whatever Snap does with it: with Snap **Off** the note plays as it is and is only marked; with Snap on it's also moved or muted. **LAST NOTES ON THIS TRACK** labels it "outside C Major" too.

### Snap

Snap moves or mutes the notes you play that fall outside the scale or the chord, so you can't hit a wrong note.

- **SNAP NOTES**:

  | Setting | Notes outside the scale or chord… |
  |---|---|
  | **Off** (default) | play as they are; the guide only shows them (a key outside the key is still outlined red) |
  | **Nearest** | move to the nearest allowed note (a tie goes down) |
  | **Up** | move up to the next allowed note |
  | **Down** | move down to the next allowed note |
  | **Mute** | don't play |

- **SNAP TO**: **Scale** (default) or **Chord tones**. Chord tones uses the chord from the pads track. With no chord yet, it falls back to the scale.

Snapped notes keep their note-offs, aftertouch and expression on the moved note, so nothing sticks. Muted notes' aftertouch and expression are dropped.

Snap and Snap to are shown only in the guide roles. In the Pads role they still act on the keys outside the trigger octave, and you can set them as host parameters; the Snap to Chord tones setting then uses the pads track's own last chord.

### Caught

**CAUGHT** keeps the last chords from the pads track, and what you played over each. When the changes come fast, you can see what just went by.

- Up to **8 cards** (4 before 1.4.1), oldest on the left. Each card shows:
  - how long the chord lasted ("2 bars", "3 bts"…), or **NOW** (with a red outline) for the chord sounding now. When the transport stops, the pads track's last chord stops sounding, so its card ends there and no card says NOW until a chord comes again;
  - its numeral and name, or "No chord" for a time with no chord from the pads track that you played over (a time with no chord and nothing played over it, such as the moment before the first chord when the transport starts, makes no card);
  - the notes you played over it: chord tones bright, other key notes grey, notes outside the key red (the last 48 per chord are kept; "+N" means N more than fit on the card);
  - a small piano roll of those notes in time.
- Notes played just before a chord change (up to 120 ms) count with the new chord, since the link reports changes slightly late. While the song plays, a chord that reaches the guide up to 120 ms after a beat starts on that beat, so lines dragged out keep their timing against the chords.
- When the chord goes (the pads track moves to another link number, stops being Pads, is deactivated by the host or deleted, or you set this track's link to Off), Caught stops at the last real chord: its card ends there, and no "No chord" card is added after it (since 1.4.1). Notes you play until the next chord comes aren't caught, except those just before it.
- **Click a card** to hear its chord (in the Bass guide, an octave lower).
- **Drag a card** for a clip of what you played over that chord, at your velocities, in time. It's named "Line over G7".
- **Drag line**: all the cards' notes in one clip ("Line over Dm7 - G7 - …").
- **Drag chords**: the caught chords as a clip ("Caught Dm7 - G7 - Cmaj7"), the first one at the clip's start. Each is in root position, close voicing, around C3 (Bass guide: C2), velocity 96, as long as it really lasted. The clip is rounded to the nearest beat.
- **Clear** starts over: "Catcher cleared."

Caught runs on the song tempo even while the transport is stopped, so it catches when you just play pads by hand. It only works in the guide roles. Its contents aren't saved with the project.

---

## Link

Link connects Lumen-Index instances so they share the key and the chord.

- **Numbers**: **Off** or **1** to **4**. Instances on the same number form a group. New instances start on **1**, so two Lumen-Index instances in one project are linked straight away.
- **Change it**: click the **LINK** chip for the next number, right-click (Mac: Control-click) for the one before. In a guide role, **FOLLOW CHORDS FROM** in the right column does the same. It's also the host parameter "Link".

### How the key travels

The key, flats/sharps and scale are shared both ways by every instance in a group: change the key on any of them and the others follow. The last change wins. A new instance joining a group takes the group's key, and so does one that comes back to it (from Off or another number) or a guide that loads a preset: it doesn't change the others. Its own key goes to the group only if no one else there has one yet. When a project opens with linked tracks saved in different keys, they all take the Pads track's key (with two Pads tracks on one link, the one that opens last).

To keep two pads tracks in different keys, put them on different link numbers, or set one to Off.

### How the chord travels

- An instance in the **Pads** role sends the chord it's playing. A pad's chord is sent at once, so an arpeggiated pad is named correctly even while it plays one note at a time.
- Chords you play by hand on the pads track (outside the trigger keys) are sent too, once they've been held steady for a moment, and not while pads are sounding.
  - Only new notes change the chord (since 1.4.1). Letting go of some notes, between chords or one finger at a time, leaves the chord as it was, so nothing "in between" (a C5 on the way out of C) is sent or caught.
  - A chord played before the last one is let go (legato): it waits up to 150 ms for the last one's notes to lift, then names the new chord. Notes still held after that (a held bass, say) count with it.
- Guides show, and snap to, the chord from the other instance in their group (the last one to send).
- **When a pads track leaves** (since 1.4.1): if a Pads instance moves to another link number, switches to a guide role, is deactivated by the host or is deleted, its chord leaves the group with it: the guides on that number show "No chord from the pads track yet" instead of its last chord. If another pads track on the same number sent a chord after it, that chord stays. The key stays as it is: every instance keeps the group's key as its own. Back on the number (or active again), the pads track's next chord is sent, even if it's the same chord as before.

### With windows closed

The link, Caught and Read keep working with every plugin window closed. (In Bitwig on Windows this was fixed in 1.4; before that they stood still with all windows closed.)

### On a Mac

On a Mac the link only reaches instances running in the same process. If your host runs plug-ins in separate processes, linked tracks may not see each other. If a guide never shows the pads track's chord on a Mac, check your host's plug-in hosting setting.

---

## Getting it into your song

### Everything you can drag out

Press on any of these, move a few pixels, and drop on the arranger or a launcher slot (in Logic, on a track):

| Drag | Clip |
|---|---|
| A **pad** | one bar of its chord, with its inversion, voicing, octave, strum, arpeggio and humanize |
| A **chord tile** on the Index | one bar, close voicing, in root position or, for a slash chord, with its bass at the bottom (the selected tile uses the inversion and voicing you picked) |
| A **shortlist chip** | one bar of that chord, with its saved inversion and voicing |
| **Drag as clip** (shortlist) | one bar per shortlist chord |
| **Drag all pads** | 12 bars, one per pad, with arpeggios, strums and humanize; Smooth across them if on |
| **Drag strip** | the progression for the length of the loop: held chords as one chord, rests as silence, slot lengths kept; Smooth if on |
| A **Caught card** | the notes you played over that chord |
| **Drag line** | the notes over all the Caught cards |
| **Drag chords** | the Caught chords at their real lengths |

Clicking a drag-only button (**Drag all pads**, **Drag strip**, **Drag as clip**, **Drag line**, **Drag chords**) without dragging just shows a hint, for example "Drag this button into the arranger: all 12 pads become a clip, one bar each, with their arpeggios."

After a drop, the footer says "Dropped Cmaj7 (1 bar)." or "Dropped Line over G7.", with the chords named as the window names them ("Dropped C/E (1 bar).", "Dropped B♭7 (1 bar)."). If the drag went nowhere: "Drag cancelled. Drop on the arranger or a launcher slot to make a clip." On Windows, press Esc during a drag to cancel it.

You can drag out of the standalone apps too, into any DAW.

### What the clip contains

- **Real notes**: the chord as voiced, not the trigger key. Strums are written as staggered notes, arpeggios as their steps (filling the chord's length, with the gate applied), and humanize as the small timing and velocity changes.
- **Length**: each chord is one 4-beat bar, unless its slot length says otherwise.
- **Velocity**: the pad's Fixed velocity, otherwise 100 (Index and shortlist chords: 100). Caught lines keep your own velocities.
- **No overlapping notes** (since 1.4.1): when the same key is struck again while it's still sounding (a Caught line, chords together with your notes, fast arpeggios, strums, humanize), the earlier note ends where the later one starts. Every note starts where it did, and the later one keeps its full length, so no key ever has two notes at once in the file.
- **Tempo**: the clip carries no tempo and no time signature. Its notes are placed in beats, so it lands at your song's tempo, and Bitwig doesn't ask whether to import a tempo. Strum and humanize times are worked out from the song's tempo at the moment you drag (in the apps, the MIDI clock's tempo; if clock has stopped, the last tempo it had; 120 bpm if no clock has come in).
- **Where it lands**: Bitwig drops a dragged clip onto its grid (often 1/16).
- **Name**: the clip name spelt in plain letters (♯ becomes #, ♭ becomes b, "/" becomes " over ", for example "F#m7 over C#"). Several chords are joined as "Am - F - C - G", cut after about 40 characters.
- At most 24 chords and 256 single notes per clip.
- Each drag starts Smooth fresh: a single pad drags as it's set, and Drag all pads and Drag strip lead from chord to chord within the clip.

### Recording versus dragging

In Bitwig, recording the track can give you the notes you played (the trigger keys) rather than the chords Lumen-Index sends, because Bitwig records the notes coming into the track, before its devices. Dragging the chords out always gets them into your song.

With the Mac standalone app, other apps (Logic included) can record what Lumen-Index sends through its virtual output (see below).

---

## Standalone apps

The apps have the same window and engine as the plugin, and talk to MIDI gear directly, with no DAW needed: keyboard in, synth out.

### The footer

- **MIDI IN <device> ▾**: your keyboard or controller. The menu (**MIDI INPUT**) has a **None** entry.
- **MIDI OUT <device> ▾**: your interface or synth (**MIDI OUTPUT**, also with **None**).
- **CH**: the channel everything goes out on. **CH same** keeps the channel each note came in on; **CH 1** to **CH 16** sends everything on that channel. Click for the next channel, right-click (Mac: Control-click) for the one before; it wraps round. Status: "Everything goes out on channel 5. Right-click: back." or "Notes go out on the channel they came in on."

### MIDI clock

Send MIDI clock from your drum machine, sequencer or DAW to the MIDI IN device:

- Arpeggios follow the clock's tempo, and its grid while it plays.
- **The progression and Read run only while clock runs after Start** (or Continue) on your clock source. The strip shows "waiting for clock" until then. Status on switching it on: "Progression on: it plays while MIDI clock runs (Start on your clock source)."
- Start resets to beat 0, Continue resumes, Stop stops, and Song Position Pointer is followed. Start plays at once, also from a source that sends clock only while it plays, and notes that come with the Start count as played on beat 1 (Read reads them, the progression's first chord starts on it).
- If clock stops arriving for half a second it counts as gone, and the tempo falls back to 120 bpm.

Without clock, everything runs at 120 bpm. There's no tempo setting in the apps.

### Pass-through

- Clock and Start/Stop/Continue pass on to MIDI OUT.
- Other channel messages (CC, pitch bend, program change, aftertouch) pass on, on the channel set by CH.
- SysEx isn't passed on.

### Windows app (Lumen-Index.exe)

- On first run it opens the first MIDI output (often the Microsoft GS Wavetable Synth) and **no input**. Pick your keyboard under MIDI IN.
- **Plug and unplug gear while it runs** (since 1.4.1): the MIDI IN and MIDI OUT menus update within a few seconds, with no restart. A device you chose that's unplugged stays chosen, shown as "(not connected)", and opens again by itself when it's back. Two identical interfaces are told apart.
- Windows lets only one program use most MIDI devices at a time. If a device won't open, close the other program that has it (a DAW, say), or switch the device off in that program's MIDI settings.

### Mac app (Lumen-Index.app)

- **Virtual output**: the first MIDI OUT entry is **Lumen-Index (virtual, for other apps)**. Logic, or any other app, sees it as a MIDI source called "Lumen-Index" and can record from it.
- On first run it picks the first MIDI input and the virtual output.
- **Gear you unplug and plug back in while it runs comes back by itself**, by name.
- Closing the window quits the app. The window position is remembered.

### Settings

The apps save the MIDI IN and OUT device names and everything the plugin would save with a project (key, pads, progression, Smooth, the page and so on). They're written when you quit and whenever you pick a device, and devices are reopened by name on start.

- Windows: `%APPDATA%\Lumen-Index\settings.txt`
- Mac: `~/Library/Application Support/Lumen-Index/settings.txt`

---

## Saving and pad set files

### Saved with your project

- The key, accidentals and scale, the role, Snap and Snap to, the link number, the Output channel and the trigger keys.
- The 12 pads, with every setting.
- The progression, including On/Off.
- Smooth and Hints.
- Window state: the page, Chords or Scales, the selected pad, Play as I browse, Lead-in, the Fill size (Triads/7ths/9ths), the editor tab, the loaded pad set's name, and the shortlist.

### Not saved

FIND text, the filters, the selected notes, Follow MIDI, Slash, Contains/Exact, Caught, Read results, and the Undo and Redo history.

### Pad set files

Each set is a file named `<name>.lumenpads`:

- Windows: `%APPDATA%\Lumen-Index\Pad sets\`
- Mac: `~/Library/Application Support/Lumen-Index/Pad sets/`

The folder is shared by every project, every instance and the standalone app on that computer. The list shows at most 200 sets.

### Older projects

Projects from 0.2.x open in 1.4.1. Projects from before 1.0.5 open with arpeggios off, and projects from before 1.3 open with Smooth off.

---

## Troubleshooting and Save log

### No sound

- Lumen-Index makes no sound itself. It needs an instrument after it: in Bitwig, put it **first** on an instrument track, before the synth; in Logic, in the Software Instrument track's **MIDI FX** slot; in the standalone apps, pick a device under **MIDI OUT**.
- Check **Output channel** (host parameter) or **CH** (apps): if everything goes out on a channel your synth isn't listening to, you'll hear nothing.
- Pads play from the trigger octave only (C1–B1 by default). If your keyboard doesn't reach that octave, change **Trigger keys**.
- In the Windows app, no MIDI IN is chosen on first run. Pick your keyboard.
- The progression is silent unless it's **On**, the transport is playing (apps: clock after Start), and the role is **Pads**.

### Notes doubled

Lumen-Index itself never starts a note that's already sounding on the same key and channel. If you hear notes twice, the synth is most likely getting them from a second path as well as from Lumen-Index, for example from another track or MIDI route listening to the same keyboard, or (with hardware) from its own keyboard. To check what Lumen-Index sent, press **Save log** right after it happens: the log lists every note in and out.

### Stuck notes

Click **Panic** in the footer. It ends every voice and sends "all notes off". Then press **Save log** and send the file (see below).

### A drag lands nowhere

- Drop on the arranger or a launcher slot (in Logic, on a track). If the footer says "Drag cancelled…", the drop wasn't accepted.
- Bitwig places the clip on its grid, so it may land a little off where you let go.
- You can drag clips *out* of the window, but not from the arranger *into* it. To read an arranger clip, use Read as it plays, or export it as MIDI and drop the file.

### Bitwig asks whether to import the tempo

Fixed in 1.4: dragged clips no longer carry a tempo or time signature, so Bitwig doesn't ask. If it still asks, check the footer says **v1.4** or later; you may have an older version loaded.

### The guide says "No chord from the pads track yet"

- Both instances must have the **same link number**, and it can't be Off. Check the **LINK** chip on both.
- The track sending chords must have its role set to **Pads**. A guide doesn't send chords to another guide.
- Play a pad, or start the progression. The guide only shows a chord once one has been played.
- On a Mac, see [On a Mac](#on-a-mac) under Link.

### Read heard nothing

- Play the clip **on the same track** as the Lumen-Index you pressed Read on. Notes on another track don't reach it.
- The transport must be playing (apps: MIDI clock after Start).
- The trigger keys aren't read. If the clip's notes are in C1–B1 (or wherever your trigger keys are), they play pads instead. Move **Trigger keys** to an octave the clip doesn't use.
- If it says "No chords in it", the notes never sounded as a chord or an arpeggio, for example a single melody line.

### Typing in FIND doesn't give capitals or #

Bitwig may keep Shift from plug-in windows. Type in lowercase (`ebm9`); for sharps, use the **ROOT** filter. See [FIND](#find).

### Undo is empty, or Ctrl+Z does nothing

- The Undo history isn't saved with the project: it starts empty each time a project loads (in the apps, each time the app starts). Closing and reopening the plugin window keeps it.
- Only changes to the pads, the progression and the key are undo steps. Switching the progression On or Off, Snap, the link, the role and the trigger keys aren't.
- It keeps the last 32 steps. Redo empties as soon as you make a new change.
- Ctrl+Z (Cmd+Z on a Mac) only reaches Lumen-Index when its window has the keyboard: click in the window first. It does nothing while you're typing in FIND or a set name. If your host keeps the key for itself, use **Undo** and **Redo** in **Pad sets ▾**, which always work.

See [Undo and Redo](#undo-and-redo).

### Smooth or Hints seem to do nothing

Hints need a pad to have been played first. With Smooth, the first chord plays as voiced; the effect starts from the second.

### Save log

**Save log** in the footer writes a text file, `lumen-index-log.txt`, to your desktop:

- Windows: `Desktop\lumen-index-log.txt` in your user folder (`%USERPROFILE%\Desktop`). If OneDrive manages your Desktop, that may not be the desktop you see: the footer gives the full path.
- Mac: `~/Desktop/lumen-index-log.txt`.

If the Desktop can't be written to, it falls back to your home folder, then to the current folder (since 1.4.1 the standalone apps do this too). The footer shows "Log saved: <path>", or "Could not write the log file."

The log holds the version and platform, the host and its settings, a summary, your settings and pads (including the progression), a timed list of recent events, the last notes in and out (and any note still held), and the last drag-out.

**To send a log**

1. Press **Save log** right after the problem happens, before doing anything else.
2. Send the file with a line on what you did and what went wrong.

Each save overwrites the last file, so rename it first if you want to keep an earlier one.

---

## Reference

### Keyboard and mouse shortcuts

| Where | Key or click | Does |
|---|---|---|
| Index | ← / → | previous / next result |
| Index | ↑ / ↓ | up / down one row |
| Index | PgUp / PgDn | 12 results back / on |
| Index | Space | replay the selected chord or scale |
| Index (Chords) | Enter | add to the shortlist, or remove if already there |
| Anywhere, not typing | Ctrl+Z (Mac: Cmd+Z) | Undo |
| Anywhere, not typing | Ctrl+Shift+Z or Ctrl+Y (Mac: Cmd+Shift+Z or Cmd+Y) | Redo |
| FIND field | Enter, Esc or Tab | leave the field |
| Pad sets name field | Enter | save |
| Pad sets name field | Esc | close the menu |
| Pad sets name field | Tab | leave the field |
| Anywhere | Esc | close a menu, or stop filling progression slots |
| Windows, during a drag | Esc | cancel the drag |
| LINK chip | click / right-click | next / previous link number |
| STRUM, VELOCITY sliders | click or drag | set the value under the mouse |
| STRUM, VELOCITY sliders | right-drag, or Ctrl+drag (Mac: Cmd or Option+drag) | fine adjustment: 10 times finer, from where it was |
| STRUM, VELOCITY sliders | mouse wheel | one step: 5 ms of strum, 1 of velocity |
| Progression slot | right-click | clear it (rest) |
| CH (apps) | click / right-click | next / previous channel |
| Mac | Control-click | same as right-click |

### Parameters the host can automate

All are stepped.

| Name | Values | Default |
|---|---|---|
| Role | Pads, Melody guide, Bass guide | Pads |
| Key | C to B (spelt per Accidentals in the automation lane; the window spells the key as it is written) | C |
| Accidentals | Sharps, Flats: only for keys that can be written either way (F♯/G♭ major, D♯/E♭ minor) | Flats |
| Scale | any of the 56 scales | Major |
| Snap | Off, Nearest, Up, Down, Mute | Off |
| Snap to | Scale, Chord tones | Scale |
| Link | Off, 1, 2, 3, 4 | 1 |
| Output channel | Same as input, 1–16 | Same as input |
| Trigger octave | C-1–B-1 to C7–B7 | C1–B1 |

**Output channel**: every note (pads, pass-through, auditions, the progression) goes out on that channel. With "Same as input", a note goes out on the channel it came in on, and window clicks, auditions and the progression use channel 1. Other MIDI messages (CC, pitch bend, program change, aftertouch) pass through on the output channel.

### Limits and numbers

| What | Number |
|---|---|
| Chord types | 50 (49 names: 1 4 ♭7 is written 7sus4, like 1 4 5 ♭7) |
| Chords | 588 (49 names × 12 roots) |
| Scales | 56 (672 on 12 roots): 29 with seven notes, 10 with five, 6 with six, 8 with eight, one each with 9, 10 and 12 |
| Mode families | 4: Major (7 modes), Harmonic minor (7), Melodic minor (7), Major pentatonic (5) |
| Scales in the KEY menu | 16 |
| Scale families (FAMILY filter) | 9 |
| Pads | 12 |
| Inversion buttons | 4 (Root to 3rd) |
| Pad octave | 0–6 |
| Strum | 0–250 ms |
| Fixed velocity | 1–127 |
| Arpeggio | up to 24 notes, over 1–3 octaves |
| Progression | up to 16 slots of 1/4 (a beat), 1/2, 1 or 2 bars; loops of 4, 8 or 16 bars (beat slots: 4; half-bar slots: up to 8) |
| Shortlist | 24 chords |
| Previews (▶ Play, a tile click, browsing) | up to 16 notes; a scale plays every note and the octave (chromatic: 13 notes) |
| Pad sets | 200 listed; names up to 39 characters |
| Undo | 32 steps; Redo as many as you've undone |
| Read | 64 bars, 4096 notes, 256 chords and rests, 12 pads, files up to 16 MB |
| Caught | 8 cards, the last 48 notes per chord |
| Dragged clip | 24 chords, 256 single notes |
| Link groups | 4 |
| Chords sounding at once | 48 (each held pad, audition or progression chord is one; an audition with a lead-in is two; notes passing through aren't limited). This isn't the footer's "voices", which counts single notes |
| Window | 1200 × 720, not resizable (scaled by the host or system) |

### The 50 chord types

maj, m, °, +, sus2, sus4, 5, 6, m6, 6/9, m6/9, maj7, 7, m7, m(maj7), m7♭5, °7, +maj7, +7, 7sus4, 7♭5, maj9, 9, m9, add9, m(add9), 9sus4, 7♭9, 7♯9, m(maj9), 11, m11, maj7♯11, 7♯11, add11, 13, m13, maj13, 7♭13, 7alt, 7sus4 without the 5th (quartal; was written sus4(♭7)), m7(11), 13sus4, 13♭9, 7♭9♭13, 9♯11, 7♯5♭9, 13♯11, 7sus2, add4.

### Where files go

| File | Windows | Mac |
|---|---|---|
| Pad sets | `%APPDATA%\Lumen-Index\Pad sets\` | `~/Library/Application Support/Lumen-Index/Pad sets/` |
| App settings | `%APPDATA%\Lumen-Index\settings.txt` | `~/Library/Application Support/Lumen-Index/settings.txt` |
| Save log | `%USERPROFILE%\Desktop\lumen-index-log.txt` (with OneDrive, check the path in the footer) | `~/Desktop/lumen-index-log.txt` |
| Dragged clips (temporary) | `%TEMP%\Lumen-Index\` | the system's temporary folder, in `Lumen-Index/` |

### Known limitations

- 4/4 only: the progression, Read and clip lengths ignore time signatures.
- The apps have no tempo setting; without MIDI clock they run at 120 bpm.
- The apps don't pass SysEx.
- On a Mac, the link only reaches instances in the same process.
- The window can't be resized, only scaled.
- Read finds only major and natural minor keys, only the 41 chord types of 1.4, and at most 64 bars.
- Undo isn't saved with the project, and whether a host passes Ctrl+Z / Cmd+Z on to the plug-in window depends on the host; **Undo** and **Redo** in **Pad sets ▾** always work.
- **Pads + progression** doesn't switch the progression On.
- At most four inversion buttons (Root to 3rd).
- Pad cards always spell trigger keys with sharps.
- You can't drag arranger clips into the window (Bitwig, Logic).
- Bitwig may keep Shift from the window: type FIND in lowercase.
- Not code-signed yet: Windows and macOS warn the first time (see [If Windows or macOS won't open it](#if-windows-or-macos-wont-open-it)).
- Pad set names and clip file names use plain ASCII characters only.
- In Bitwig, recording the track can record the trigger keys rather than the chords: drag the chords out instead.
