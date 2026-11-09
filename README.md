# The Interpreter's Dilemma

An interactive game about consecutive interpretation. You play the interpreter in a business call between Hoca Nuri, a Turkish-speaking master calligrapher, and Dana Whitfield, the English-speaking director of an online arts program. For each line, you choose how to say it aloud, then see what the other person actually understood.

**Live demo:** _add your GitHub Pages link here_

## How it works

- Six moments from one meeting: a greeting, a specialist term (*icazet*), a vague time (*ikindi*), a polite "pay me what you see fit," English idioms rendered into Turkish, and a quiet question that tests neutrality.
- Every option is scored for how much meaning it keeps and how it affects trust in the room.
- After each choice, a gap bar shows what was kept and what was lost, with a note explaining why.
- The ending recaps each moment and includes a short glossary of the Turkish words used.
- Turkish lines include an optional "show the literal words" hint, so no Turkish is required to play.

## Run it locally

No build step and no dependencies. Open `index.html` in a browser. For live reload, use the Live Server extension in VS Code.

The page loads two fonts (Instrument Serif and Instrument Sans) from Google Fonts. Offline, it falls back to system fonts.

## Edit the content

All scenes live in the `<script>` section of `index.html`, between the `/*DATA*/` and `/*END*/` comments.

Each scene has:

| Field | Purpose |
| --- | --- |
| `topic`, `setup` | Title and context shown above the line |
| `speaker`, `from` | Who is speaking and in which language |
| `line`, `literal` | The spoken line and its word-for-word gloss |
| `meant` | What the speaker actually meant |
| `options` | The renderings to choose from, each with `kept` (0-100), `trust` (change), `verdict`, `heard` and `note` |

Add a scene by copying an existing block. The game picks up the new scene count automatically. Colors and fonts are defined as variables at the top of the `<style>` section.

## Technical notes

- Plain HTML, CSS and JavaScript in a single file.
- Light and dark themes through CSS variables and `prefers-color-scheme`.
- Responsive down to phone width.
- Keyboard accessible, with visible focus states and reduced-motion support.
- Option order is shuffled on every playthrough.

## Credits

Made by Hanan Sahin. Hoca Nuri, Dana Whitfield and the program they work with are fictional.
