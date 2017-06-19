# Slides

## Contributing

I use [hieroglyph](https://github.com/nyergler/hieroglyph) to make my slides. This should work for python 2.7, 3.3 or 3.4:

```
cd source
virtualenv v
source v/bin/activate
pip install -r requirements.txt
make slides
```

The slides will be built into the `_build/` directory, and you can just view them in your browser! (file:///home/full/path/to/\_build/myslides.html)
