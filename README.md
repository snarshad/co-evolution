# Co-Evolution

A living, generative artwork about humans and AI growing together. Living growth rises from below and digital growth descends from above. Where they meet, each bends a little toward the other without becoming the other. Around them drift phrases from a conversation about co-evolution, belonging and trust, and you can ask the piece questions out loud or by typing.

**Try it online:** https://snarshad.github.io/co-evolution/

2026 • Created at Wisdom Beyond - Beacons • Arshad Tayyeb, made together with Claude (Anthropic)

---

## Best in Google Chrome

The art itself works in any modern browser. The listening and answering features need **Google Chrome**, because Chrome has a small AI model, **Gemini Nano**, built in. It runs on your own computer, so the piece can answer questions without sending them anywhere.

To get the full experience you need:

- **Chrome 148 or newer** on a desktop or laptop: Windows 10 or 11, macOS 13 or later, Linux, or a Chromebook Plus. Phones are not supported.
- **About 22 GB of free disk space** for the model.
- **A graphics card with more than 4 GB of memory**, or 16 GB of RAM and at least 4 processor cores.

The first time, Chrome downloads the model (a few gigabytes). The page starts that download as soon as it can; if Chrome wants a click first, click anywhere on the art. A small dot next to the ear button shows the model's state:

| Dot | Meaning |
| --- | --- |
| Yellow, pulsing | Loading or downloading (hover to see progress) |
| Green | Ready: answers come from your computer |
| Red | Something went wrong (hover for the message) |
| Grey | This browser or computer can't run the model |

To see what Chrome has installed, type `chrome://on-device-internals` into the address bar.

**Other browsers.** Firefox and Safari show the art, sound, patterns and typing, but not listening or answers; a notice explains this when the page opens. Safari is not recommended because the animation runs slowly there. Microsoft Edge has a similar model in its preview versions (Canary or Dev, with a setting turned on in `edge://flags`).

---

## Run it on your own computer

The whole piece is a single file, `index.html`.

1. **Get the file.** Download this repository (the green **Code** button, then **Download ZIP**), or clone it:
   ```
   git clone https://github.com/snarshad/co-evolution.git
   ```
2. **Start a small local web server** in the folder that contains `index.html`. Open Terminal (Mac or Linux) or Command Prompt (Windows), go to that folder, and run:
   - Mac or Linux:
     ```
     cd path/to/co-evolution
     python3 -m http.server 8000
     ```
   - Windows:
     ```
     cd /d path\to\co-evolution
     py -m http.server 8000
     ```
   Python comes with macOS and most Linux systems. On Windows, install it from [python.org](https://www.python.org/downloads/) if `py` is not found.
3. **Open the piece in Chrome** at:
   ```
   http://localhost:8000/
   ```
4. When you are done, press **Control-C** in the Terminal or Command Prompt window to stop the server.

**Why not just double-click the file?** It works, but Chrome does not remember microphone permission for a file opened straight from disk, so it asks again every time listening restarts. Served from `localhost`, Chrome asks once. If you do open it from disk, a small **help** button appears at the top left after you turn on listening, with these same steps and copy buttons.

---

## What you can do

- **Tap or click anywhere** to plant a seed of both kinds of growth: a living line rising and a digital line descending from the same spot.
- **Sound (speaker button).** On by default; it begins with your first click or key press, since browsers only allow sound after you interact. The growth plays notes in a bright major scale, the two sides slowly find a shared rhythm, and a soft sound of flowing water runs underneath.
- **Microphone button.** Lets the garden hear the room. It listens to sound, not words: voices and claps plant seeds, low sounds feed the living side, high sounds feed the digital side, a steady shared rhythm pulls the pulses into step, and a quiet room makes the center glow.
- **Ear button: speech recognition.** Words people say drift in from the sides, and questions rise from below and get an answer from the digital side. Needs Chrome with Gemini Nano.
- **Dots button: reaction-diffusion patterns.** Soft spots grow and divide where the two kinds of growth meet, like the patterns on animal skins. It also turns on by itself after a minute.
- **Type to speak.** Start typing anywhere and a field appears at the bottom. Press Enter to send your words into the garden, as if you had said them.
- **Ask a question,** typed or spoken. Begin with words like *what*, *why* or *how*, or ask for something with *tell me* or *explain*. The digital side thinks for a moment, then answers in bright dotted letters that drift down from above.
- **About button (lower right).** Explains the piece and how it was made. While it is open, you can ask about the art itself, for example why it uses these colors, and the answers come from the point of view of the artwork and its makers.
- **The panel (lower left).** It folds to a small tab after 20 seconds; click the tab to open it again. **Pause** stops the growth and **Begin again** clears it.

**Left alone,** the garden keeps itself company: after a few seconds without a click it taps itself every three seconds, and after four minutes it starts over.

---

## Privacy

- The **microphone** mode only measures loudness, tone and rhythm on your computer. Nothing is recorded or sent.
- The **ear** mode uses Chrome's speech recognition, which sends audio to Google to turn it into words. The page says so while it is on.
- **Answers** come from Gemini Nano on your own computer. Nothing is stored, and the piece never knows who is speaking.

---

## Customizing your copy

Open `index.html` in a text editor and search for these names:

- **`DRONE_LEVEL`**: volume of the background water (1 is the original level; it ships at 0.2).
- **`RD_ENABLED`**: set to `false` to leave out the reaction-diffusion patterns, for slower computers.
- **`artworkContext`** and **`aboutContext`**: the plain-text notes the AI reads before answering. Edit them to change what it knows about the piece.
- **`ANTHROPIC_API_KEY`**: optionally, paste an [Anthropic API key](https://console.anthropic.com/) here so Claude can answer when Chrome's model isn't available. **Only do this in a copy that stays on your own computer.** Anyone who can open the file can read the key, so never commit a key to this repository or put it on a public website.

The terminal button in the panel opens a debug log that shows what the piece hears, how it classifies speech, and where answers come from.
