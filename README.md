# Dirigible One

![Dirigible One specimen](documentation/specimen.png)

Dirigible One is a display typeface based on [Nunito](https://github.com/googlefonts/nunito) by Vernon Adams. Every contour has been pushed outward and all corners rounded as far as they go, so the letters look inflated. Single weight, Regular only.

The script that transforms Nunito into Dirigible One is at `sources/dirigible.py`.

## Building

Font is built using [gftools](https://github.com/googlefonts/gftools).

Recommended: set up a virtual environment so the dependencies stay separate from the rest of your system. Run this once:

```
python3 -m venv sources/venv
source sources/venv/bin/activate
```

You will see `(venv)` appear at the start of your prompt. That means the environment is active. Repeat the `source` line in any new terminal window to turn it back on.

Install dependencies:

```
pip install -r requirements.txt
```

Build:

```
cd sources
gftools builder config.yaml
```

The new font files will appear in `fonts/ttf/`, `fonts/otf/`, and `fonts/webfonts/`.

## Regenerating the UFO from Nunito

The script `sources/dirigible.py` is what turns a Nunito UFO source into the inflated Dirigible One UFO. You only need this if you want to rebuild the source from scratch (for example, after a Nunito update). Most people never need to run it.

To run it, point the script at a Nunito UFO file:

```
python sources/dirigible.py path/to/Nunito-Regular.ufo
```

It will write a new `Dirigible-Regular.ufo` next to the script. You can then open it in Glyphs or any other UFO editor.

Note: this script only produces the base inflated shapes from Nunito. It does not include the outline corrections or other manual cleanup that the shipped UFO has. Think of the script's output as a starting point, not a finished font.

## License

Dirigible One is licensed under the [SIL Open Font License, Version 1.1](OFL.txt).

Nunito was originally designed by Vernon Adams. Dirigible One is a derivative work by Michael Seh.
