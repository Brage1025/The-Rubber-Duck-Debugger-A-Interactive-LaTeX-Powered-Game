<div align="center">

# The Rubber Duck Debugger

[![CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](http://creativecommons.org/licenses/by/4.0/)
![LaTeX](https://img.shields.io/badge/Made%20with-LaTeX-008080.svg?logo=latex)
![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![Build Status](https://img.shields.io/badge/build-passing-brightgreen.svg)
[![GitHub stars](https://img.shields.io/github/stars/Brage1025/The-Rubber-Duck-Debugger-A-Interactive-LaTeX-Powered-Game?style=social)](https://github.com/Brage1025/The-Rubber-Duck-Debugger-A-Interactive-LaTeX-Powered-Game)

**A interactive LaTeX‑powered game**

</div>

This project is the result of me trying to learn some more advanced **TeX programming**. It implements a branching narrative game entirely within LaTeX, using macros, token lists, hyperlinks, and conditionals—all to tell a story about a programmer _(Self insert much)_, a stubborn bug _(You have no idea how many I had to deal with)_, and a squeaky debugging companion.

## Features

- **Interactive story** in a PDF: click on choices to navigate the story.
- **Multiple endings**: find the winning path or have some coffee.
- **Pun‑heavy theme**: rubber duck debugging meets LaTeX typesetting.
- **Cleanly separated game engine and data**: easy to extend with new scenes.
- **Fully commented code** explaining each TeX trick used—ideal for me to review later if needed.

## How to Play

**(Quick Play)**: Just download and use the `rubber-duck-debugger.pdf`

1. **Clone the repository**:

   ```bash
   git clone https://github.com/Brage1025/The-Rubber-Duck-Debugger-A-Interactive-LaTeX-Powered-Game.git
   cd rubber-duck-debugger
   ```

2. **Compile the game** (requires a LaTeX distribution, e.g., TeX Live (What I'm using), MiKTeX, or MacTeX):

   ```bash
   pdflatex rubber-duck-debugger.tex
   pdflatex rubber-duck-debugger.tex   # run twice to resolve all hyperlinks
   ```

   Alternatively, use `latexmk`:

   ```bash
   latexmk -pdf rubber-duck-debugger.tex
   ```

3. **Open the resulting PDF** (`rubber-duck-debugger.pdf`) in any PDF viewer (Adobe Reader, Preview, etc, or even some browsers.) and click the blue links to make choices.

4. **Play through the story:** Can you fix the `\latex` error?

## Project Structure

- `rubber-duck-debugger.tex` – Main source file containing both the game engine and the story data.
- `README.md` – This file.
- `LICENSE` – MIT License (or your choice).
- `.gitignore` – Ignores LaTeX auxiliary files created by the project (`.aux`, `.log`, `.out`, etc.).

## How It Works

The game is built on a few custom macros:

- `\scene{id}{text}{choices}` – Defines a new scene.
  - `id` is a unique label used for hyperlinks.
  - `text` is the narrative displayed.
  - `choices` is a comma‑separated list of `\choice{description}{target}` commands.

- `\choice{description}{target}` – Renders a clickable link that jumps to the scene with the given `target` id.

Inside `\scene`, we use `\@for` (from the LaTeX kernel) to iterate over the choice list and `\hypertarget`/`\hyperlink` (from `hyperref`) to create navigation anchors and links. An empty choice list signals the end of the game.

The code is heavily commented to explain each step—perfect for anyone learning LaTeX programming.

It should be a decent example of turning LaTeX into a "game engine", demonstrating that LaTeX is far more than a typesetting tool (or just that typesetting tools can be used in more ways than one).

## Requirements

- A LaTeX distribution (TeX Live 2020+ recommended, what I used) with packages:
  - `geometry`
  - `hyperref`
  - `xcolor`
  - `parskip`
  - `etoolbox` (used for list processing)
- A PDF viewer that supports hyperlinks (all modern viewers should do).

## License

This project is licensed under the Creative Commons Attribution 4.0 International License. To view a copy of this license, visit http://creativecommons.org/licenses/by/4.0/ or see the [LICENSE](LICENSE) file.

You are free to share and adapt the material for any purpose, even commercially, as long as you provide appropriate credit.

## Contact Info

Email: meb102025@gmail.com

---

<div align="center">

Created by [Brage1025](https://github.com/Brage1025)

_"To &lt;div&gt; or not to &lt;div&gt;, that is the question."_

</div>
