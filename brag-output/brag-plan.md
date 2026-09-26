# Delulu Beats — launch video plan

**Angle.** A site played by ear has to be *heard*, so the video opens with a tone and no
music, and the first words are the site's own: *everything here is slightly off; your
job is to notice.* Then it proves it — four games, each shown mid-judgement, where the
app is telling you exactly how wrong you were.

**Hook (first 2s).** The cyan waveform, one real 311Hz tone sounding, and that line. No
logo, no music yet — the silence around the tone is the point.

**Punchline.** *Every sound you just heard was made in it.* Which is literally true: the
music bed is a loop built in Beat Lab and downloaded from it, and the opening tone is
recorded off Sine Language. Nothing in this video was synthesised by anything but the
product.

- **Tone:** default — punchy, clean. Cuts land on the bar; no crossfades between busy
  dark frames, a 3-frame dip instead.
- **Format:** landscape 1920×1080, 30fps, **21.3s = 11 bars at 124bpm**, so every cut is
  musical.
- **Identity:** the site's own — ink `#0c0d12`, bone `#eff0f4`, muted `#7e8290`, the amber
  `#ffb02e` of the logo's U, Unbounded for display and Spline Sans Mono for labels.

## Everything on screen and in the speakers is real

The footage is the real games driven live in a browser, recorded at 1280×800. The audio
was captured off the app's own master bus by tapping anything that connects to
`ctx.destination`, so it is the actual Web Audio output, not a re-creation.

| Heard | Where it came from |
|---|---|
| The opening tone | Sine Language, round 1, recorded live (311Hz on screen) |
| The music, all of it | A House loop at 124bpm built in **Beat Lab** and taken with its own Download button |

## Storyboard

| Bars | t | Footage | Words |
|---|---|---|---|
| 1 | 0.00 | Sine Language: the waveform, LISTEN 1 | **Everything here is slightly off.** |
| 2 | 1.94 | ” (music enters on the downbeat) | **Your job is to notice.** |
| 3–4 | 3.87 | Sine Language: 311 Hz, slider, LOCK IT IN | SINE LANGUAGE — *Hear a tone. Then find it again.* |
| 5–6 | 7.74 | Downbeat: notes on the lane, PERFECT | DOWNBEAT — *Hit every note on the beat.* |
| 7–8 | 11.61 | Off-Grid: WHICH HIT WAS LATE? → IT WAS BEAT 6 | OFF-GRID — *One hit is late. Find it.* |
| 9–10 | 15.48 | Beat Lab: the sequencer filling in | BEAT LAB — *Then build your own, and take it with you.* |
| 11 | 19.35 | — | Wordmark · **Every sound you just heard was made in it.** · delulubeats.com |

Nine games exist; four are shown. The outro says nine.

## Build

1. Drive each game in Playwright, recording video and tapping the master bus for audio.
2. Beat Lab: set House, press its own Download, keep the WAV it hands over.
3. Compose in one HTML stage, every frame a pure function of `t`, footage 1:1 (no
   speed change, so the real motion and timing survive).
4. 638 frames at 1920×1080 → ffmpeg, with the tone under bar 1 and the loop under 2–11.
