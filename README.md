# Presentating

This is the repository where all my slide decks live. I use [Hieroglyph](http://docs.hieroglyph.io/en/latest/) to make my slides, which live at http://slides.lucywyman.me

## Dependencies

Python (either 2 or 3)

## To build

```
cd source
virtualenv v
source v/bin/activate
pip install -r requirements.txt
make slides
```

Then, in your browser, go to file:///$HOME/path/to/slides/\_build/slides/my-slides.html

If you include [presenter notes](http://docs.hieroglyph.io/en/latest/getting-started.html#presenter-notes) in your slides, press 'c' to see them when viewing the slides
